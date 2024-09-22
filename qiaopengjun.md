---
timezone: Asia/Shanghai # 中国标准时间 (UTC+8)
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

# {你的名字}

1. 自我介绍
    Qiao Pengjun 乔鹏军。有Python、Go、Rust、solidity的开发经验。大约是去年开始了解Web3，最近在学习solidity。对区块链技术很感兴趣。了解了一点Solana、Sui、Starknet... 正在继续学习。希望本次学习能让我更深入的了解Web3。拥抱Web3，拥抱未来。

2. 你认为你会完成本次残酷学习吗？
   我认为我会完成本次残酷学习，因为我有信心，并且我相信我能够克服任何困难。

## Notes

<!-- Content_START -->

### 2024.09.18

[The Starknet Book](https://book.starknet.io/index.html)

Starkli Installation

```shell
curl https://get.starkli.sh | sh
starkliup
```

Restart your terminal and confirm installation:

```shell
starkli --version
```

To upgrade Starkli, simply repeat the steps.

<https://book.starknet.io/ch02-01-basic-installation.html>

```shell
scarb --version
katana --version
```

实操

```shell
starknet on  main [!] via 🅒 base
➜
      scarb --version  # For Cairo code compilation
    starkli --version  # To interact with Starknet
    katana --version # To declare and deploy on local development

scarb 2.6.5 (d49f54394 2024-06-11)
cairo: 2.6.4 (https://crates.io/crates/cairo-lang-compiler/2.6.4)
sierra: 1.5.0

0.3.4 (9f6ea67)
katana 0.7.4
```

### 2024.09.19

部署合约前一定要先部署钱包账户，否则会报错。
<https://docs.starknet.io/quick-start/set-up-an-account/>

 Cairo  在 `Starknet` 智能合约中怎么写？

- 需要定义一个模块 mod
- 需要使用属性 `#[starknet::contract]`
- 这种编程类型被称为元编程
- 属性是宏
- 宏的作用是消耗你在宏下定义的代码，并转换为其它代码
- 在这种情况下，转化是将模块转换为智能合约，所以这就是所谓的元编程
- 元编程在Rust当中流行起来、同样也在 cairo 中使用，只是使用了不同的宏或属性
- 当我们想要定义合约的存储时，实际上是定义了一个结构体，这个结构体必须叫 `Storage`
- 这个存储必须使用属性   `#[storage]` 来注解
- 在 trait 中必须为 self 定义类型

### 2024.09.20

protostar
installed

```shell
curl -L https://raw.githubusercontent.com/software-mansion/protostar/master/install.sh | bash


Detected your preferred shell is zsh and added Protostar to PATH. Run 'source /Users/qiaopengjun/.zshrc' or start a new terminal session to use Protostar.
Then, run 'protostar --help'.


source /Users/qiaopengjun/.zshrc
protostar --help

protostar -v
Protostar version: 0.14.0
Cairo-lang version: 0.11.2
Cairo 1 compiler version: 1.1.0
22:55:11 [INFO] Execution time: 1.78 s
```

<https://www.youtube.com/watch?v=30gk2v2gXyo&list=PLKhUlfTgU76DVMLsoGD8C30pCWh66peRC>
<https://www.youtube.com/watch?v=NzXvkiSuwR0&list=PLthnZsjX96VjbSvvdKf1cyx5lBWU9mnJ7&index=3>

### 2024.09.21

remix 第一次部署调用合约成功，第二次无法点击 Declare， 调用合约失败， 换了浏览器可以成功。
猜测原因是缓存问题， 清理缓存后可以成功。
<https://www.youtube.com/watch?v=qrnbf2Ji-oU>

STARKWARE ：是位于以色列的公司，开发了 Starknet，包括 Starknet 相关的技术，目前负责构建和发展， Starknet 的核心团队是 Starkware 的员工。 Starkware 的创始人及现任的CEO 发明了 Starks ZK

的证明，这种证明推动了所有这些创新。 STARKWARE 做的第一个 ZKSTARKS 的实现被称为 STARKEx，STARKEx 是一个需要授权的系统，所以你不能直接使用STARKEx，你需要与 STARKWARE 签订合同协议才能使用它。STARKEx 有一些固定的功能，比如说你可以交易代币，做期货合约、资产交易等待。例如：DYDXVERSION3 实际就是运行在 STARKEx 上的。许多应用程序幕后都是使用的是STARKEx。 这是 STARKWARE 开发的第一个产品。

实际上Cairo 就是为 STARKEx 开发的。最初是作为一种内部工具，以便更容易提高系统的能力，一段时间以后，它们希望创建一种系统，使用相同的技术、相同类型的零知识证明，使得人们可以自己使用 Cairo 创建智能合约，并随时部署它们，无须任何许可。这就是 STARKNET。因此 STARKNET是一个无需许可的系统。是一个二层汇总。使用以太坊作为安全层，你可以通过智能合约部署你的代码逻辑，无需得到 STARKWARE 的任何许可。

STARKNET Foundation ： STARKNET 基金会是成立大约一年的一个非营利组织。目标是帮助发展 STARKNET 生态系统，或者与一些开发者达成协议来创建一些应用，或者帮助分散系统的治理。

### 2024.09.22

cairo 特征
创建可证明的程序 计算的完整性
在 CairoVM 上运行
类似 Rust 的语法
相似的所有权模型
强类型 traits macros
不专为智能合约设计
不需要了解 ZK
强类型的语言
通用语言
目前的主要用例是为 STARKNET 创建智能合约
利用了零知识证明
Cairo 就是一种高级语言、强类型、非常灵活、非常类似于 Rust，但是并不完全相同

Cairo 在 Starknet 智能合约中怎么写？
需要定义一个模块 mod
需要使用属性 #[starknet::contract]
这种编程类型被称为元编程
属性是宏
宏的作用是消耗你在宏下定义的代码，并转换为其它代码
在这种情况下，转化是将模块转换为智能合约，所以这就是所谓的元编程
元编程在Rust当中流行起来、同样也在 cairo 中使用，只是使用了不同的宏或属性
当我们想要定义合约的存储时，实际上是定义了一个结构体，这个结构体必须叫 Storage
这个存储必须使用属性 #[storage] 来注解
在 trait 中必须为 self 定义类型

```rust
#[starknet::interface]
trait ISimpleStorage<TContractState> {
  // 当你有一个方法实际上想修改智能合约内部状态时，你需要传递智能合约的状态，self 参数作为引用 ref
  fn set(ref self: TContractState, x: u128);
  // 如果从状态中只读而不修改 可以请求状态作为快照作为传递  快照使用 @ 符号
  fn get(self: @TContractState) -> u128;
}

#[starknet::contract]
mod SimpleStorage {
  #[storage]
  struct Storage {
    stored_data: u128
  }
  
  // 以下实现将成为智能合约的 ABI ，所以这是任何人都可以调用的智能合约的公共接口
  #[abi(embed_v0)]
  impl SimpleStorage of super::ISimpleStorage<ContractState> {
    fn set(ref self: ContractState, x: u128) {
      self.stored_data.write(x);
    }
    
    fn get(self: @ContractState) -> u128 {
      self.stored_data.read()
    }
  }
}
```

### 2024.09.23

笔记内容

### 2024.09.24

笔记内容

### 2024.09.25

笔记内容

### 2024.09.26

笔记内容

### 2024.09.27

笔记内容

### 2024.09.28

笔记内容

### 2024.09.29

笔记内容

### 2024.09.30

笔记内容

### 2024.10.01

笔记内容

### 2024.10.02

笔记内容

### 2024.10.03

笔记内容

### 2024.10.04

笔记内容

### 2024.10.05

笔记内容

### 2024.10.06

笔记内容

### 2024.10.07

笔记内容

### 2024.10.08

笔记内容

### 2024.10.09

笔记内容

### 2024.10.10

笔记内容

### 2024.10.11

笔记内容

### 2024.10.12

笔记内容

<!-- Content_END -->
