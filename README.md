## **Rust language research**

<img src="https://i.imgur.com/d7Hv99h.png" >

#

### Used VSCode Extensions

- Rust
- Crates
- Better TOML

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
