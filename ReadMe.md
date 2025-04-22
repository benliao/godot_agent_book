# Godot Agent Book

> [!Tip]
> This book use [github-godot-rust-book] as a template.
> This book is deployed **[godot-agent.github.io/book][book-web]**

## Local setup

The book is built with [mdBook] and the plugins [mdbook-toc] and [mdbook-admonish]. To install them and build the book locally, you can run:

```bash
cargo install mdbook mdbook-toc mdbook-admonish
mdbook build
```

To run a local server with automatic updates while editing the book, use:

```bash
mdbook serve --open
```

[book-web]: https://godot-agent.github.io/book
[mdbook-admonish]: https://github.com/tommilligan/mdbook-admonish
[mdbook-toc]: https://github.com/badboy/mdbook-toc
[mdBook]: https://github.com/rust-lang-nursery/mdBook
[github-godot-rust-book]: https://github.com/godot-rust/book/