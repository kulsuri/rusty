# rusty
Projects to get familiar with the Rust programming language

# Installation
Install rustup via brew:
```sh
brew install rustup
```
Install Rust:
```sh
rustup install stable
```
Check Rust is up to date:
```sh
rustup update
```
Cargo: the Rust build tool and package manager
- build project with cargo build
- run project with cargo run
- test project with cargo test
- build documentation for project with cargo doc
- publish library to crates.io with cargo publish
To test that you have Rust and Cargo installed, you can run this in your terminal of choice:
```sh
cargo --version
```

# Generating a new Rust project
```sh
cd 1_generate_new_project # navigate to the directory where you want to create your project
cargo new hello-rust
```
This will generate a new directory called hello-rust with the following files:
```
hello-rust
|- Cargo.toml
|- src
  |- main.rs
```
Cargo.toml is the manifest file for Rust. It’s where you keep metadata for your project, as well as dependencies.

src/main.rs is where we’ll write our application code.

To run the project, navigate into the project directory and use cargo run:
```sh
cd hello-rust
cargo run
```
This will compile and run the project, printing `Hello, world!` to the terminal.

# Adding dependencies
Libraries can be found on crates.io, the package registry for Rust. In Rust, packages are called “crates.”

In this project, we’ll use a crate called ferris-says by running:
```sh
cargo add ferris-says
```
A dependency will be added to our Cargo.toml file automatically.
```
[dependencies]
ferris-says = "0.3.2"
```
Alternatively, you can manually add the dependency to Cargo.toml and then run `cargo build` to download and compile the dependency. The `Cargo.lock` file will be created to keep track of the exact versions of dependencies used in the project.

We can use the `ferris-says` crate in our `src/main.rs` file. This line means that we can now use the `say` function that the `ferris-says` crate exports for us.
```rust
use ferris_says::say;
```

# A simple Rust program
Here’s a simple Rust program that uses the ferris-says crate to print a message:

[OPTIONAL]
```sh
cd 2_simple_rust_program_with_dep
cargo new hello-ferris
cd hello-ferris
cargo add ferris-says
```
In the `src/main.rs` file, replace the contents with the following code:
```rust
use ferris_says::say; // from the previous step
use std::io::{stdout, BufWriter};

fn main() {
    let stdout = stdout();
    let message = String::from("Hello fellow Rustaceans!");
    let width = message.chars().count();

    let mut writer = BufWriter::new(stdout.lock());
    say(&message, width, &mut writer).unwrap();
}
```
To run the program, use:
```sh
cargo run
```
This will compile and run the program, printing a message from Ferris, the Rustacean mascot, to the terminal.
```
 __________________________
< Hello fellow Rustaceans! >
 --------------------------
        \
         \
            _~^~^~_
        \) /  o o  \ (/
          '_   -   _'
          / '-----' \
```