Ownership

1.
```rust
/* fn main() {
    // Use as many approaches as you can to make it work
    let x = String::from("hello, world");
    let y = x;
    println!("{},{}",x,y);
} */

fn main() {
    let x = String::from("hello, world");
    let y = x.clone();
    println!("{},{}",x,y);
}

output: hello, world,hello, world

Explanation: clone() method used

```

2.
```rust
/* // Don't modify code in main!
fn main() {
    let s1 = String::from("hello, world");
    let s2 = take_ownership(s1);

    println!("{}", s2);
}

// Only modify the code below!
fn take_ownership(s: String) {
    println!("{}", s);
} */

fn main() {
    let s1 = String::from("hello, world");
    let s2 = take_ownership(s1);

    println!("{}", s2);
}

fn take_ownership(s: String)-> String {
    println!("{}", s);
    s
}

output: 
hello, world
hello, world

Explanation:
Add String method in fn take_ownership.

```

3.
```rust
/* fn main() {
    let s = give_ownership();
    println!("{}", s);
}

// Only modify the code below!
fn give_ownership() -> String {
    let s = String::from("hello, world");
    // Convert String to Vec
    let _s = s.into_bytes();
    s
} */

fn main() {
    let s = give_ownership();
    println!("{}", s);
}

// Only modify the code below!
fn give_ownership() -> String {
    let s = String::from("hello, world"); 
    s
}

output: hello, world

Explanation: Remove Inappropriate Lines.

```

4.
```rust
/* // Fix the error without removing code line
fn main() {
    let s = String::from("hello, world");

    print_str(s);

    println!("{}", s);
}

fn print_str(s: String)  {
    println!("{}",s)
} */

fn main() {
    let s = String::from("hello, world");

    print_str(s.clone());

    println!("{}", s);
}

fn print_str(s: String)  {
    println!("{}",s)
}

output:
hello, world
hello, world

Explanation: clone() method used

```

5.
```rust
/* // Don't use clone ,use copy instead
fn main() {
    let x = (1, 2, (), "hello".to_string());
    let y = x.clone();
    println!("{:?}, {:?}", x, y);
} */

fn main() {
    let x = (1, 2, (), "hello");
    let y = x;
    println!("{:?}, {:?}", x, y);
}

output: (1, 2, (), "hello"), (1, 2, (), "hello")

Explanation: Changed y=x line to get output

```

Mutability

6.
```rust
/* fn main() {
    let s = String::from("hello, ");
    
    // Modify this line only !
    let s1 = s;

    s1.push_str("world");

    println!("Success!");
} */

fn main() {
    let s = String::from("hello, ");
    
    let mut s1 = s;

    s1.push_str("world");

    println!("Success!");
}

output: Success!

Explanation: Added mut in s1 = s

```

7.
```rust
/* fn main() {
    let x = Box::new(5);
    
    let ...      // Implement this line, dont change other lines!
    
    *y = 4;
    
    assert_eq!(*x, 5);

    println!("Success!");
} */

fn main() {
    let x = Box::new(5);
    
    let mut y = Box::new(3);   
    
    *y = 4;
    
    assert_eq!(*x, 5);

    println!("Success!");
}

output: Success!

Explanation: added mut y = Box::new(3)

```

Partial move

8.
```rust
/* fn main() {
   let t = (String::from("hello"), String::from("world"));

   let _s = t.0;

   // Modify this line only, don't use `_s`
   println!("{:?}", t);
} */

fn main() {
   let t = (String::from("hello"), String::from("world"));

   let _s = t.0;

   println!("{:?}", t.1);
}

output: "world"

Explanation: added t.1 in print to print the second part of t

```

9.
```rust
/* fn main() {
   let t = (String::from("hello"), String::from("world"));

    // Fill the blanks
    let (__, __) = __;

    println!("{:?}, {:?}, {:?}", s1, s2, t); // -> "hello", "world", ("hello", "world")
} */

fn main() {
   let t = (String::from("hello"), String::from("world"));

    let (s1, s2) = t.clone();

    println!("{:?}, {:?}, {:?}", s1, s2, t); 
}

output: "hello", "world", ("hello", "world")

Explanation: Added let (s1, s2) = t.clone()

```

