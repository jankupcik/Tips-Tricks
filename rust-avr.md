Visual Studio Code + WSL
========================

- In WSL create a symlink:
  ```
  ~/<ProjectName> -> /mnt/c/Users/Honza/Programming/<ProjectName>/
  ```

- Open `<ProjectName>` folder in VSCode


AVR targets/specifications
==========================

<https://github.com/Rahix/avr-hal-template/tree/main/avr-specs>


Compilation
===========

Prerequisites 
-------------

- A version of the nightly Rust compiler. Can be checked by `rustc -V` and must 
    return "-nightly", e.g. `rustc 1.85.0-nightly (8dc83770f 2024-12-06)`

- The rust-src rustup component. 
    If missing, install using `rustup component add rust-src`

- AVR-GCC on the system for linking

- AVR-Libc on the system for support libraries


Compilation
-----------

    rustup override set nightly   <-- this is really required
    cargo build --release


AVR in Rust
===========

Library to access registers
---------------------------

- <https://crates.io/crates/avr-device>
- [Example of panic function](https://github.com/Rahix/avr-device/blob/main/examples/atmega328p/src/main.rs)


Interrupts
----------

- [Výborný článek o přerušení](https://blog.rahix.de/005-avr-hal-millis/)
- <https://docs.rs/critical-section/latest/critical_section/>
- <https://docs.rs/avr-device/latest/avr_device/interrupt/>
