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
<!-- Content_END -->
