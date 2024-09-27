---
timezone:  Asia/Shanghai
---

---

# Phipupt

1. 自我介绍  
   接触 web3 挺长时间了，一直浅尝则止。希望借这个机会深入学习下 Starknet 和 zk  
   ps：目前正在参与 [Web3-CTF-Intensive-CoLearning](https://github.com/DeFiHackLabs/Web3-CTF-Intensive-CoLearning)
2. 你认为你会完成本次残酷学习吗？  
   没问题

## Notes

<!-- Content_START -->

### 2024.09.18

[Starknet Book](https://book.starknet.io/index.html) 已经不维护了，内容已整合到官方文档。因此，接下来参考[官方文档](https://docs.starknet.io/)学习

第一天先下载钱包、安装开发环境

1. 钱包插件  
   [Argent](https://www.argent.xyz/argent-x)   
   [Braavos](https://braavos.app/download-braavos-wallet/)

   在[这里](https://starknet-faucet.vercel.app/)领取测试网的 ETH

2. 区块链浏览器
   - [Starkscan](https://starkscan.co/)
   - [Starknet](https://viewblock.io/starknet)
   - [Voyager](https://voyager.online/)

3. 开发工具
- [Starkli](https://book.starkli.rs/)： 命令行界面与 Starknet 进行交互

   安装：
   ```
   curl https://get.starkli.sh | sh
   starkliup
   ```

- [Scarb](https://docs.swmansion.com/scarb/)： Cairo 和 Starknet 的生态系统的构建工具链和包管理器

   安装：
   ```
   curl --proto '=https' --tlsv1.2 -sSf https://docs.swmansion.com/scarb/install.sh | sh
   ```

### 2024.09.19
昨天部署了开发环境，领了水。今天开始尝试部署合约，发现 Foundry 开发框架推出了 Starknet 版本。考虑到在以太坊上的用的比较熟了，我决定使用 Foundry 来部署合约。

Starknet Foundry 使用：

- 安装

   ```
   curl -L https://raw.githubusercontent.com/foundry-rs/starknet-foundry/master/scripts/install.sh | sh

   snfoundryup
   ```

- 初始化项目

   ```snforge init hello_world```


- 运行测试

   ```snforge test```

待续...


### 2024.09.20
今天阅读[官方文档](https://docs.starknet.io/)，整理了一些 Starknet 相关概念
![starket-concepts](./phipupt/starknet-concepts.png)


### 2024.09.21
今天整理了一些 Starknet 生态项目
![starknet-ecosystem](./phipupt/starknet-ecosystem.png)


### 2024.09.22
今天整理了一些 Starknet 组件
![starknet-components.png](./phipupt/starknet-components.png)


### 2024.09.23
一些开发需要用到的资源：
- [vscode Cairo 扩展](https://marketplace.visualstudio.com/items?itemName=starkware.cairo1)，提供在编写 Cairo 智能合约时的帮助
- [starknet-devnet-rs](https://github.com/0xSpaceShard/starknet-devnet-rs) 使用 Rust 开发的 Starknet 本地测试节点
- [Katana](https://book.dojoengine.org/toolchain/katana) 由 Dojo 团队开发的一个极其快速的开发网络。可以将 Katana 用作通用开发网络

Starknet Foundry 居然还没有本地节点？


### 2024.09.24
starknet-devnet-rs 使用

安装：
```
cargo install starknet-devnet
```

运行节点：
```
starknet-devnet
```

加载环境变量
```
SEED=10 starknet-devnet
```

从文件加载配置
```
source .my-env-file && starknet-devnet
```

RPC 调用(获取账户余额)：
```
curl -X POST --data '{
    "jsonrpc": "2.0",
    "id": "1",
    "method": "devnet_getAccountBalance",
    "params": {
        "address": "<address>",
        "unit": "WEI",
        "block_tag": "latest"
    }
}' http://127.0.0.1:5050/
```


### 2024.09.25
今天正式开始学习 Cairo。

Cairo 是第一个用于创建可证明程序的图灵完备语言，适用于一般计算。Cario 由 Rust 编写。Cairo 还引入了 Sierra，这是一种新的中间表示，确保每次 Cairo 运行都可以被证明。

Cairo 不仅仅是为区块链开发者而设。作为一种通用编程语言，它可以用于任何计算，这些计算可以在一台计算机上进行证明，并在其他硬件要求较低的机器上进行验证

1. 准备工作
   - 安装 Scarb（Cairo构建工具和包管理器） 
   - [安装 VSCode 扩展](https://marketplace.visualstudio.com/items?itemName=starkware.cairo1)


2. 参考
   - [Cairo 语言官网](https://www.cairo-lang.org/)


### 2024.09.26

Scarb：Cairo构建工具和包管理器

1. 安装
   建议通过 asdf 安装 Scarb，这是一个可以按项目管理多个语言运行时版本的 CLI 工具

   asdf 安装：
   ```
   git clone https://github.com/asdf-vm/asdf.git ~/.asdf --branch v0.14.1
   . "$HOME/.asdf/asdf.sh"
   ```

   使用 asdf 安装 scarb：
   ```
   asdf plugin add scarb
   ```

   安装特定版本 scarb：
   ```
   asdf install scarb 2.8.1
   ```

2. 使用
   使用 Scarb 创建项目：
   ```
   scarb new hello_world
   ```

   其他命令：
   - `scarb build`
   - `scarb test`
   - `scarb cairo-run`
   - `scarb fmt`


3. 参考
- [Scarb 官方文档](https://docs.swmansion.com/scarb/docs.html)

### 2024.09.27
Cairo 笔记：
在 Cairo 中，代码包被称为 crates

开罗使用不可变内存模型，这意味着一旦内存单元被写入， 它不能被覆盖，只能被读取。为了反映这种不可变的内存模型， 在开罗中，变量默认是不可变的。
Caironautes

felt252 Cairo 有三种主要的标量类型：felts、整数和布尔值

布尔值的大小为一个 felt252

开罗没有原生的字符串类型，但提供了两种处理字符串的方法：使用单引号的短字符串和使用双引号的字节数组。 开罗使用felt252来处理短字符串。由于felt252是 251 位的，短字符串限制为 31 个字符（31 * 8 = 248 位，这是适合 251 位的最大 8 的倍数）

开罗代码使用蛇形命名法作为函数和变量名称的常规风格，其中所有字母都是小写字母，且下划线用于分隔单词

开罗有三种循环：loop、while和for

<!-- Content_END -->
