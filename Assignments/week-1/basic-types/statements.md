Example

```
fn main() {
    let x = 5u32;

    let y = {
        let x_squared = x * x;
        let x_cube = x_squared * x;
        
        x_cube + x_squared + x
    };

    let z = {
        2 * x
    };

    println!("x is {:?}", x);
    println!("y is {:?}", y);
    println!("z is {:?}", z);
}

output:
x is 5
y is 155
z is 10

```
Exercises

1.
```
fn main() {
   let v = {
       let mut x = 1;
       x += 2;
       x
   };

   assert_eq!(v, 3);
   println!("Success!");
}

output: Success!

Explanation: add x in main function.

```
2.
fn main() {
   let v = {
       let x = 3;
       x
   };

   assert!(v == 3);
   println!("Success!");
}

output: Success!

Explanation: add x in main function

```
3.
fn main() {
    let s = sum(1 , 2);
    assert_eq!(s, 3);
    println!("Success!");
}

fn sum(x: i32, y: i32) -> i32 {
    x + y
}

output: Success!

Explanation: removed semi-colon in x + y

```