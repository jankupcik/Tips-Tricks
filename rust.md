- Versions

  - global
    ```
    rustup install <toolchain>
    rustup default <toolchain>

    <toolchain> = stable/beta/nighly
    ```

  - local
    ```
    rustup override set version
    ```
    
  - to test on 1.20:
    ```
    rustup run stable-1.20 <test commands>
    ```
    
- List of supported targets with installed ones
  ```
  rustup target list
  ```
  
  - filter to only installed only
    ```
    rustup target list --installed
    ```
    
- New project
  ```
  cargo new <project name>
  ```
  
- Generate documentation
  ```rust
  /// This is a documentation for something() function.
  /// It needs three slashes.
  ///
  /// # Examples
  /// 
  /// ```rust
  /// println!("Full support of markdown in doc");
  /// ```
  pub fn something() {}
  ```

  ```
  cargo doc --open
  ```

Enumerations
============
```rust
enum State {
    Stop,
    Go
}
```
```rust
fn ...(state: State) {
    match state {
        State::Stop => ...,
        State::Go => ...,
   }
}
```
-or-
```rust
fn ...(state: State) {
    use self::State::*;
    match state {
        Stop => ...,
        Go => ...,
   }
}
```

Traits
======

Built-In Traits
---------------
- `Eq`, `PartialEq` allows values to be compared
- `Ord`, `PartialOrd` allows values to be put in the order

   Note: `partialX` = sometimes, for some instances of the type, the equality/order is not possibly to determine, e.g.:
  
    - `i32`: x == x always
    - `f32`, `f64`: x == x if not NaN, NaN != NaN
 
- `Display` - allows formatting with the default formatter, fit for users to read
  ```rust
  println!("{}", display);
  ```    
- `Debug` - similar to `Display` but is only for debugging, often not very pretty
  ```rust
  println!("{:?}", debug);
  println!("{:#?}", debug); // prettier
  ```

- `Clone` - allows a value to be explicitly cloned
  ```rust
  let a = foo();
  let b = a.clone()
  ```
- `Copy` - compiler may do the copy automatically
  
  For simple types likes integers, floating-point numbers, characters, it means that the code using their values doesn't have to worry about ownership and borrowing, it can always create a copy.

- `Iterator` - enables:
  ```rust
  for element in implementingIterator {}
  ```
