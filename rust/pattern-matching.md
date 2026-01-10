## Pattern Matching

### Background

Since starting out my journey with Rust, I think my favourite feature I've found so far is the pattern matching. I did a small module at university using Haskell, and Rust's pattern matching feels very similar to me, which was surprising in a language I was expecting to be far closer to C than Haskell. I think the reason I like it so much is that it makes me consider all the possible paths my program can take. Rust's `match` in combination with its `enum` system makes it very easy to manage different states in your program.

### Examples

```
enum Type {
    SimpleString(String),
    Error(String),
    Integer(i64),
    BulkString(Option<String>),
    Array(Vec<RespType>),
}

match type_char {
    '+' => parse_simple_string(),
    '-' => parse_error(),
    ':' => parse_integer(),
    '$' => parse_bulk_string(),
    '*' => parse_array(),
    _ => Err(ParseError::UnknownType),
}
```


For example, the RESP parser in my Redis clone was very easy to implement with pattern matching. First, you define an `enum` which makes you think about which RESP types you want to encounter, and which types you want to ignore, and then you match against the type indicator char. Of course, the compiler won't build your program until you make sure to handle each possible branch your program can take.

### Errors

Rust's pattern matching is also a useful tool for error handling, which I'll talk about more in [errors.md](https://github.com/PaddyConnolly/writing/rust/errors.md).
