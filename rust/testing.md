## Testing in Rust

Rust offers us three separate ways to test our code:

- Embedded tests: Test effectively side-by-side with our functions
- External tests: Tests live together in a `tests` directory, mainly for integration tests
- Documentation tests: Tests found inside code blocks in documentation can be run as any other test.

The main difference is between embedded tests and external tests. Embedded tests are part of a project module, just like the rest of the code in the module. Therefore, they have access to structs, methods, fields and functions that may be private, which makes them good for testing functions which may not be easily exposed to the user. External tests have the same access as if you were to use your crate as a dependency. Therefore, these are mainly used for integration testing, since you are using the code in the same way a user would.
