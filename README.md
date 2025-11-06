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