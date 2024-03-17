To access arguments within the `Args` struct within the `let agrs: Args` variable we can use the nth method which exists on the `Args`. We're gonna declare new variables. First one is `first` and it will be assigned the value of calling the `nth` method `args.nth()` on args. hovering over the method in the replit ide will show more info:
```this method takes 1 argument but 0 arguments were supplied
Debug

rustc
core::iter::traits::iterator::Iterator
pub fn nth(&mut self, n: usize) -> Option<Self::Item>
Returns the nth element of the iterator.

Like most indexing operations, the count starts from zero, so nth(0) returns the first value, nth(1) the second, and so on.
```

##Note that all preceding elements, as well as the returned element, will be consumed from the iterator. That means that the preceding elements will be discarded, and also that calling nth(0) multiple times on the same iterator will return different elements.

#nth() will return None if n is greater than or equal to the length of the iterator.
```Examples
#Basic usage:

let a = [1, 2, 3];
assert_eq!(a.iter().nth(1), Some(&2));
Calling nth() multiple times doesn't rewind the iterator:

let a = [1, 2, 3];
let mut iter = a.iter();
assert_eq!(iter.nth(1), Some(&2));
assert_eq!(iter.nth(1), None);
Returning None if there are less than n + 1 elements:

let a = [1, 2, 3];
assert_eq!(a.iter().nth(10), None);
```
in the function definition we can see that it takes in two arguments`pub fn nth(&mut self, n: usize)` being a mothod on a struct the first argument is implicit(to clearly and directy expressed but heavily implied, readily apparent and understood or assumed to be true/as such by everyone) and ususally a reffernce to `self` where `self` is the struct. In this case, this is mutable refernce to self`&mut self` the ampersand `&` is probably the reference and `mut` is for mutable. The argument that needs to be passed in is n which is a `usize`  a number. It returns the `n`th element of the iterator which is wraped in an option `pub fn nth(&mut self, n: usize) -> Option<Self::Item>`
Here firstly we have the implicit argument which is a mutable refernce to self and the numbers `0` and `1` are the second argument which is the usize. Since this is an indexing operation `nth(0)` and `nth(1)` are 1st and 2nd element of the iterators:
Like most indexing operations, the count starts from zero, so `nth(0)` returns the first value, `nth(1)` the second, and so on. 
```definition
core::iter::traits::iterator::Iterator
pub fn nth(&mut self, n: usize) -> Option<Self::Item>
Returns the nth element of the iterator.
```
########we will get to this eventually
```accessing
use std::env::{args, Args};
fn main() {
	let args: Args = args();

	let first = args.nth(0);
    println!("{:?}", first);
}
```
This will lead to an error because of the first implicit argument which is a mutable reference to self `let args` which is `args.nth(0)`  so we will get an error saying that the `args` variable cannot be borrowed as mutable because variable here are not mutable by default unless they are declared as mutable `let mut args: Args = args();`.
```output
cargo run
   Compiling calculator v0.1.0 (/home/runner/mruining/calculator)
error[E0596]: cannot borrow `args` as mutable, as it is not declared as mutable
 --> calculator/src/main.rs:5:15
  |
5 |   let first = args.nth(0);
  |               ^^^^ cannot borrow as mutable
  |
help: consider changing this to be mutable
  |
4 |   let mut args: Args = args();
  |       +++

For more information about this error, try `rustc --explain E0596`.
error: could not compile `calculator` (bin "calculator") due to previous error
```
make these changes
```fix
use std::env::{args, Args};
fn main() {
	let mut args: Args = args();

	let first = args.nth(0);
    println!("{:?}", first);
}
```