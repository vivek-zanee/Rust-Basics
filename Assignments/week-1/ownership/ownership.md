Ownership

1.
```
fn main() {
    let x = String::from("hello, world");
    let y = x.clone();
    println!("{},{}",x,y);
}

output: hello, world,hello, world

Explanation: clone() method used

```

2.
```
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
```
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
```
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
```
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
```
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
```
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
```
fn main() {
   let t = (String::from("hello"), String::from("world"));

   let _s = t.0;

   println!("{:?}", t.1);
}

output: "world"

Explanation: added t.1 in print to print the second part of t

```

9.
```
fn main() {
   let t = (String::from("hello"), String::from("world"));

    let (s1, s2) = t.clone();

    println!("{:?}, {:?}, {:?}", s1, s2, t); 
}

output: "hello", "world", ("hello", "world")

Explanation: Added let (s1, s2) = t.clone()

```

