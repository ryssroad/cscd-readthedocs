# Create a WASM File

**Step 1: Access the Contract Code**

Whether you've authored the code or acquired it from another source, having access to the smart contract code is essential.



**Step 2: Identify the Folder Structure**

A typical smart contract will resemble the structure below:

```
cw-contract/
├── .cargo/
│   └── config 
├── .circleci/
│   └── config.yml 
├── .github/workflows/
│   └── Basic.yml 
├── examples/
│   └── schema.rs 
├── schema/ 
├── src/ 
│   ├── state.rs 
│   ├── contract.rs  
│   ├── lib.rs  
│   ├── msg.rs  
│   └── error.rs 
└── target/ 
```



**Step 3: Create the WASM File**

Unoptimized Version: Use the command `cargo wasm`.

Optimized Version: If you have Docker installed, utilize the following:

{% code overflow="wrap" %}
```
docker run --rm -v "$(pwd)":/code \
--mount type=volume,source="$(basename "$(pwd)")_cache",target=/code/target \
--mount type=volume,source=registry_cache,target=/usr/local/cargo/registry \
cosmwasm/rust-optimizer:0.12.6
```
{% endcode %}

Ensure the command is run from the root directory of the folder.

{% hint style="info" %}
WASM files that aren't optimized can become excessively large. This can lead to potential deployment issues on Cascadia or incur elevated gas fees. Whenever feasible, aim for an optimized WASM file.
{% endhint %}



**Step 4: Upload the WASM File**

Navigate to the Contract Upload section on Cascadia.

Select your generated WASM file.

Click on the "Upload Contract" button.
