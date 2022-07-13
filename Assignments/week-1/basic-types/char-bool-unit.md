Char

1.
```rust
/* // Make it work
use std::mem::size_of_val;
fn main() {
    let c1 = 'a';
    assert_eq!(size_of_val(&c1),1); 

    let c2 = '中';
    assert_eq!(size_of_val(&c2),3); 

    println!("Success!");
} */

use std::mem::size_of_val;
fn main() {
    let c1 = 'a';
    assert_eq!(size_of_val(&c1),4); 

    let c2 = '中';
    assert_eq!(size_of_val(&c2),4); 

    println!("Success!");
} 

output: Success!

Explanation: Changed the value of c1 and c2 -> 4.

```
2.
```rust
/* // Make it work
fn main() {
    let c1 = "中";
    print_char(c1);
} 

fn print_char(c : char) {
    println!("{}", c);
} */

fn main() {
    let c = '中';
    print_char(c);
} 

fn print_char(c: char) {
    println!("{}", c);
}

output: Success!

Explanation: changed the "中" -> '中'

```
Bool

3.
```rust
/* // Make println! work
fn main() {
    let _f: bool = false;

    let t = true;
    if !t {
        println!("Success!");
    }
}  */

fn main() {
    let _f: bool = false;
    let t = false;
    if !t {
        println!("Success!");
    }
}

output: Success!

Explanation: Changed the t = true to get the if condition work

```
4.
```rust
/* // Make it work
fn main() {
    let f = true;
    let t = true && false;
    assert_eq!(t, f);

    println!("Success!");
} */

fn main() {
    let f = true;
    let t = true || false;
    assert_eq!(t, f);
    println!("Success!");
}

output: Success!

Explanation: Changed the && to ||

```
Unit type

5.
```rust
/* // Make it work, don't modify `implicitly_ret_unit` !
fn main() {
    let _v: () = ();

    let v = (2, 3);
    assert_eq!(v, implicitly_ret_unit());

    println!("Success!");
}

fn implicitly_ret_unit() {
    println!("I will return a ()");
}

// Don't use this one
fn explicitly_ret_unit() -> () {
    println!("I will return a ()");
} */

fn main() {
    let v0: () = ();

    let v = (2, 3);
    assert_eq!(v0, implicitly_ret_unit());
    println!("Success!");
}

fn implicitly_ret_unit() {
    println!("I will return a ()");
}

fn explicitly_ret_unit() -> () {
    println!("I will return a ()");
}

output: 
I will return a ()
Success!

Explanation: made changes in first two lines to start from v0.

```
6.
```rust
/* // Modify `4` in assert to make it work
use std::mem::size_of_val;
fn main() {
    let unit: () = ();
    assert!(size_of_val(&unit) == 4);

    println!("Success!");
} */

use std::mem::size_of_val;
fn main() {
    let unit: () = ();
    assert!(size_of_val(&unit) == 0);

    println!("Success!");
}

output: Success!

Explanation: the value is changed to 0.

```