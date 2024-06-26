# ZKWasm Example

An example of using ZKWasm to do some operations.

## Installation

1. Install clang.

```bash
brew install llvm
```
2. Install zkwasm.
```bash
git clone --recurse-submodules https://github.com/DelphinusLab/zkwasm
git submodule init
cargo build
```
3. Use clang to build your C file.
```bash
clang --target=wasm32 --no-standard-libraries -Wl,--export-all -Wl,--no-entry -Wl,--allow-undefined -o stringlen.wasm stringlen.c
```

## Creating Proofs
```bash
sudo RUST_BACKTRACE=1 cargo run --release -- --host default --function zkmain --wasm ../stringlen.wasm single-prove --public 11:i64
```

## Verifying Proofs
```bash
sudo RUST_BACKTRACE=1 cargo run --release -- --host default --function zkmain --wasm ../stringlen.wasm single-verify
```

## License

MIT License.

## Contact

Your Name - [@argfoo-web3](https://github.com/argfoo-web3)