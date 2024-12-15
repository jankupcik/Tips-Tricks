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
