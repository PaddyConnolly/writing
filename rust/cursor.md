## The Cursor Type

The `Cursor` type in Rust gives us a lot of help when dealing with buffers. It implements the traits `Read`, `Write` and `Seek`, which means get lots of tools which make working with buffers so much easier.

Firstly, it provides some abstraction from the underlying type, we can work with in-memory buffers using the same I/O tools as we would for files. Secondly, if we just used indices with arrays, there's nothing stopping us from reading the current value, and forgetting to increment our index. Rust's `Cursor` doesn't let us do this – reads and writes are performed through the respective traits, which automatically update the underlying index. It is still possible for us to access the underlying buffer using indices if we want to, but the intended way is to use the `Cursor` type to help us avoid these little bugs which could creep in.

The `Seek` trait allows us to control the `Cursor`'s position, we can move the position relative to the start or end of the buffer, as well as the current position. This can be useful working with data with offsets or headers -> think packets or similar.
