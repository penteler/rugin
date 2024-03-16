error
```mruining/calculator$ cargo run
   Compiling calculator v0.1.0 (/home/runner/mruining/calculator)
warning: unused import: `Args`
 --> calculator/src/main.rs:1:22
  |
1 | use std::env::{args, Args};
  |                      ^^^^
  |
  = note: `#[warn(unused_imports)]` on by default

error[E0277]: `Args` doesn't implement `std::fmt::Display`
 --> calculator/src/main.rs:5:20
  |
5 |     println!("{}", args);
  |                    ^^^^ `Args` cannot be formatted with the default formatter
  |
  = help: the trait `std::fmt::Display` is not implemented for `Args`
  = note: in format strings you may be able to use `{:?}` (or {:#?} for pretty-print) instead
  = note: this error originates in the macro `$crate::format_args_nl` which comes from the expansion of the macro `println` (in Nightly builds, run with -Z macro-backtrace for more info)

For more information about this error, try `rustc --explain E0277`.
warning: `calculator` (bin "calculator") generated 1 warning
error: could not compile `calculator` (bin "calculator") due to previous error; 1 warning emitted
```
the other output
There is also a warning about the unused  `Args`  import
```Compiling calculator v0.1.0 (/home/runner/mruining/calculator)
warning: unused import: `Args`
 --> calculator/src/main.rs:1:22
  |
1 | use std::env::{args, Args};
  |                      ^^^^
  |
  = note: `#[warn(unused_imports)]` on by default

warning: `calculator` (bin "calculator") generated 1 warning (run `cargo fix --bin "calculator"` to apply 1 suggestion)
    Finished dev [unoptimized + debuginfo] target(s) in 4.12s
     Running `/home/runner/mruining/target/debug/calculator`
Args { inner: ["/home/runner/mruining/target/debug/calculator"] }
```
