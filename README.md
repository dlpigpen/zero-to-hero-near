# Rust Smart Contract Template

## Getting started

To get started with this template:

1. Test the contract 

    `cargo test -- --nocapture`

2. Build the contract

    `RUSTFLAGS='-C link-arg=-s' cargo build --target wasm32-unknown-unknown --release`

**Get more info at:**

* [Rust Smart Contract Quick Start](https://docs.near.org/docs/develop/contracts/rust/intro)
* [Rust SDK Book](https://www.near-sdk.io/)



# Build (for Windows it's build.bat)
./build.sh

# Create fresh account if you wish, which is good practice
near delete crossword.mitsori1.testnet mitsori1.testnet
near create-account crossword.mitsori1.testnet --masterAccount mitsori1.testnet

# Deploy
near deploy crossword.mitsori1.testnet --wasmFile res/my_crossword.wasm

# Call the "new" method
near call crossword.mitsori1.testnet new '{"solution": "69c2feb084439956193f4c21936025f14a5a5a78979d67ae34762e18a7206a0f"}' --accountId crossword.mitsori1.testnet



# Create fresh account if you wish, which is good practice
near delete crossword.mitsori1.testnet mitsori1.testnet
near create-account crossword.mitsori1.testnet --masterAccount mitsori1.testnet

# Deploy
near deploy crossword.mitsori1.testnet --wasmFile res/my_crossword.wasm \
  --initFunction 'new' \
  --initArgs '{"solution": "69c2feb084439956193f4c21936025f14a5a5a78979d67ae34762e18a7206a0f"}'
  
  
near view crossword.mitsori1.testnet get_solution
near state crossword.mitsori1.testnet