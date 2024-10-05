---
timezone:  Asia/Shanghai
---

> 请在上边的 timezone 添加你的当地时区，这会有助于你的打卡状态的自动化更新，如果没有添加，默认为北京时间 UTC+8 时区
> 时区请参考以下列表，请移除 # 以后的内容

timezone: Pacific/Honolulu # 夏威夷-阿留申标准时间 (UTC-10)

timezone: America/Anchorage # 阿拉斯加标准时间 (UTC-9)

timezone: America/Los_Angeles # 太平洋标准时间 (UTC-8)

timezone: America/Denver # 山地标准时间 (UTC-7)

timezone: America/Chicago # 中部标准时间 (UTC-6)

timezone: America/New_York # 东部标准时间 (UTC-5)

timezone: America/Halifax # 大西洋标准时间 (UTC-4)

timezone: America/St_Johns # 纽芬兰标准时间 (UTC-3:30)

timezone: America/Sao_Paulo # 巴西利亚时间 (UTC-3)

timezone: Atlantic/Azores # 亚速尔群岛时间 (UTC-1)

timezone: Europe/London # 格林威治标准时间 (UTC+0)

timezone: Europe/Berlin # 中欧标准时间 (UTC+1)

timezone: Europe/Helsinki # 东欧标准时间 (UTC+2)

timezone: Europe/Moscow # 莫斯科标准时间 (UTC+3)

timezone: Asia/Dubai # 海湾标准时间 (UTC+4)

timezone: Asia/Kolkata # 印度标准时间 (UTC+5:30)

timezone: Asia/Dhaka # 孟加拉国标准时间 (UTC+6)

timezone: Asia/Bangkok # 中南半岛时间 (UTC+7)

timezone: Asia/Shanghai # 中国标准时间 (UTC+8)

timezone: Asia/Tokyo # 日本标准时间 (UTC+9)

timezone: Australia/Sydney # 澳大利亚东部标准时间 (UTC+10)

timezone: Pacific/Auckland # 新西兰标准时间 (UTC+12)

---

# Reign

1. Former banker and securities industry professional, engaged in macro and microeconomic analysis, stock, futures, forex, cryptocurrency trading, and quantitative research.
2. yes
## Notes

<!-- Content_START -->

### 2024.09.18

### Introduction_1

**Historical Management of Societal Roles:** Traditionally, societal roles such as currency, property rights, and social status have been governed by centralized entities through protocols and registries, with their value dependent on widespread trust in their integrity.

**Challenges of Centralization:** Centralized management often faces issues like corruption, conflicts of interest, and exclusion (Eli Ben-Sasson, Bareli, Brandt, Volokh, 2023).

**Bitcoin's Integrity Web:** Bitcoin introduced a novel approach called an "integrity web," characterized by:<br>
>>**Public Protocol:** It is governed by an openly described protocol.<br>
>>**Inclusive Peer-to-Peer Network:** It operates over a broad and decentralized network.<br>
>>**Fair Value Distribution:** It distributes value fairly to maintain societal consensus on its integrity.<br>
  
**Ethereum's Expansion:** Ethereum built upon Bitcoin's concept by extending the integrity web to include any function definable by computer programming, beyond just monetary functions.

**Scalability vs. Decentralization:** Both Bitcoin and Ethereum struggle with balancing scalability and decentralization. They often prioritize inclusivity, allowing verification of the system's integrity by those with limited resources, which can affect their ability to meet global demand.

### 2024.09.19

### Introduction_2

**Blockchain Definition**
In the rapidly evolving technological landscape, defining "Blockchain" is complex, but Eli Ben-Sasson (2023) highlights three key properties:

1. **Public Protocol**: Blockchain operates on an openly accessible protocol, fostering transparency and trust, which are vital for broader adoption.
2. **Open P2P Network**: Rather than being centralized, blockchain functions over a peer-to-peer (P2P) network, enhancing resilience and reducing the risk of censorship or failure.
3. **Value Distribution**: Blockchain incentivizes its participants by distributing value in a wide-ranging, equitable manner. This motivates operators to maintain the system’s integrity while promoting consensus.

While these properties encapsulate the essence of Blockchain, the definition may evolve as the technology matures.

**Starknet Definition**
Starknet is a Layer-2 solution for Ethereum, designed to enhance transaction speed, reduce costs, and ensure security using zk-STARKs technology. It balances scalability and consensus through a framework of mathematical proofs, allowing anyone to validate its integrity. Starknet enables powerful operators to boost network capacity while ensuring universal accessibility to verification tools.

**Starknet’s Mission**
Starknet aims to empower individuals to freely implement any social functions they desire, rooted in decentralization and inclusivity.

**Starknet’s Values**
1. **Lasting Broadness**: Starknet avoids power centralization, ensuring broad participation in its governance and operations. Its protocol remains open, and inclusivity is central to its structure.
2. **Neutrality**: Starknet remains neutral, agnostic to the societal functions it supports, and resistant to censorship.
3. **Individual Empowerment**: Education and autonomy of users are prioritized, fostering informed participation in the ecosystem.

**Key Features of Starknet**
- **Low Costs**: Starknet transactions are cheaper than those on Ethereum, and upcoming updates like Volition and EIP 4844 will further reduce costs.
- **Developer-Friendly**: It allows easy dApp development through its native language, Cairo.
- **Speed and Efficiency**: Future releases aim to further improve transaction speed and reduce costs.
- **CVM (Cairo Virtual Machine)**: Starknet operates its own VM (Cairo VM), which enables innovative decentralized applications beyond the Ethereum Virtual Machine (EVM).

Key innovations include **Account Abstraction**, **Volition** for regulating data availability, and **Paymaster**, which allows flexible transaction fee payments, including gasless transactions.

**Cairo: The Language of Starknet**
Cairo, inspired by Rust, is the programming language for creating scalable and secure STARK-based smart contracts. Developers can start learning Cairo through resources like the Cairo Book and Starklings.

**Starknet Governance**
Starknet’s governance is overseen by the Starknet Foundation, focusing on community-driven development and decision-making. Governance involves community voting on protocol upgrades, starting with testing on the Goerli Testnet and then moving to Mainnet after approval.

**SNIP: Starknet Improvement Proposals**
SNIPs (Starknet Improvement Proposals) are formal blueprints for enhancing the Starknet protocol. They outline technical specifications and rationale for proposed changes. SNIPs provide transparency and are vital for technical discussions and decision-making within the Starknet community.

### 2024.09.20

### 1.Getting Strated
Starknet is a scalable layer 2 solution built on Ethereum, designed to improve transaction throughput while maintaining Ethereum's security. The guide you provided outlines how to deploy and interact with a Starknet smart contract using the Cairo programming language, which specializes in creating validity proofs.


1. **Setting Up the Development Environment**:  
   Developers are advised to use the Remix IDE with the Starknet plugin enabled. After installation, they need to select the appropriate Cairo version (v2.5.4 in this example) under the settings tab.

2. **Modifying the Sample Project**:  
   The tutorial begins with a preconfigured sample project. Developers need to check and update the Cairo version in the `Scarb.toml` file to ensure it matches the version being used (v2.5.4). 

3. **Cleaning and Renaming the Project**:  
   Rename the root directory to "ownable" and adjust the `Scarb.toml` file's `[package]` section to reflect this change. Certain files (`balance.cairo` and `forty_two.cairo`) must be deleted, and the `lib.cairo` file should be cleared to prepare for new content.

These steps form the groundwork for deploying an example contract (`Ownable`) on Starknet. For full details on the process, visit the guide directly.

### 2024.09.21

### 2. Straknet Tooling

### Suggested Learning Path:
1. **Cairo Programming Language**: It is essential to have a basic understanding of Cairo. Reading chapters 1-6 of the *Cairo Book* (covering topics such as Getting Started, Enums, and Pattern Matching) is advised, followed by the *Starknet Smart Contracts* chapter. This will help developers understand the examples in this chapter.

2. **Starknet Development Tools**:
   - Starknet supports multiple programming languages for development, such as **JavaScript**, **Rust**, and **Python**.
   - Front-end developers can use **Starknet.js** with **React**, while **Rust** and **Python** are ideal for back-end development.
   - The **Starknet SDK** is available for various languages to facilitate dApp creation.

3. **Tools and Frameworks**:
   - **Scarb**: A package manager for compiling smart contracts.
   - **Starkli**: A CLI tool for interacting with the Starknet network.
   - **Starknet Foundry**: A framework for testing smart contracts.
   - **Katana**: Creates a local test node for development and testing.

4. **SDKs and Front-end Development**:
   - **Starknet.js**: Used for building front-end applications with React.
   - **Starknet_py** and **Starknet_rs**: SDKs for interfacing with Starknet using Python and Rust.

5. **Testing**:
   - **Starknet-Foundry** and **Devnet** provide tools for testing smart contracts effectively in a local environment.

### 2024.09.22

#### Basic Installation
This chapter focuses on setting up the essential tools for Starknet development, including Starkli, Scarb, and Katana.

#### Key Tools:
1. **Starkli:** A command-line tool for interacting with the Starknet network.

- Install via:
~~~
curl https://get.starkli.sh | sh
starkliup
~~~
- Verify installation with:
~~~
starkli --version
~~~
2. **Scarb:** Cairo's package manager, similar to Rust’s Cargo, used to compile Cairo code to Sierra (an intermediate language between Cairo and CASM).

- Requirements: Git must be installed and added to the system's PATH.
- Recommended installation method: Use asdf to manage Scarb versions.
~~~
asdf plugin add scarb
asdf install scarb 2.5.4
asdf global scarb 2.5.4
~~~
- Alternatively, install Scarb via the official script:
~~~
curl --proto '=https' --tlsv1.2 -sSf https://docs.swmansion.com/scarb/install.sh | sh
~~~
3. **Katana:** A local Starknet node for development.

- Install using the dojoup installer:
~~~
curl -L https://install.dojoengine.org | bash
dojoup
~~~
- Verify installation with:
~~~
katana --version
~~~


### 2024.09.23

### Starkli, Scarb, Katana

This chapter provides a guide for compiling, deploying, and interacting with a Starknet smart contract using tools like Starkli, Scarb, and Katana.

#### Installation and Setup
1. **Version Check**: Ensure the following commands return specified versions:
   ~~~
   scarb --version
   starkli --version
   katana --version
   ~~~

   Required versions:
   - Katana: 0.6.0-alpha.7
   - Starkli: 0.2.8 (f59724e)

3. **Project Initialization**:
   - Create a new Scarb project with `scarb new my_contract`.
   - Update the `Scarb.toml` file to include Starknet dependencies.

4. **Environment Variables**:
   - Set up a `.env` file in the `src/` directory with:
     ```
     export STARKNET_ACCOUNT=katana-0
     export STARKNET_RPC=http://0.0.0.0:5050
     ```

#### Contract Declaration
1. **Create a Smart Contract**:
   - Edit `src/lib.cairo` to include a basic contract template.
   - Compile the contract using `scarb build`.

2. **Declare the Contract**:
   - Ensure environmental variables are loaded with `source .env`.
   - Start Katana in a separate terminal using `katana`.
   - Declare the contract with:
     ```
     starkli declare target/dev/my_contract_hello.contract_class.json
     ```
   - Successful declaration returns a unique contract class hash.

#### Contract Deployment
1. **Deploy the Contract**:
   - Use the command:
     ```
     starkli deploy <CLASS_HASH> <CONSTRUCTOR_INPUTS>
     ```
   - Convert strings to felt252 format with `starkli to-cairo-string`.

#### Interacting with Contracts
1. **Read Data**:
   - Use `starkli call <CONTRACT_ADDRESS> get_name` to fetch data without modifying state.
   - Decode the result with `starkli parse-cairo-string`.

2. **Modify State**:
   - Use `starkli invoke <CONTRACT_ADDRESS> set_name <felt252>` to change the contract state.
   - Convert new names to felt252 format before invoking.

This chapter outlines the complete workflow for developing and managing Starknet smart contracts, focusing on ensuring compatibility between tools and providing practical commands for contract management.


### 2024.09.24

### Summary of Scarb: The Package Manager

**Scarb** is the package manager for Cairo and Starknet projects, handling dependencies, compiling projects, and streamlining the development process, similar to Rust's Cargo. Here's an overview of its usage:

1. **Initialization and Workflow**:
   - Set up a project with `scarb new <project_name>`, which generates a `Scarb.toml` file and a `src/lib.cairo` file.
   - Add dependencies directly in the `Scarb.toml` file or via the `scarb add` command.
   - Compile projects into Sierra code using `scarb build`, producing an intermediate output for deployment to Starknet.

2. **Project Structure**:
   - A typical Cairo package includes a `Scarb.toml` file and a `src` directory containing `.cairo` files (e.g., `lib.cairo`).
   - External libraries can be added via the `[dependencies]` section of `Scarb.toml`, specifying either registry or Git sources.

3. **Components**:
   - Starting with version 2.3.0, Scarb supports **Components**—modular add-ons that encapsulate reusable logic, storage, and events for smart contracts, allowing for easy extension of contract functionality.

4. **Example**:
   - A simple Cairo contract can be modularized using components, such as separating ownership logic into an `ownable_component` module and integrating it with the main contract.

5. **Commands Cheat Sheet**:
   - `scarb new <project_name>`: Initialize a new project.
   - `scarb build`: Compile the project into Sierra code.
   - `scarb add <dependency> --git <repo>`: Add a Git-hosted dependency.
   - `scarb clean`: Remove build artifacts.

6. **Version Changes**:
   - Version 2.3.0 introduced JSON outputs for Sierra and CASM code and support for components.

### 2024.09.25

#### Installation Steps for Starknet Development Tools

This guide helps set up essential Starknet development tools.

1. **Essential Tools**:
   - **Starkli**: A command-line interface (CLI) for interacting with Starknet.
   - **Scarb**: Cairo’s package manager for compiling code to Sierra, the intermediary language for Starknet.
   - **Katana**: A Starknet node designed for local development.

2. **Starkli Installation**:
   - Install via command:
     ```
     curl https://get.starkli.sh | sh
     ```
   - Verify installation with `starkli --version`. Repeat the steps to upgrade.

3. **Scarb Package Manager Installation**:
   - **Requirements**: Ensure a Git executable is available in your PATH.
   - Install via **asdf** for version management:
     ```
     asdf plugin add scarb
     asdf install scarb 2.5.4
     asdf global scarb 2.5.4
     ```
   - Alternatively, install directly:
     ```
     curl --proto '=https' --tlsv1.2 -sSf https://docs.swmansion.com/scarb/install.sh | sh
     ```
   - Verify installation with `scarb --version`.

4. **Katana Node Installation**:
   - Install using the Dojo engine installer:
     ```
     curl -L https://install.dojoengine.org | bash
     ```
   - Verify installation with `katana --version`.

### 2024.09.26

### Summary of Scarb: The Package Manager

**Scarb** is Cairo’s package manager designed for both Cairo and Starknet projects. It simplifies development by handling dependencies, compiling code, and integrating with tools like Foundry.

#### **Scarb Workflow**
1. **Initialize** a project with `scarb new`, generating a `Scarb.toml` file and a basic project structure.
2. **Add Code** to the `src` directory.
3. **Add Dependencies** via `scarb add`.
4. **Compile** the project using `scarb build`, converting it into Sierra code, the intermediate layer between Cairo and CASM.

#### **Cairo Project Structure**
- Projects follow a modular structure where each package has a `Scarb.toml` manifest file and a `src/lib.cairo` file. 
- Packages can include external libraries and modules, which are declared in the `Scarb.toml` file.

Example project structure:
```
my_package/
├── src/
│   ├── lib.cairo
├── Scarb.toml
```

#### **Building and Adding Dependencies**
- **Build** projects using `scarb build`, which generates the compiled Sierra code.
- **Add dependencies** by editing `Scarb.toml` or using `scarb add`. Dependencies can be hosted on GitHub or other sources and pinned to specific commits for consistency.

#### **Components (since version 2.3.0)**
Components in Scarb allow for reusable modular add-ons that extend contracts without rewriting logic. For instance, ownership functionality can be separated into a component and plugged into various contracts.

#### **Example of Adding a Component**
A typical Starknet contract can use components like `ownable_component` for ownership management, ensuring reusable and cleaner contract design.

#### **Key Commands:**
- `scarb new <project_name>`: Initialize a new project.
- `scarb build`: Compile Cairo code into Sierra.
- `scarb add <dependency>`: Add a dependency from a Git repository.
- `scarb clean`: Remove build artifacts.

#### **Conclusion**
Scarb is a powerful tool in the Cairo ecosystem, helping developers efficiently manage packages, dependencies, and code. With more experience, developers can fully leverage its capabilities to enhance their Starknet projects. Components, in particular, make it easier to build modular, reusable contract logic.

### 2024.09.27

**Katana: A Local Node for Starknet Development**

**Katana** is a tool developed by the Dojo team to aid in local development for Starknet. It allows developers to run a local Starknet environment for testing and interacting with smart contracts without needing to rely on public testnets. This local node is highly beneficial for fast, iterative contract development and debugging.

### Features of Katana:
- **Local Development & Testing**: Katana provides a local node, making it easier to test contracts, similar to the starknet-devnet (a public testnet maintained by Shard Labs). 
- **Contract Interaction**: It enables developers to deploy and interact with contracts in a local setting. Examples of contract interaction using Katana can be found in resources like *The Cairo Book*.
- **RPC Integration**: Katana supports Remote Procedure Calls (RPC), allowing communication between nodes and making it possible to interact with your local node via tools like Infura or Alchemy.

### Getting Started with Katana:
1. **Installation**: Katana can be installed using the `dojoup` installer with the following commands:
   ```bash
   curl -L https://install.dojoengine.org | bash
   dojoup
   ```
   After installation, verify it using `katana --version`.
   
2. **Starting a Local Node**: Launch a local Starknet node with specific parameters such as the number of accounts and seed:
   ```bash
   katana --accounts 3 --seed 0
   ```
   This creates prefunded accounts for testing, with output displaying their addresses, private and public keys, and the URL for the JSON-RPC server (e.g., `http://0.0.0.0:5050`).

3. **Persistence**: The local node does not store data permanently, meaning all information is erased after the node stops. To stop the node, simply use `Ctrl+C`.

### 2024.09.28

1. **环境准备**：确保安装 `scarb` 和 `starkli`，并成功运行相关命令。

2. **智能钱包设置**：创建包含私钥的Signer和包含钱包地址的Account Descriptor，部署到Sepolia Testnet。

3. **密钥管理**：使用Starkli生成和安全存储keystore文件。

4. **RPC提供者选择**：推荐使用Infura、Alchemy或免费RPC服务。

5. **账户描述符创建**：通过Starkli的fetch命令生成Account Descriptor文件，包含智能钱包的独特信息。

6. **合约声明与部署**：先声明合约，再部署实例，确保使用正确的class hash和构造参数。

7. **与合约交互**：使用call命令读取合约状态，使用invoke命令修改状态，处理潜在错误。

8. **验证与确认**：通过区块浏览器检查合约部署状态和交互结果。
   
### 2024.09.29

1. **Starkli简介**：
   - Starkli是一个命令行工具，旨在简化与Starknet的交互，基于starknet-rs。

2. **基本设置**：
   - 确保完成基本安装后，可以通过命令 `starkli --version` 验证安装。

3. **连接Starknet**：
   - Starkli使用JSON-RPC提供者进行连接，选项包括：
     - Infura或Alchemy等服务。
     - 临时本地节点（如katana）用于开发和测试。
     - 自建节点。

4. **使用Katana交互**：
   - 启动Katana并获取链ID和最新区块号的命令示例。
   - 通过命令 `starkli declare` 声明合约并查看状态变化。

5. **合约部署**：
   - Starkli支持参数解析，简化合约部署过程，通过特定格式传递构造函数输入。

6. **与Testnet交互**：
   - 使用第三方JSON-RPC API与Testnet交互，示例命令可获取最新区块号。

7. **环境变量设置**：
   - 设置环境变量以便进行ETH转账等操作，并通过`starkli invoke`命令执行。

8. **脚本创建**：
   - 提到将在下一小节中创建一个Bash脚本，以进一步与Starknet交互。
   
### 2024.09.30

这段内容详细说明了如何创建和运行自定义Bash脚本与Starknet进行交互，具体分为两个示例：Katana Local Node和Goerli Testnet。

### 1. Katana Local Node
- **目的**：连接到本地StarkNet开发网络，获取当前链ID、最新区块号和指定账户的余额。
- **步骤**：
  1. 确保Katana在终端1中运行：
     ```bash
     katana
     ```
  2. 在终端2中创建一个脚本文件：
     ```bash
     touch script_devnet
     ```
  3. 使用文本编辑器编辑该文件，插入以下脚本：
     ```bash
     #!/bin/bash
     chain=$(starkli chain-id --rpc http://0.0.0.0:5050)
     echo "Connected to the Starknet local devnet with chain id: $chain"
     
     block=$(starkli block-number --rpc http://0.0.0.0:5050)
     echo "The latest block number on Katana is: $block"
     
     account1="0x517ececd29116499f4a1b64b094da79ba08dfd54a3edaa316134c41f8160973"
     balance=$(starkli balance $account1 --rpc http://0.0.0.0:5050)
     echo "The balance of account $account1 is: $balance ETH"
     ```
  4. 执行脚本：
     ```bash
     bash script_devnet
     ```
  5. 输出内容将显示连接的链ID、最新区块号以及指定账户的余额。

### 2. Goerli Testnet
- **目的**：连接到Goerli测试网络，读取最新区块号并检索特定交易哈希的交易收据。
- **步骤**：
  1. 创建一个脚本文件：
     ```bash
     touch script_testnet
     ```
  2. 编辑文件并粘贴以下脚本：
     ```bash
     echo "Input your testnet API URL: "
     read url
     chain=$(starkli chain-id --rpc $url)
     echo "Connected to the Starknet testnet with chain id: $chain"
     
     block=$(starkli block-number --rpc $url)
     echo "The latest block number on Goerli is: $block"
     
     echo "Input your transaction hash: "
     read hash
     receipt=$(starkli receipt $hash --rpc $url)
     echo "The receipt of transaction $hash is: $receipt"
     ```
  3. 执行脚本：
     ```bash
     bash script_testnet
     ```
  4. 输入测试网API URL和交易哈希（示例哈希：`0x2dd73eb1802aef84e8d73334ce0e5856b18df6626fe1a67bb247fcaaccaac8c`）。
  
### 总结
这些示例展示了如何通过自定义Bash脚本实现与Starknet的交互，帮助用户获取链信息、区块数据和账户余额等，增强了对区块链网络的操作能力。

### 2024.10.01

Starknet Devnet (Rust-based) is a local development environment designed for testing and development on the Starknet platform. It is similar to the Python-based version but implemented in Rust for performance.

#### **Installation Options**
1. **Docker**: Starknet Devnet can be installed using Docker (follow provided instructions).
2. **Manual Installation**: 
   - Prerequisites: Install Rust (follow Rust installation guide).
   - Procedure: Clone the repository using the command `git clone https://github.com/0xSpaceShard/starknet-devnet-rs.git`, and then run `cargo run` to start.

#### **Running Starknet Devnet**
Once installed, running the command `cargo run` starts the Devnet, predeploying several contracts and accounts (with addresses, private and public keys, and seed values provided). A sample output will include details such as:
- **Fee Token Contract**
- **Universal Deployer Contract**
- **Predeployed Accounts**

#### **Key Features**
- **Seed-based Account Replication**: The `--seed` flag enables reproducing the same account sequence across different sessions.
   - Example: `cargo run -- --seed 912753742`
  
- **Dumping and Loading Data**: 
   - To save your progress, use the `--dump-on exit --dump-path` flag. To load saved data, specify the dump path and seed during launch.
   - Example for dumping: `cargo run -- --dump-on exit --dump-path ./dumps/contract_1`
   - Example for loading: `cargo run -- --dump-path ./dumps/contract_1 --seed 912753742`
  
#### **Additional Flags**
- `--accounts`: Specify number of predeployed accounts.
- `--account-class`: Set the class used by predeployed accounts (e.g., `cairo0` or `cairo1`).
- `--initial-balance`: Set initial account balance.
- `--port` and `--host`: Define where the server listens for connections.

#### **Cross-Version Compatibility Warning**
Dumping and loading data across different versions may not be compatible, so caution is advised when upgrading Devnet versions.

#### **Minting Tokens**
Tokens can be minted by making a POST request:
```bash
curl -d '{"amount":8646000000000, "address":"0x6e...eadf"}' -H "Content-Type: application/json" -X POST http://localhost:5050/mint
```

This Rust version of Starknet Devnet offers a similar feature set to the Python-based version but provides performance optimizations through Rust.

### 2024.10.02

*Designing Freedom* by Stafford Beer is a collection of lectures from 1973, where Beer explores cybernetics, management, and organizational theory. He introduces the concept of "freedom" in the context of self-organizing systems, arguing that true freedom is found within systems that provide enough structure to guide decision-making while allowing flexibility for adaptation and innovation. 

Key themes include:
1. **Systems Thinking**: Beer emphasizes the need for understanding organizations as dynamic, interconnected systems. He advocates for using cybernetic principles to design more responsive and adaptive systems.
2. **Homeostasis in Organizations**: Like biological systems, organizations must maintain balance and stability while responding to environmental changes. Beer refers to this as homeostasis, emphasizing the importance of continuous feedback loops.
3. **Viable System Model (VSM)**: One of Beer’s most influential contributions, VSM is a framework for designing systems that can survive in complex and unpredictable environments. It is built on the idea that for any system to be viable, it must balance autonomy with central control.
4. **Freedom and Control**: Beer challenges the traditional dichotomy between freedom and control, proposing that freedom is maximized not by removing constraints but by designing systems that allow flexibility within appropriate constraints.

### 2024.10.03

The **Deployment Script Example** for Starknet smart contracts guides users through setting up a testing and deployment environment, using a Bash script to automate tasks such as initializing accounts, testing contracts, building and deploying, and performing multicalls. Below is a summary of the steps:

### Requirements
- Compatible with **scarb 2.4.3**, **cairo 2.4.3**, **sierra 1.4.0**, **snforge 0.14.0**, and **sncast 0.14.0**.
- Requires installation of **jq** for handling JSON.
- Ensure you complete the **Starknet Devnet** setup beforehand.

### Script Setup

1. **Create Script File**:  
   - Create a `script.sh` in the project’s root directory.
   - Make the script executable using: `chmod +x script.sh`.

2. **Insert Script**:  
   The script includes functions and steps to automate the testing and deployment process. Important elements are:
   - **Error Management**: Stops on the first error with `set -e`.
   - **Environment Variables**: Use these for security (e.g., `ACCOUNT1_ADDRESS`, `ACCOUNT1_PRIVATE_KEY`).
   - **Account Setup**: Defines accounts for smart contracts via JSON and manages them through `sncast`.
   - **Contract Testing**: Runs tests using `snforge`, proceeding only if tests pass.
   - **Contract Deployment**: Uses `scarb` to build and `sncast` to declare and deploy contracts, handling different Devnet versions (Rust or Python).
   - **Multicalls**: Creates a `multicall.toml` to execute multiple contract function invocations.
   - **State Queries**: Checks the contract's state (e.g., balances) after deployment.

3. **Optional Adjustments**:  
   Modify the Bash path if necessary by using `which bash`.

### Execution
To run the script, provide private key environment variables before execution:
```bash
ACCOUNT1_PRIVATE_KEY="your_key" ACCOUNT2_PRIVATE_KEY="your_key" ./script.sh
```

### Considerations
- The script uses `set -e` to enhance reliability by stopping on command failure.
- Secure private keys and sensitive information. Consider moving hardcoded values (e.g., account addresses) to a configuration file.

### 2024.10.04

Starknet.js is a JavaScript/TypeScript library used to connect decentralized applications (DApps) to Starknet, an Ethereum layer 2 solution. Its architecture is modeled after ethers.js, making it easier for developers familiar with Ethereum to work with Starknet.

### Key Components:

1. **Installation**:
   - Install via npm: 
     - Stable release: `npm install starknet`
     - Latest features: `npm install starknet@next`

2. **Core Concepts**:
   - **Account**: Represents the end-user and their wallet. Unlike Ethereum's Externally Owned Accounts (EOAs), Starknet accounts are contracts.
   - **Provider**: Used to interact with the Starknet network, providing a "read" connection. Services like Infura or Alchemy can be used to set up an RPC provider.
   - **Contracts**: Interact with deployed smart contracts using the contract address and ABI. Contracts require a signer to modify blockchain states.

3. **Handling Units**:
   - Special utility functions are available to handle data types such as Cairo's Uint256 structs.

4. **Deployment**:
   Starknet.js supports deploying smart contracts. The deployment process involves setting up a Node.js environment, preparing the necessary scripts, and configuring TypeScript. It also walks through creating key pairs, compiling contract code, and deploying contracts on Starknet.

5. **Additional Tools**:
   - Automated contract deployment, interaction with account contracts, and ETH transfers using pre-defined scripts.

### 2024.10.05

### Steps Overview:

1. **Setup and Global Variables**: 
   - Defines essential variables like contract names, profile names, addresses, and keys. It uses environment variables for sensitive data such as private keys, which is a good security practice, although additional precautions like using `.env` files would further improve safety.

2. **Cleaning Previous Environment**:
   - Deletes old account files to ensure a fresh environment for new accounts.

3. **Running Contract Tests**:
   - Runs tests using `snforge` and checks for failures. If tests fail, the script halts and prompts the user to fix the issues before continuing.

4. **Creating Accounts**:
   - Iterates through JSON-defined account data to add or create new accounts using `sncast`. It checks for existing accounts to avoid duplication.

5. **Building, Declaring, and Deploying Contracts**:
   - Builds the smart contract with `scarb` and declares it on the Starknet network. Depending on whether the class hash already exists, it either reuses the existing hash or declares a new one.
   - Deploys the contract and stores the deployed contract address.

6. **Executing Multicalls**:
   - Sets up and executes multicalls using a TOML configuration file, which runs multiple contract functions in a single batch, reducing network overhead.

7. **Querying Contract State**:
   - After deployment and multicall execution, the script checks the contract’s state (e.g., the balance) to verify the correctness of the contract.

8. **Cleanup**:
   - Cleans up temporary files like the multicall TOML file once execution is complete.

### Execution:

- The script is run with environment variables for the private keys:

   ```bash
   ACCOUNT1_PRIVATE_KEY="0x259f4329e6f4590b" ACCOUNT2_PRIVATE_KEY="0xb4862b21fb97d" ./script.sh
   ```

### Security Considerations:
- **Environment Variables**: Using environment variables is safer than hardcoding private keys, but they could still be exposed to other processes on the machine. For more security, you could use tools like `dotenv` or secret management systems (e.g., AWS Secrets Manager) to manage sensitive data.
- **set -e**: Ensures that the script exits on the first error, which helps prevent the execution of subsequent steps in case of failures, enhancing reliability.

### Further Enhancements:
- **Configuration Files**: Instead of hardcoding values such as account addresses or contract names in the script, you could move them to a configuration file, making the script easier to maintain and update.

This script offers a solid foundation for deploying smart contracts on Starknet in a controlled, automated fashion. It can be customized and extended to suit more complex scenarios or different environments.
<!-- Content_END -->
