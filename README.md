# CosmWasm Cheatsheet

This is a rough draft of a cheatsheet I'm working on for CosmWasm smart contract development.

### rust-optimizer

In order to deploy CW smart contracts, you will need to optimize production code using [rust-optimizer](link).

Note: You will need Docker installed in order to run `rust-optimizer`.

Navigate to the project root and run the following on OS X:
```
docker run --rm -v "$(pwd)":/code \
  --mount type=volume,source="$(basename "$(pwd)")_cache",target=/code/target \
  --mount type=volume,source=registry_cache,target=/usr/local/cargo/registry \
  cosmwasm/rust-optimizer:0.12.6
```

Or the following on Windows:
```
docker run --rm -v ${pwd}:/code `
 --mount type=volume,source="$("$(Split-Path -Path $pwd -Leaf)")_cache",target=/code/target `
 --mount type=volume,source=registry_cache,target=/usr/local/cargo/registry `
 cosmwasm/rust-optimizer:0.12.6
 ```

 The binary will be under the folder `artifacts`.
