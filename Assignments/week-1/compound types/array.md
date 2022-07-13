
1.
```rust
/* // FIX the error with least changing
// DON'T remove any code line
fn main() {
    let mut v = String::from("hello,");
    let r = &mut v;

    match r {
       &mut value => value.push_str(" world!") 
    }
} */

fn main() {
    let arr: [i32; 5] = [1, 2, 3, 4, 5];

    assert!(arr.len() == 5);

    println!("Success!");
}

output: Success!

Explanation: Changed the len acc to the array size

```

2.
```rust
/* fn main() {
    // We can ignore parts of the array type or even the whole type, let the compiler infer it for us
    let arr0 = [1, 2, 3];
    let arr: [_; 3] = ['a', 'b', 'c'];
    
    // Fill the blank
    // Arrays are stack allocated, `std::mem::size_of_val` returns the bytes which an array occupies
    // A char takes 4 bytes in Rust: Unicode char
    assert!(std::mem::size_of_val(&arr) == __);

    println!("Success!");
} */

fn main() {
    // we can ignore parts of the array type or even the whole type, let the compiler infer it for us
    let arr0 = [1, 2, 3];
    let arr: [_; 3] = ['a', 'b', 'c'];

    // Arrays are stack allocated, `std::mem::size_of_val` return the bytes which array occupies
    // A char takes 4 byte in Rust: Unicode char
    assert!(std::mem::size_of_val(&arr) == 12);

     println!("Success!");
}

output: Success!

Explanation: the size of val is 12

```

3.
```rust
/* fn main() {
    // Fill the blank
    let list: [i32; 100] = __ ;

    assert!(list[0] == 1);
    assert!(list.len() == 100);

    println!("Success!");
} */

fn main() {
    let list: [i32; 100] = [1; 100];

    assert!(list[0] == 1);
    assert!(list.len() == 100);
    println!("Success!");
}

output: Success!

Explanation: Added [1;100]

```

4.
```rust
/* fn main() {
    // Fix the error
    let _arr = [1, 2, '3'];

    println!("Success!");
}
 */

fn main() {
    // fix the error
    let _arr = [1, 2, 3];
    println!("Success!");
}

output: Success!

Explanation: changed '3' -> 3

```

5.
```rust
/* fn main() {
    let arr = ['a', 'b', 'c'];
    
    let ele = arr[1]; // Only modify this line to make the code work!

    assert!(ele == 'a');

    println!("Success!");
} */

fn main() {
    let arr = ['a', 'b', 'c'];

    let ele = arr[0];

    assert!(ele == 'a');
    println!("Success!");
}

output: Success!

Explanation: changed the arr[1] -> [0]

```

6.
```rust
/* // Fix the error
fn main() {
    let names = [String::from("Sunfei"), "Sunface".to_string()];
    
    // `Get` returns an Option<T>, it's safe to use
    let name0 = names.get(0).unwrap();

    // But indexing is not safe
    let _name1 = &names[2];

    println!("Success!");
} */

fn main() {
    let names = [String::from("Sunfei"), "Sunface".to_string()];

    // `get` returns an Option<T>, it's safe to use
    let name0 = names.get(0).unwrap();

    // but indexing is not safe
    let _name1 = &names[1];
    println!("Success!");
}

output: Success!

Explanation: changed the index -> 1

```