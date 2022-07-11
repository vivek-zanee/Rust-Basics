Integer

1. 
```
 fn main() {
    let x: u32 = 5;
    let mut y: u32 = 5;
    y = x;
    println!("Success!");
}

output: Success!

Explanation: Changed the data type of x, i32 -> u32 and removed let z = 10.

```
2.
```
fn main() {
    let v: u16 = 38_u8 as u16;
    println!("Success!");
}

output: Success!

Explanation: Added u16 in let v line.

```
3.
```
fn main() {
    let x = 5;
    assert_eq!("i32".to_string(),type_of(&x));  // 1
    println!("Success!");
}

fn type_of<T>(_: &T) -> String {
    format!("{}", std::any::type_name::<T>())
}

output: Success!

Explanation: changed 'u32' -> 'i32' in 1

```
4.
```
fn main() {
    assert_eq!(i8::MAX, 127); 
    assert_eq!(u8::MAX, 255); 
    println!("Success!");
}

output: Success!

Explanation: Added 127 and 255 as in the max value of i8 and u8.

```
5.
```
fn main() {
   let v1 = 247_u8 + 8;
   let v2 = i8::checked_add(119, 8).unwrap();
   println!("{},{}",v1,v2);
}

output: Success!

Explanation: changed 251_u8 to 247_u8 in v1 and add(251,8) to (119,8) in v2, since it is the max value of u8 and i8.

```

6.
```
fn main() {
    let v = 1_024 + 0xff + 0o77 + 0b1111_1111;
    assert!(v == 1597);
    println!("Success!");
}

output: Success!

Explanation: changed v == 1579 -> 1597 as, if we add the v it will give 1597.

```
Floating-Point

7.
```
fn main() {
    let x = 1_000.000_1; // f64
    let y: f32 = 0.12; // f32
    let z = 0.01_f64; // f64

    println!("Success!");
}

output: Success!

Explanation: added f64 in cmnt area to describe its type.

```
8.
```
fn main() {
    assert!(0.1_f32 +0.2_f32 ==0.3_f32);
    println!("Success!");
}

output: Success!

Explanation: added _f32 in the line to get float output.

```
Range

9.
```
fn main() {
    let mut sum = 0;
    for i in -3..2 {
        sum += i
    }

    assert!(sum == -5);

    for c in 'a'..='z' {
        println!("{}",c as u8);
    }
}

Explanation: added c as u8 as the output will be unsigned datatype.

```
10.
```
use std::ops::{Range, RangeInclusive};
fn main() {
    assert_eq!((1..5), Range{ start: 1, end: 5 });
    assert_eq!((1..=5), RangeInclusive::new(1, 5));
    println!("Success!");
}

output: Success!

Explanation: Filled with 5 and =5 to complete the code.

```
Computations

11.
```
fn main() {
    // Integer addition
    assert!(1u32 + 2 == 3);

    // Integer subtraction
    assert!(1i32 - 2 == -1);
    assert!(1i8 - 2 == -1); 
    
    assert!(3 * 50 == 150);

    assert!(9/ 3 == 3); // error ! make it work

    assert!(24 % 5 == 4);
    // Short-circuiting boolean logic
    assert!(true && false == false);
    assert!(true || false == true);
    assert!(!true == false);

    // Bitwise operations
    println!("0011 AND 0101 is {:04b}", 0b0011u32 & 0b0101);
    println!("0011 OR 0101 is {:04b}", 0b0011u32 | 0b0101);
    println!("0011 XOR 0101 is {:04b}", 0b0011u32 ^ 0b0101);
    println!("1 << 5 is {}", 1u32 << 5);
    println!("0x80 >> 2 is 0x{:x}", 0x80u32 >> 2);
}

output:
0011 AND 0101 is 0001
0011 OR 0101 is 0111
0011 XOR 0101 is 0110
1 << 5 is 32
0x80 >> 2 is 0x20

Explanation: Added unsigned datatype in some areas and true, false in boolean logic.

```
