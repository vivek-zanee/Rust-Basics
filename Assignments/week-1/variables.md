Binding and mutability

1.
```rust
/* // Fix the error below with least amount of modification to the code
fn main() {
    let x: i32; // Uninitialized but used, ERROR !
    let y: i32; // Uninitialized but also unused, only a Warning !

    assert_eq!(x, 5);
    println!("Success!");
} */

fn main() {
    let x: i32 = 5; 
    let y: i32; 

    assert_eq!(x, 5);
    println!("Success!");
}

output: Success!

Explanation: initialize i32 = 5

```
2.
```rust
/* // Fill the blanks in the code to make it compile
fn main() {
    let __ =  1;
    __ += 2; 
    
    assert_eq!(x, 3);
    println!("Success!");
} */

fn main() {
    let mut x =  1;
    x += 2; 
    
    assert_eq!(x, 3);
    println!("Success!");
}

output: Success!

Explanation: add mut since x is used twice

```
Scope

3.
```rust
/* // Fix the error below with least amount of modification
fn main() {
    let x: i32 = 10;
    {
        let y: i32 = 5;
        println!("The value of x is {} and value of y is {}", x, y);
    }
    println!("The value of x is {} and value of y is {}", x, y); 
} */

fn main() {
    let x: i32 = 10;
    {
        let y: i32 = 5;
        println!("The value of x is {} and value of y is {}", x, y);
    }
    println!("The value of x is {}", x); 
}

output:
The value of x is 10 and value of y is 5
The value of x is 10

Explanation: Remove y out of scope, since y is declared inside the scope.

```
4.
```rust
/* // Fix the error with the use of define_x
fn main() {
    println!("{}, world", x); 
}

fn define_x() {
    let x = "hello";
} */

fn main() {
    let x = define_x();
    println!("{}, world", x); 
}

fn define_x() -> String{
    let x = "hello".to_string();
    x
}

output: hello, world

Explanation: add to_string() and declare x in main fn

```

Shadowing

5.
```rust
/* // Only modify `assert_eq!` to make the `println!` work(print `42` in terminal)
fn main() {
    let x: i32 = 5;
    {
        let x = 12;
        assert_eq!(x, 5);
    }

    assert_eq!(x, 12);

    let x =  42;
    println!("{}", x); // Prints "42".
} */

fn main() {
    let x: i32 = 5;
    {
        let x = 12;
        assert_eq!(x, 12);
    }

    assert_eq!(x, 5);

    let x =  42;
    println!("{}", x); // Prints "42".
}

output: 42

Explanation: changed the value in (x,_)

```
6.
```rust
/* // Remove a line in the code to make it compile
fn main() {
    let mut x: i32 = 1;
    x = 7;
    // Shadowing and re-binding
    let x = x; 
    x += 3;


    let y = 4;
    // Shadowing
    let y = "I can also be bound to text!"; 

    println!("Success!");
} */

fn main() {
    let mut x: i32 = 1;
    x = 7;
    // Shadowing and re-binding
    let x = x; 
    let y = 4;
    // Shadowing
    let y = "I can also be bound to text!"; 

    println!("Success!");
}

output: Success!

Explanation: remove unwanted fields

```
Unused Variables

7.
```rust
/* fn main() {
    let x = 1; 
}

// Warning: unused variable: `x` */

fn main() {
    let x = 1;
    println!("{}",x)
}

output: 1

Explanation: Declare the unused variable with println

```

Destructuring

8.
```rust
/* // Fix the error below with least amount of modification
fn main() {
    let (x, y) = (1, 2);
    x += 2;

    assert_eq!(x, 3);
    assert_eq!(y, 2);

    println!("Success!");
} */

fn main() {
    let (mut x, y) = (1, 2);
    x += 2;
    assert_eq!(x, 3);
    assert_eq!(y, 2);
    println!("Success!");
}

output: Success!

Explanation: added mut in x

```

Destructuring assignments

9.
```rust
/* fn main() {
    let (x, y);
    (x,..) = (3, 4);
    [.., y] = [1, 2];
    // Fill the blank to make the code work
    assert_eq!([x,y], __);

    println!("Success!");
}  */

fn main() {
    let (x, y);
    (x,..) = (3, 4);
    [.., y] = [1, 2];
    // Fill the blank to make the code work
    assert_eq!([x,y], [3,2]);
    println!("Success!");
} 

output: Success!

Explanation: added [3,2]

```
