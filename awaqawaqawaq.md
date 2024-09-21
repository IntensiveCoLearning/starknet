---
timezone: Asia/Shanghai 
---

> 请在上边的 timezone 添加你的当地时区，这会有助于你的打卡状态的自动化更新，如果没有添加，默认为北京时间 UTC+8 时区
> 时区请参考以下列表，请移除 # 以后的内容


---

# awaqawaqawaq

1. 区块链新人,没有经验，啥也不会，不过总有开始的一步(
2. 你认为你会完成本次残酷学习吗？ maybe(70%)

## Notes

<!-- Content_START -->

### 2024.09.18

# 了解 starknet
## Unlock Period and Token Economics

StarkNet is a permissionless decentralized Validity-Rollup (ZK-Rollup) operating as an L2 network on Ethereum. It enables dApps to scale without compromising Ethereum’s composability and security, powered by the STARK cryptographic proof system.

- **Total Value Locked (TVL)**: $236.09m
- **Stablecoins Market Cap**: $86.69m
- **STRK Market Cap**: $679.91m

### [Unlock Period](https://coinmarketcap.com/currencies/starknet-token/#token_unlocks)

The token unlock schedule outlines the distribution and release rate of strk.

每月解锁0.64%MAX SUPPLY($63.99M strk) 约占当前市值的3%

2025 4月开始每月解锁1.28%MAX SUPPLY($127.6M	 strk)[😢😢😢](https://support.coinmarketcap.com/hc/en-us/articles/360043836811-Market-Capitalization-Cryptoasset-Aggregate)
![Estimated Circulating Supply of STRK](https://docs.starknet.io/architecture-and-concepts/_images/STRK_estimated_circulating_supply.jpg)

### [Token Economics](https://docs.starknet.io/architecture-and-concepts/economics-of-starknet/)

StarkNet's tokenomics .

## [Starknet/STARKWARE/Cairo](STARKEx)
- **STARKWARE** ：是位于以色列的公司，开发了 Starknet，包括 Starknet 相关的技术，目前负责构建和发展， Starknet 的核心团队是 Starkware 的员工。 
- **Starkware** : 的创始人及现任的CEO 发明了 Starks ZK
- **Cairo** : 具备zk抽象的高级语言

## stark支持智能钱包，使用原生账户抽象方案
- **[about AA(account abstraction)](https://www.odaily.news/post/5189963)**







### 2024.09.19
# 快速上手Cairo
- [Cairo 101](https://www.wtf.academy/en/docs/cairo-101/Constructor/)
- [Starknet Remix](https://remix.ethereum.org/#lang=en&optimize=false&runs=200&evmVersion=null)

**Cairo与Rust语法非常相似，但本人并不会rust**
- mod 模块关键字创建合约
- #[starknet::contract] 合约关键字，如果不声明，则不能部署在 Starknet 上
- #[starknet::storage] 修饰符，用于声明合约存储变量
- #[external(v0)] 外部函数声明
- let y_u8: u8 = 2; 类型声明
- local变量     // use `let` keywods to declare local variables 
- 可变，不可变，Shadowing
- self: @ContractState  view函数 self.var_name.read()
- self: ContractState  使用self.var_name.write(new_value) 修改
- use array::ArrayTrait; 数组
- loop循环
- Mapping/enum/Storage struct
- :: 用于访问结构体、枚举或模块的关联函数、常量或类型或者指定泛型类型的具体参数 
  
  MyStruct::my_function(); 
  
  let map: LegacyMap<ContractAddress, u256> = LegacyMap::new(); // 指定 LegacyMap 的类型参数
### 2024.09.20
- match模式匹配,类似switch
- 模式绑定 Colors::Red(()) 括号内携带参数
  ``` rust
  // match pattern with data (Actions)
  fn match_action(self: @ContractState, action: Actions) -> u128 {
    match action {
        Actions::Forward(dist) => {
            dist//将匹配到的值绑定至dist
        },
        Actions::Stop(_) => {
            0_u128
        }
    }
  } 
  ```

- Option
  调用Option::Some(value)创建一个Option::Some(value)的值，调用Option::None()创建一个Option::None的值 
  ``` rust
  let x: Option<u8> = Option::Some(5);
  let y: Option<u8> = Option::None();
  
  ```
  x y 为option类型，可使用match模式匹配
  ``` rust  
  match option{
      Option::Some(value) => value,
      Option::None(_) => 0_u8,
  }
  ```
- Into\TryInto  类型转换
- #[constructor] 在合约部署期间自动运行一次




<!-- Content_END -->
