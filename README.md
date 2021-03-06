# Git Interactive Rebase Tool

Full feature terminal based sequence editor for git interactive rebase. Written in Rust using ncurses.

![Image](git-interactive-tool.gif?raw=true)

## Install

#### Debian and derivatives

Download the `.deb` file from the releases page and install. The executable will be installed to `/usr/bin`.

#### MacOS and OSX

Download the `interactive-rebase-tool` from the releases page and copy it to a location on your `PATH`.

### Configure Git

In your command line run:

    git config --global sequence.editor interactive-rebase-tool

## Usage

```shell
interactive-rebase-tool --version | -v | <rebase-todo-filepath>
```

### Getting Help

The tool has built in help that can be accessed by hitting the `?` key.

### Key Bindings

| Key          | Description |
| ------------ | ----------- |
|  Up          | Move selection up |
|  Down        | Move selection down |
|  Page Up     | Move selection up five lines |
|  Page Down   | Move selection down five lines |
|  `q`         | Abort interactive rebase |
|  `Q`         | Immediately abort interactive rebase |
|  `w`         | Write interactive rebase file |
|  `W`         | Immediately write interactive rebase file |
|  `?`         | Show help |
|  `c`         | Show commit information |
|  `j`         | Move selected commit down |
|  `k`         | Move selected commit up |
|  `p`         | Set selected commit to be picked |
|  `r`         | Set selected commit to be reworded |
|  `e`         | Set selected commit to be edited |
|  `s`         | Set selected commit to be squashed |
|  `f`         | Set selected commit to be fixed-up |
|  `d`         | Set selected commit to be dropped |


## Development

### Install Rust

To start developing the project you will need to [install Rust](https://doc.rust-lang.org/book/getting-started.html),
which can generally be done using [rustup](https://www.rustup.rs/).

### Setup

#### Debian and derivatives

You will need `build-essential` and `libncurses5-dev` to build the project.
Additionally you will need `pkg-config` and `liblzma-dev` if you wish to build
a release. They can be installed using `apt-get`:

    sudo apt-get install build-essential libncurses5-dev
    sudo apt-get install pkg-config liblzma-dev


### Build and run

Use cargo to build and run the project. From the project project root run:

    # only build
    cargo build --release
    # build and run
    cargo run <path-to-git-rebase-todo-file>


### Release

##### Install Cargo Deb

Cargo Deb has not been released to creates.io so it will need to be installed from the GitHub repository.

    cargo install --git https://github.com/mmstick/cargo-deb


##### Building

    cargo build --release
    cargo deb

A deb file will be written to `target/debian/git-interactive-rebase-tool_*.deb`.

## License

Git Interactive Rebase Tool is released under the ISC license. See [LICENSE](LICENSE).
