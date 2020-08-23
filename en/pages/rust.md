# Rust

## ctags
[Universal Ctags](https://github.com/universal-ctags/ctags) is ctags with rust support
```bash
sudo apt update && sudo apt install gcc make pkg-config autoconf automake python3-docutils libseccomp-dev libjansson-dev libyaml-dev libxml2-dev
cd $(mktemp -d /tmp/universal-ctags-XXXXXXXXX)
git clone https://github.com/universal-ctags/ctags
cd ctags
./autogen.sh
./configure
sudo make && sudo make install
```

## Tools Crates
- [Cargo Bloat](https://github.com/RazrFalcon/cargo-bloat) Find out what takes most of the space in your executable.
- [Cargo LLVM Lines](https://github.com/dtolnay/cargo-llvm-lines) Count the number of lines of LLVM IR across all instantiations of a generic function.
- [Just](https://github.com/casey/just) Simple  `make` without build-system. `just` is a handy way to save and run project-specific commands.
- [Cargo make](https://github.com/sagiegurari/cargo-make) Rust task runner and build tool.

## Crates
- [Rustyline](https://crates.io/crates/rustyline/) Readline implementation in Rust. Use arrows, backspace, etc when reading stdin
- [Clap](https://github.com/clap-rs/clap) Argument Parsing
- [Colored](https://github.com/mackwic/colored) Coloring terminal so simple
- [reqwest](https://github.com/seanmonstar/reqwest) Batteries included HTTP Client
- [scraper](https://github.com/causal-agent/scraper) HTML parsing and querying with CSS selectors
- [serde](https://github.com/serde-rs/serde) Serde is a framework for serializing and deserializing Rust data structures efficiently and generically
- [serde_json](https://github.com/serde-rs/json) Serde JSON serialization file format
- [regex](https://github.com/rust-lang/regex) Regex for Rust
- [lazy_static](https://github.com/rust-lang-nursery/lazy-static.rs) A macro for declaring lazily evaluated statics in Rust
- [dirs](https://github.com/dirs-dev/dirs-rs) Cross-platform library. Provides platform-specific, user-accessible locations
- [chrono](https://github.com/chronotope/chrono) Date and Time for Rust

## Concurrency Crates
- [tokio](https://github.com/tokio-rs/tokio) event-driven, non-blocking I/O platform for **async** Rust futures
- [crossbeam](https://github.com/crossbeam-rs/crossbeam) Is a crate that provides a tool set for concurrent programming
- [rayon](https://github.com/rayon-rs/rayon) data-parallelism. (Work stealer). **Convert squential iterators into parallel ones**
- [threadpool](https://github.com/rust-threadpool/rust-threadpool) A thread pool for running a number of jobs on a fixed set of worker threads
- [parking_lot](https://github.com/Amanieu/parking_lot) Faster thread-safe *primitives*: `Mutex`, `RwLock`, `Once`, etc

## Code samples
- [C# LINQ a-alike samples](https://gist.github.com/leonardo-m/6e9315a57fe9caa893472c2935e9d589)

## Frameworks
- [Amethyst](https://github.com/amethyst/amethyst) data-driven and data-oriented game engine. Using an (Entity Component System) ECS Model
