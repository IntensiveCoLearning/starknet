---
timezone: Asia/Shanghai
---


# Hansen

1. 自我介绍： 在比特世界重构一个新的我 , 看过starknet的相关资料， 觉得它是一个非常好的zk链 
2. 你认为你会完成本次残酷学习吗？  yes,I will.

## Notes

<!-- Content_START -->

### 2024.09.29

starknet js 的文档
https://starknetjs.com/docs/guides/intro

官网:
https://docs.starknet.io/

starkli book:
https://book.starkli.rs/

Foundry Book:
https://foundry-rs.github.io/starknet-foundry/starknet/index.html

Cairo Registry: 仓库
https://scarbs.xyz/

### 2024.09.28
今天写合约 ，调试 和部署  
写了一个 counter 的合约 ， 


### 2024.09.27

安装 scarb 
安装 starkli  
熟悉 starkli 命令   
- starkli signer
- starkli block-number
- starkli balance
- starkli account deploy    等


### 2024.09.26

分两个链 ：StarkEx 企业服务，  StarkNet  通用服务
starknet 不兼容evm，而是cvm 
    - Warp：将 Solidity 转译为 Cairo 语言的转译器
    - Kakarot：一个用 Cairo 语言编写的 zkEVM
三个特性：
- 工作原理：StarkNet 有五个组成部分。分别是在 StarkNet 上的 Prover（证明者），Sequencer（排序器）和全节点；以及部署在以太坊上的验证者（Verifier）和核心状态合约（StarkNet Core）。
- 账户抽象：StarkNet 实现了原生账户抽象
- 证明系统：STARK 证明 相比 SNARK 有更多创新，更安全

StarkNet 有一些原生的创新应用，分别是全链游戏、合约钱包和链上 AI


### 2024.09.25
简单看一下 cario 语言的 基本语法 


### 2024.09.24

学习 Starknet-js: Javascript SDK
- Starknet.js 是web 前端连接starknet 链的库。
- js-》 provider -》链 

- Starknet accounts are contracts.
- The provider allows you to interact with the Starknet network.
- contracts： 合约地址 和 abi 接口

- Next.js是一个基于React的框架，构建服务器端渲染的应用程序。React仍然是应用程序的基础，但结构和导航机制--架构--是由Next.js定义的。
  
### 2024.09.23
听 线上的课程：starknet 工具链与开发环境  
下一步目标，做一个合约，部署在测试链上。 

- https://voyager.online/   stark  的浏览器
- 部署合约，可以用 starkli  命令行  ，也可以用js-sdk 方式 ， 后者更简单
- address  是 account 的一个属性， 通过address 可以确定你的账号信息。 在部署合约的时候， 只有address 是不够的。
- 用“人”钱包，部署合约时， 先要 将账号 部署，




### 2024.09.22
今天 大概看了一下  ， cairo  的语法，   
安装了 scarb 包管理器  

### 2024.09.21

完成  starknet 的Getting Started   
在Remix IDE 中 ，部署和调用了 合约 

### 2024.09.19
学习了 视频的内容  https://youtu.be/p6mPT2HOGKI

交易生命周期：
1. mempools -> sequencer -> prover  
2. 提交到L1 层， 再做其他的vertifer

智能合约：
1. 类hash  
   每个合约1个类， 一个hash  
2. 编译过程
   cairo  sierra  casm 
3. 部署过程 
   declare   ，deploy  ，调用 
   
账户抽象：
1. 签名抽象 
   会话密钥，社交回复，密钥替换
2. 支付抽象
   支持非eth gas
   
Multicall  多重调用
1. 多个调用，一次打包  

Cairo 合约审计
1. 权限控制
   replace_class_syscall ,为了升级方便，但要注意安全  
   self.ownable.assert_only_owner();  账号检查
2. Felt 算数
   可能会越界   
   30/9    uint 类型 。
3. Tx.Origin 验证 
   get_caller_address() 作为验证的对象 
4. 隐私数据泄露
    密码存在了合约上，是有问题 
	采用hash 存储 。
5. 重入漏洞
   在调用外部合约之前，避免更新本合约的相关内部状态 。 
6. 不安全的library call 
7. 跨链
   以太坊 和 starknet 的地址，位数不同 。 
   跨链桥数据不一致性   

### 2024.09.18

Starknet is a Layer-2 network that makes Ethereum transactions faster, cheaper, and more secure using zk-STARKs technology. 
Starknet 是一个二层网络，利用 zk-STARKs 技术使以太坊交易更快、更便宜、更安全。你可以将其视为以太坊之上的一个增强层，在速度和成本方面进行了优化。
关键特性:
	- 低费用
	- 开发友好性 
	- 速度 和 高效性 
	- 使用 cairo 语言的 CVM  虚拟机 

cairo 语言
Cairo is tailor-made for creating STARK-based smart contract。 支持证明的语言 。类似rust  

### 2024.09.17




<!-- Content_END -->
