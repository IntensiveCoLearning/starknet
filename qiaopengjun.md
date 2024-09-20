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

笔记内容

### 2024.09.22

笔记内容

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
