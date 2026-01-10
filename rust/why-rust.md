## Why I started learning Rust

Before I started learning Rust, I effectively knew nothing about it – except that 1. People love Rust and 2. People thought Rust would replace C. Now I did learn C at university, but never really used it subsequently, but I could see why people could get excited about a new C replacement. I also found out before starting my journey that people really like Rust for its approach to multi-threading. This was also something I was interested in learning more about since every multi-threaded project I did at university felt very clunky, and I never really knew much about what was going on.

I decided on two projects to give myself an introduction to Rust, the first a simple HTTP server and client, something which I knew how to implement, in order to get a grasp of the syntax and style. The second a Redis clone, as I wanted a system design concept which I could learn more about (i.e. Key-Value stores) and an excuse to use multi-threading.

One thing I'm really enjoying about Rust right now is that using Rust alongside the `rust-analyzer` LSP, I almost always catch errors before I build and run. In Python for example, I often find that I get stuck in a cycle of run-wait-fix, while Rust's compiler is so strict that when I see no errors in my file, I run it and have a good chance that my code works perfectly.
