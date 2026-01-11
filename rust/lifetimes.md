## Lifetimes in Rust

### Background

Lifetimes are one of the many features of Rust which I had no idea about when starting out. In Rust, a lifetime tells the compiler how long a reference is guaranteed to be valid. Most of the time, the compiler can work it out, e.g. if you declare a variable at the start of a simple function, it should be a valid reference until the function returns. However, consider the scenario where a function returns the larger of two values, `a` and `b`. At compile time, we don't know which value the output references. We can solve this with *lifetime annotations*, we tell the compiler that the output reference is only valid as long as both of the inputs are still valid. Then, the compiler enforces that we never use the output reference outside of its valid lifetime.


### Lifetime Annotations

When the compiler needs our help to work out a reference's lifetime, we need to annotate the variable with a lifetime parameter. When writing functions with lifetime annotations, they go in between the function name and the parameters, as below:

```fn max<'a>(x: &'a i32, y: &'a i32) -> &'a i32 {x}```

I like that it reads similarly to normal English e.g. Define a `function` called `max` with two lifetime parameters `a` and `b` – and parameter `x` is a reference with lifetime `'a` to an `i32`
