To access arguments within the `Args` struct within the `let agrs: Args` variable we can use the nth method which exists on the `Args`. We're gonna declare new variables. First one is `first` and it will be assigned the value of calling the `nth` method `args.nth()` on args. hovering over the method in the replit ide will show more info:
```this method takes 1 argument but 0 arguments were supplied
Debug
rustc
core::iter::traits::iterator::Iterator
pub fn nth(&mut self, n: usize) -> Option<Self::Item>
Returns the nth element of the iterator.

Like most indexing operations, the count starts from zero, so nth(0) returns the first value, nth(1) the second, and so on.

Note that all preceding elements, as well as the returned element, will be consumed from the iterator. That means that the preceding elements will be discarded, and also that calling nth(0) multiple times on the same iterator will return different elements.

nth() will return None if n is greater than or equal to the length of the iterator.

Examples
Basic usage:

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
in the function definition we can see that it takes in two arguments`pub fn nth(&mut self, n: usize)` being a mothod on a struct the first argument is implicit(to clearly and directy expressed but heavily implied, readily apparent and understood or assumed to be true/as such by everyone)
```accessing
use std::env::{args, Args};
fn main() {
	let args: Args =  args();
	let first = args.nth
	println!("{:?}");
}
```