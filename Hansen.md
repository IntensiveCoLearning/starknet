---
timezone: Asia/Shanghai
---


# Hansen

1. 自我介绍： 在比特世界重构一个新的我 , 看过starknet的相关资料， 觉得它是一个非常好的zk链 
2. 你认为你会完成本次残酷学习吗？  yes,I will.

## Notes

<!-- Content_START -->
### 2024.09.23
听 线上的课程：starknet 工具链与开发环境  
下一步目标，做一个合约，部署在测试链上。 


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
