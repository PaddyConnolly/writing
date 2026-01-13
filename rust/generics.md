## Generics

Rust implements generics using something called monomorphisation: for each concrete type (i.e. String, i32, u64) used with a generic function, the compliler generates a specialised version of the function at compile-time.

This means that Rust abstractions are zero-cost, i.e. you don't have to pay for more human-readable code with longer runtimes. So effectively, you write code that is easiest for you to understand, and the compiler converts it into efficient, type-specific machine code.
