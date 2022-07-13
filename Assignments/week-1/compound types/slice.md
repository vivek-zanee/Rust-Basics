
1.
```rust
/* // Fix the errors, DON'T add new lines!
fn main() {
    let arr = [1, 2, 3];
    let s1: [i32] = arr[0..2];

    let s2: str = "hello, world" as str;

    println!("Success!");
} */

fn main() {
    let arr = [1, 2, 3];
    let s1: &[i32] = &arr[0..2];

    let s2: &str = "hello, world";
    println!("Success!");
}

output: Success!

Explanation: Added & in s1

```

2.
```rust
/* fn main() {
    let arr: [char; 3] = ['中', '国', '人'];

    let slice = &arr[..2];
    
    // Modify '6' to make it work
    // TIPS: slice( reference ) IS NOT an array, if it is an array, then `assert!` will passed: Each of the two UTF-8 chars '中' and '国'  occupies 3 bytes, 2 * 3 = 6
    assert!(std::mem::size_of_val(&slice) == 6);

    println!("Success!");
} */

fn main() {
    let arr: [char; 3] = ['中', '国', '人'];

    let slice = &arr[..2];

    // TIPS: slice( reference ) IS NOT an array, if it is an array, then `assert!` will passed: each of the two UTF-8 chars '中' and '国'  occupies 3 bytes, 2 * 3 = 6
    assert!(std::mem::size_of_val(&slice) == 16);
    println!("Success!");
}

output: Success!

Explanation: size of val is 16

```

3.
```rust
/* fn main() {
    let arr: [i32; 5] = [1, 2, 3, 4, 5];
    // Fill the blanks to make the code work
    let slice: __ = __;
    assert_eq!(slice, &[2, 3, 4]);

    println!("Success!");
} */

fn main() {
    let arr: [i32; 5] = [1, 2, 3, 4, 5];
    let slice: &[i32] = &arr[1..4];
    assert_eq!(slice, &[2, 3, 4]);
    println!("Success!");
}

output: Success!

Explanation: added slice: &[i32] = &arr[1..4];

```
String slices

4.
```rust
/* fn main() {
    let s = String::from("hello");

    let slice1 = &s[0..2];
    // Fill the blank to make the code work, DON'T USE 0..2 again
    let slice2 = &s[__];

    assert_eq!(slice1, slice2);

    println!("Success!");
} */

fn main() {
    let s = String::from("hello");

    let slice1 = &s[0..2];
    let slice2 = &s[..2];

    assert_eq!(slice1, slice2);
    println!("Success!");
}

output: Success!

Explanation: Added index value ..2 in slice2

```

5.
```rust
/* fn main() {
    let s = "你好，世界";
    // Modify this line to make the code work
    let slice = &s[0..2];

    assert!(slice == "你");

    println!("Success!");
} */

fn main() {
    let s = "你好，世界";
    let slice = &s[0..3];

    assert!(slice == "你");
    println!("Success!");
}

output: Success!

Explanation: Replaced index value ..3 in slice

```

6.
```rust
/* // Fix errors
fn main() {
    let mut s = String::from("hello world");

    // Here, &s is `&String` type, but `first_word` need a `&str` type.
    // It works because `&String` can be implicitly converted to `&str, If you want know more ,this is called `Deref` 
    let word = first_word(&s);

    s.clear(); // error!

    println!("the first word is: {}", word);
}
fn first_word(s: &str) -> &str {
    &s[..1]
} */

fn main() {
    let mut s = String::from("hello world");

    // here, &s is `&String` type, but `first_word` need a `&str` type.
    // it works because `&String` can be implicitly converted to `&str, If you want know more ,this is called `Deref` 
    let word = first_word(&s);

    println!("the first word is: {}", word);

    s.clear();
}

fn first_word(s: &str) -> &str {
    &s[..1]
}

output: the first word is: h

Explanation: s.clear() comes after it prints the word.

```
