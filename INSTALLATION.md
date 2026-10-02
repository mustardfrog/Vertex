# Installing Vertex

> **Note:** This document explains how to build Vertex from source.  
> If you don’t want to build it manually, you can use the pre-built binaries from the [Releases](https://github.com/DomioKing653/Vertex/releases/tag/v0.1.51-alpha).
> *(Note: binaries are currently available only for Linux.)*

---

## Dependencies

Before you start, make sure you have installed:

- Rust programming language toolchain
- Git
- Zig toolchain

---

## Installation

First, clone the repository and navigate into it:

```shell
git clone https://github.com/DomioKing653/Vertex
cd Vertex
```

---

## Compilation

Build the main project:

```bash
cargo build --release
```

Then build the codegen library:

```bash
cd src/runtime_lib
cargo build --lib --release
```

---

## Final Setup

#### Manual

### Setting PATH manually

After successful compilation, move the required binaries:

- `vertex` and `vertexC` from `./target/release/`
- `libvm_runtime.a` from `./src/codegen/target/release/`

Place them somewhere in your `PATH` environment variable.

Finally, set the `VERTEX_RUNTIME_PATH` environment variable to point to `libvm_runtime.a`.

#### Using script

You can also set those env variables using the script by runing:
``bash
source set_env_vertex.sh
``

### Setting PATH using script
In any shell, run:
```bash
source set_env_vertex.sh
```

---

## Done

Congratulations — Vertex has been successfully built from source!
