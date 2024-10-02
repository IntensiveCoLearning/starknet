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


### 2024.09.23
- [观看了第一期视频，看的懂但是看不懂🙃🙃🙃](https://youtu.be/p6mPT2HOGKI)

### 2024.09.24
- 事件 
   - 将数据存储在事件中比存储在存储变量中更具成本效益
   - 事件不能直接从合约内部读取。
   - 诸如 starknet.js 的应用程序可以通过 RPC 接口订阅这些事件，并在前端触发响应。
   - #[event]和#[derive(Drop, starknet::Event)]
   - 事件变体成员必须是一个与变体同名的结构体
   - 使用emit()释放
- 异常处理
  - assert() 
  - panic()
### 2024.9.25
#### 因为之前没有接触过Rust，所以对Rust的语法和特性感觉理解困难，观看了 [https://www.bilibili.com/video/BV1hjh1emEAY/?spm_id_from=333.337.search-card.all.click&vd_source=1356c9c3725643abb61fbb2c32756c84] 对所有权、借用规则、引用、生命周期 有了一定了解

### 2024.9.26
- Cairo 中的每一个值都有一个 所有者（owner）。
值在任一时刻有且只有一个所有者。
当所有者（变量）离开作用域，这个值将被丢弃。
如果一个值的所有权没有被 转移（move），它不能离开作用域。
- 借用(ref)
  - 借用（borrowing）允许你访问一个值而不取得其所有权。
  - 借用分为 可变借用（mutable borrow）和 不可变借用（immutable borrow）。
  - 可变借用允许你修改值，而不可变借用则不允许。
  - 在任一时刻，一个值只能有一个可变借用，或者任意数量的不可变借用。
  - 借用必须显式地声明，并且不能超过值的所有权生命周期。
  - 借用必须在使用前声明，并且不能在声明后使用。
- copy drop
  - #[derive(Copy, Drop)] 
  - 实现 Drop 特性的类型被允许没被 Move 就超出范围
  - 实现 Copy 特性的类型不被 Move 语义约束
- 在 Cairo 中，快照是某一时刻值的不可变视图。你可以将一个值的快照传递给函数，同时保留原始值的所有权。
- 使用 @ 操作符创建 x 的快照,使用 desnap 操作符 * 将快照转换回普通值
### 2024.9.27
- 观看了共学第二期视频
### 2024.9.30
- Trait
    - Trait 是一种定义了某些行为（方法）的抽象类型
    - 使用impl 实现trait
    - 使用 #[starknet::contract] 属性标记的 trait
    - 使用#[generate_trait]属性，在不用单独声明trait的情况下直接使用impl构建功能 语法糖
- 泛型 
    - 类型参数在函数名后的尖括号 < > 中指定。例如 <T>
    - impl PairImpl<T> of PairTrait<T>  // 实现泛型方法
    - 约束
- 接口
    - 用 #[starknet::interface] 属性标记的 trait
    - 必须明确声明函数的装饰器。
  
      其中的函数不应被实现。

      不应声明构造函数。

      不应声明状态变量。

      不应声明事件（与 Solidity 不同）。

      所有view函数需要包含参数self: @TContractState，external函数需要包含参数ref self: TContractState。
###  2024.10.1
- 观看视频学习了rust [https://www.bilibili.com/video/BV15y421h7j7?p=9&vd_source=1356c9c3725643abb61fbb2c32756c84]
###  2024.10.2
- 观看视频学习了rust [https://www.bilibili.com/video/BV15y421h7j7?p=9&vd_source=1356c9c3725643abb61fbb2c32756c84]
- String &str 
- copy move
- 可变借用，不可变借用
<!-- Content_END -->
