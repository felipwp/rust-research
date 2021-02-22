## **Rust language research**

<img src="https://i.imgur.com/d7Hv99h.png" >

#

### Used VSCode Extensions

- Rust
- Crates
- Better TOML

#

### **MUTABILITY**

- Once a value is assigned to a variable, it can never be changed (unless you explicitly tell the compiler to make it mutable);

```rs
 let example = 0; // regular variable
 example = 1 + 2; // ❌ will throw an error

 let mut mutable_example = 0; // mutable variable
 mutable_example = 1 + 2; // ✅ works just fine
```

#

### **MACROS**

- A macro is code that writes other code, this is known as metaprogramming;
- It is called just like a function, but it has an exclamation point in the end;
- Different from functions, you don't have to assign neither a type nor the quantity of parameters when using a macro;
- You pass any kind of variable, be it a function, a string or a float;
- Example:

```rs
  fn main() {
    println!("This is a {}, {}", "test", 123 )
    // output: "This is a test 123"
  }
```

- You can check the generated code using a crate called <a href="https://crates.io/crates/cargo-expand">cargo-expand</a>, the example above will return something like this:

```rs
fn main() {
    {
        ::std::io::_print(::core::fmt::Arguments::new_v1(
            &["This is a ", " ", " ", "\n"],
            &match (&"Rust", &"Macro", &"Test") {
                (arg0, arg1, arg2) => [
                    ::core::fmt::ArgumentV1::new(arg0, ::core::fmt::Display::fmt),
                    ::core::fmt::ArgumentV1::new(arg1, ::core::fmt::Display::fmt),
                    ::core::fmt::ArgumentV1::new(arg2, ::core::fmt::Display::fmt),
                ],
            },
        ));
    }
}
```

#

### **FUNCTIONS**

- The "main" function is always the first thing to run in a Rust executable;
- Snakecase naming (lowercase with underscores);
- Passing arguments example: `fn calculate(value: f32)`;
- You also need to specify the return type, for example, if you want to return a float: `fn calculate(value: f32) -> f32`;
- You can also return values by not adding a semicolon in the last expression of the function;

#

### **MEMORY ALLOCATION CONCEPTS**:

### Stack

- The size of every variable has to be known at compile time (cannot change dinamically);
- When a function exits it's stack, the frame is released, deallocating the memory **automatically**;
- Stores variables created by each function in memory;
- A new "stack frame" is created for every function call, being allocated on top of the current one;
- Size is restricted.

### Heap

- The memory is managed manually (using pointers);
- Failing to release memory allocated heaps leads to memory leaks;
- No size restrictions, can allocate huge amounts of data, it is only limited by the physical resources of the system;
- Can be accessed globally, anywhere, anytime;
- Shold be avoided when possible, if a program allocates and deallocates a lot of blocks on the heap, eventually, the heap will be fragmented, making it harded to find the allocated data.

#

### **TYPES**:

- Usize or Isize

  - Architecture dependant types, either 32 or 64 bits;
  - On a 32 bits architecture, it will be 4 bytes and on a 64 bits it will be 8 bytes;

- Integer
  - A "u" at the start means it's an unsined variable;
  - A "i" at the start means it's a signed variable;
  - The number that comes after the letter represents the size of the variable in bits, it can go from 8 to 128.
- Float
  - f32 and f64, the number means the same as in the Integer type;
- Boolean
  - bool - 1 byte in size;
- Character
  - char - always 4 bytes in size, holds a single unicode character

#
