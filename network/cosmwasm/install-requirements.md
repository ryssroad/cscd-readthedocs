# Install Requirements

**Step 1: Setting Up Your Development Environment**

**Install Golang**

Required for `wasmd`. Install Go from its [official documentation](https://github.com/golang/go/wiki#working-with-go). Ensure you have Go version v1.18+.

**Install Rust**

`rustup` is used to manage dependencies and seamlessly switch between different versions of `cargo` and `rustc`, both crucial for Rust development.\




**Step 2:  Installing Rust (for Linux & Mac):**

Begin with `rustup` installation.

Set up wasm32 target with the following commands:

{% code overflow="wrap" %}
```
rustup default stable
cargo version
rustup update stable
rustup target add wasm32-unknown-unknown
```
{% endcode %}



**Installing Rust (for Windows 10):**

Obtain `rustup-init.exe` from rustup.rs or rust-lang.org.

If needed, download [Visual C++ Build Tools 2019](https://visualstudio.microsoft.com/visual-cpp-build-tools/). Ensure "Windows 10 SDK" and ''English language pack'' are selected.

Run the setup for Rust and then install the wasm32 target similarly to the Linux & Mac setup.



**Step 3: Install `wasmd`**

{% code overflow="wrap" %}
```
git clone https://github.com/CosmWasm/wasmd.git
cd wasmd
git fetch --tags
git checkout v0.27.0  # Replace with stable version if needed.
make install
```
{% endcode %}



**Step 4: Install the Command-Line Tools:**

```
apt install jq curl
```



**Step 5: Choose your IDE**

An Integrated Development Environment (IDE) is needed. Here are two options:



**VSCode:** Equipped with Rust Language Server (RLS) capabilities. Combine it with the rust-analyzer extension for optimal Rust code support.

**IntelliJ IDEA Community Edition:** Comes with the IntelliJ Rust plugin, providing swift inline language feature support. Particularly useful for developers familiar with IntelliJ products.



#### **Step 6: Enhance Development**

A toolset to boost the lifespan of CosmWasm smart contracts. It consists of three repositories:



[**CosmWasm Gitpod**](https://github.com/oraichain/cosmwasm-gitpod)

Provides a ready-to-use development environment, integrating Rust, VS Code browser, crucial extensions, and Keplr wallet compatibility.



[**CosmWasm IDE extension**](https://github.com/oraichain/cw-vscode)

A VS Code extension simplifying the building & deployment of CosmWasm smart contracts.



[**CosmWasm IDE extension webview**](https://github.com/oraichain/cw-ide-webview)

A React application facilitating Keplr wallet interactions and enabling custom network additions.
