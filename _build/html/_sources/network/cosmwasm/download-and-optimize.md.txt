# Optimization

Before progressing, ensure you've completed the first steps. It's important to have either the Node.js REPL or the `wasmd` Go CLI pre-configured.



**Step 1: Obtaining and Compiling the Contract Code**

Get the [`cw-contracts`](https://github.com/InterWasm/cw-contracts) repository first. Then:

{% code overflow="wrap" %}
```plaintext
git clone https://github.com/InterWasm/cw-contracts
cd cw-contracts
git checkout main
cd contracts/nameservice
rustup default stable
cargo wasm
```
{% endcode %}

To trim it down, you can run:

```plaintext
RUSTFLAGS='-C link-arg=-s' cargo wasm
```

This command yields a much compact version, roughly 165kB in size. This file or another optimized version will eventually get uploaded to the blockchain.



**Step 2: Running Unit Tests**

Unit tests ensure the contract operates as expected:

```plaintext
RUST_BACKTRACE=1 cargo unit-test
```



**Step 3: Optimizing for Deployment**

The `rust-optimizer` is the tool for this task and it allows third parties to validate the legitimacy of the contract.

{% hint style="info" %}
The `rust-optimizer` requires Docker.
{% endhint %}

On Linux and Mac, execute:

{% code overflow="wrap" %}
```plaintext
docker run --rm -v "$(pwd)":/code \
  --mount type=volume,source="$(basename "$(pwd)")_cache",target=/code/target \
  --mount type=volume,source=registry_cache,target=/usr/local/cargo/registry \
  cosmwasm/rust-optimizer:0.12.11
```
{% endcode %}

For Windows:

{% code overflow="wrap" %}
```plaintext
docker run --rm -v ${pwd}:/code `
 --mount type=volume,source="$("$(Split-Path -Path $pwd -Leaf)")_cache",target=/code/target `
 --mount type=volume,source=registry_cache,target=/usr/local/cargo/registry `
 cosmwasm/rust-optimizer:0.12.11
```
{% endcode %}

After optimization, the resultant binary is located under the `artifacts` directory and will be approximately 138 kB in size.
