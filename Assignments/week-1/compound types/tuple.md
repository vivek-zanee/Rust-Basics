1.

```rust
/* fn main() {
    let _t0: (u8,i16) = (0, -1);
    // Tuples can be tuple's members
    let _t1: (u8, (i16, u32)) = (0, (-1, 1));
    // Fill the blanks to make the code work
    let t: (u8, __, i64, __, __) = (1u8, 2u16, 3i64, "hello", String::from(", world"));

    println!("Success!");
} */

fn main() {
    let _t0: (u8,i16) = (0, -1);
    // Tuples can be tuple's members
    let _t1: (u8, (i16, u32)) = (0, (-1, 1));
    let t: (u8, u16, i64, &str, String) = (1u8, 2u16, 3i64, "hello", String::from(", world"));
    println!("Success!");
}

output: Success!

Explanation: Types have been added to complete the code

```

2.
```rust
/* // Make it work
fn main() {
    let t = ("i", "am", "sunface");
    assert_eq!(t.1, "sunface");

    println!("Success!");
} */

fn main() {
    let t = ("i", "am", "sunface");
    assert_eq!(t.2, "sunface");
    println!("Success!");
 }

output: Success!

Explanation: Changed t.1 -> t.2

```

3.
```rust
/* // Fix the error
fn main() {
    let too_long_tuple = (1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13);
    println!("too long tuple: {:?}", too_long_tuple);
} */

fn main() {
    let too_long_tuple = (1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12);
    println!("too long tuple: {:?}", too_long_tuple);
}

output: too long tuple: (1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12)

Explanation: Removed 13 as a tuple holds 12 values

```

4.
```rust
/* fn main() {
    let tup = (1, 6.4, "hello");

    // Fill the blank to make the code work
    let __ = tup;

    assert_eq!(x, 1);
    assert_eq!(y, "hello");
    assert_eq!(z, 6.4);

    println!("Success!");
} */

fn main() {
    let tup = (1, 6.4, "hello");

    let (x, z, y) = tup;

    assert_eq!(x, 1);
    assert_eq!(y, "hello");
    assert_eq!(z, 6.4);

     println!("Success!");
}

output: Success!

Explanation: Added (x, z, y) to complete tupe order

```

5.
```rust
/* fn main() {
    let (x, y, z);

    // Fill the blank
    __ = (1, 2, 3);
    
    assert_eq!(x, 3);
    assert_eq!(y, 1);
    assert_eq!(z, 2);

    println!("Success!");
}
 */
fn main() {
    let (x, y, z);

    // fill the blank
    (y, z, x) = (1, 2, 3);
    
    assert_eq!(x, 3);
    assert_eq!(y, 1);
    assert_eq!(z, 2);

    println!("Success!");
}

output: Success!

Explanation: Added (y, z, x) to complete tupe order

```

6.
```rust
/* fn main() {
    // Fill the blank, need a few computations here.
    let (x, y) = sum_multiply(__);

    assert_eq!(x, 5);
    assert_eq!(y, 6);

    println!("Success!");
}

fn sum_multiply(nums: (i32, i32)) -> (i32, i32) {
    (nums.0 + nums.1, nums.0 * nums.1)
} */

fn main() {
    let (x, y) = sum_multiply((2, 3));
 
    assert_eq!(x, 5);
    assert_eq!(y, 6);

    println!("Success!");
 }
 
 fn sum_multiply(nums: (i32, i32)) -> (i32, i32) {
     (nums.0 + nums.1, nums.0 * nums.1)
 }

output: Success!

Explanation: Added (2, 3) to complete (x,y)

```