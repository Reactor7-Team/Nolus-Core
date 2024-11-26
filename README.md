# Nolus-Core

## **Prerequisites**

Ensure the following software and tools are installed on your system:

1. **Git**  
   Install Git for cloning the repository.  
   ```bash
   sudo apt update && sudo apt install -y git
   ```

2. **Rust and Cargo**  
   Install Rust using `rustup`.  
   ```bash
   curl --proto '=https' --tlsv1.2 -sSf https://sh.rustup.rs | sh
   source $HOME/.cargo/env
   rustup update
   ```

3. **Build Essentials**  
   Install build tools (for Linux-based systems):  
   ```bash
   sudo apt install -y build-essential libssl-dev pkg-config
   ```

4. **Node.js and Yarn (optional)**  
   Required if the project involves a web-based component.  
   ```bash
   curl -sL https://deb.nodesource.com/setup_16.x | sudo -E bash -
   sudo apt install -y nodejs
   npm install --global yarn
   ```

---

## **Cloning the Repository**

Clone the Nolus Core repository from GitHub:

```bash
git clone https://github.com/nolus-protocol/nolus-core.git
cd nolus-core
```

---

## **Building the Project**

1. **Check the Rust Toolchain**  
   Ensure you have the correct version of Rust (check the repository's `README.md` for version requirements).  
   ```bash
   rustup show
   ```

2. **Compile the Project**  
   Run the following command to build the binary:  
   ```bash
   cargo build --release
   ```

   The compiled binary will be located in the `target/release` directory.

---

## **Running Nolus Core**

1. **Initialize the Node**  
   Before running the node, initialize its configuration and data directories:  
   ```bash
   ./target/release/nolus-core init <moniker-name>
   ```

2. **Configure the Node**  
   Modify the configuration files located in `~/.nolus/config/`.  
   - **`config.toml`**: Adjust network, P2P, and RPC settings.  
   - **`genesis.json`**: Ensure you are using the correct genesis file for the network.

   Example: To join a testnet, download the genesis file:  
   ```bash
   wget -O ~/.nolus/config/genesis.json <testnet-genesis-url>
   ```

3. **Start the Node**  
   Run the node with:  
   ```bash
   ./target/release/nolus-core start
   ```

   Monitor logs to ensure the node is running correctly.

---

## **Interacting with the Blockchain**

1. **Query the Blockchain**  
   Use the CLI to query blockchain information:  
   ```bash
   ./target/release/nolus-core query <command>
   ```

2. **Submit Transactions**  
   Use the CLI to submit transactions:  
   ```bash
   ./target/release/nolus-core tx <command>
   ```

3. **Keys Management**  
   Create or manage keys for signing transactions:  
   ```bash
   ./target/release/nolus-core keys add <key-name>
   ```

---

## **Development**

To contribute to the Nolus Core repository:

1. Create a new branch for your feature or bugfix:  
   ```bash
   git checkout -b feature/my-feature
   ```

2. Make your changes and commit:  
   ```bash
   git add .
   git commit -m "Description of changes"
   ```

3. Push the branch and create a pull request:  
   ```bash
   git push origin feature/my-feature
   ```

---
