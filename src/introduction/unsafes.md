Unsafes
=======

`unsafe` is a way to tell Rust that "I know what I'm doing!", which is often necessary when writing low-level code, providing safe abstractions. You cannot write a kernel without `unsafe`s.

In that light, a kernel cannot be 100% safe, however the unsafe parts have to be marked with an `unsafe`, which keeps the unsafe parts segregated from the safe code. We seek to eliminate the `unsafe`s where we can, and when we use `unsafe`s, we are extremely careful.

A quick grep gives us some stats: The kernel has 16.52% unsafe code, a 50% improvement in the last three weeks. User space has roughly ~0.2%.

This contrasts with kernels written in C, which cannot make guarantees about safety without costly formal analysis.

You can find out more about how `unsafe` works in the [relevant section of the Rust book](https://doc.rust-lang.org/book/unsafe.html).
