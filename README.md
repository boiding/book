# book
Support material for the boiding workshop. Read it [online][].

## Setup
This book is created with [mdBook][mdbook]. Execute the following command to
install it. 

```sh
cargo install mdbook
```

To build the book run

```sh
mdbook build
```

For more options see the [documentation][mdbook-docs] or run `mdbook --help`.

### pre-commit hook
In order to automatically build the book on each commit the `pre-commit.sh`
script is created. You can activate it with the following command.

```sh
ln -s pre-commit.sh .git/hooks/pre-commit
```

[mdbook]: https://github.com/azerupi/mdBook
[mdbook-docs]: http://azerupi.github.io/mdBook/
[online]: https://boiding.github.io/book/
