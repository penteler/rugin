a function is delared using the `fn` keyword with the handle main `main()` this a call to the printline macro `println!()` the exclaim denotes the macro here and is apararently also called the "bang/bane symbol"
```by default
fn main() {
    println!("Hello, world!");
}
```
The rust standard library comes with an EMV module which in his words "allows access to the command line arguments passed when calling the program". For this project we will need these exports: the args function and the Args struct. "the args function returns an instance of the Args struct". It will be imported into the file scope as such with the use keyword followed by stadard(std- I'm assuming this refers to the standard library) seperated by a space followed by two colons followed by the module name 'env', 2 colons(::),name of the function 'args' and the name of the struct 'Args' in curly braces seperated by a comma(and of cource a semiconon at the end.
Then we'll declare a new variable "args" using the 'let' keyword. We can "assign the value of the return of calling the function args" - so whatever the args function call returns will be assigned as the value of the variable args.
Underneath this we can use the println!(print line macro) to print the value of the args variable so basically this should show us what this- args(); (the args function call) returns. Instead of Hello, World! we place curly braces as a string and this will be the first argument and then we will pass the variable because we want it to go in the cury brackets. For some reason we can't just place it in the curly braces. Now run this by typing in "cargo run" in the shell to get an error. This happens because the trait display `std::fmt::Display` is not implemented for `Args` Here `fmt` might bet the module and `Display` might be a trait
```args
use std::env::{args, Args};
fn main() {
	let args = args();
    println!("{}", args);
}
```
fix this by making these changes `?#` (pretty print) might also work:
```changes
use std::env::{args, Args};
fn main() {
	let args = args();
    println!("{:?}", args);
}
```
This is how the Args struct is printed:
```output
Args { inner: ["/home/runner/mruining/target/debug/calculator"] }
```
it contains an inner field and the path to the binary