## Error Handling in Rust

### Background

One thing I've definitely noticed while learning Rust is that I really had no idea how error types worked before this, and it felt really frustrating trying to parse errors. For example, when building my HTTP server, I would try and return an error, should I use `std::error::Error` or `thiserror::Error` or `anyhow::Error` or `rusqlite::Error`? This was a big upgrade from my previous approach of print statements saying "Something went wrong :(", or raising generic exceptions.

However, as I've progressed with my projects, I keep encountering different tools that Rust gives you to help you handle Options and Errors – pattern matching, custom crates, and even implementing your own errors.

### Options and Results

Rust provides two enums which help you to implement intended behaviour when dealing with values which are uncertain at compile time. The first, `Option`, is found in languages which I've used before, they simply indicate a variable could have a value, or it could not (usually indicated with None, Nil or Null - Rust uses `None``). These are useful for avoiding errors, as in order to use the value, you also have to decide what should happen if you don't get a value.

The second enum is a Result, which wasn't anything that I had encountered before. It seems similar to an Option at first, and a lot of my early struggles were down to confusing the two. A Result means you could have a value, or you could have an Error. A Result is an enum with two branches: `Ok()` and `Err()`. This makes it easy to pattern match and decide what your program should do depending on the value it gets.

But this does also bring problems - mainly that if you have to decide what to do if you don't get a value every time you are unsure - it means you have to write a lot of error/none checking code. Rust has some ways we can make our error handling much more concise.

### The `?` Operator

After realising how many Options I had to handle writing a simple HTTP server, I went looking for ways to make my code more concise, and found the `?` operator. My first thought was that it would be bad practice, as it felt like I was ignoring errors, which could lead to much larger problems down the line. While this is possible, the `?` operator's real strength is that it lets you decide where and when you decide to handle your errors. For example, if I read a line from a buffer, strip off the newline,  and drop the first char, do I want to check for None's at each stage? Or do I want to do it once at the end before I run my output through the parser? This operator allows us to delay the check until we really need it – if we want to handle a missing value in the main parser, we can use `?`s in all of the helper methods, so that they either run as intended, or return early and allow us to handle the error in our main parsing function.
