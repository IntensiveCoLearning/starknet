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

L1 最终确认
以太坊的最终确认大约是每6分钟实现一次

在乐观汇总中，从 L2 提取资金到 L1，大约需要一周的时间

在 Starknet 的情况下，这个等待时间只有2个小时

每2个小时就从 Starknet 发送有效性证明到 L1

一旦证明被验证，你就可以将资金转移到 L1

L2 的最终确认也就是 Starknet 的最终确认非常短

目前大约三秒钟，因此确认交易的速度非常快

只有在你想要将资产取回到 L1 时，才需要等待两个小时

与乐观汇总相比，在这方面是一个很大的优势

智能钱包的好处在于你获得了比普通钱包更好的用户体验，可以进行多次调用硬件签署来恢复会话秘钥。所有这些都是由账户抽象实现的。即将签署者与账户分离。

账户是一个具有特定接口的智能合约。

因此每次创建账户时，你都有签署者和 Starknet 上的账户合约。

它支持使用不同的椭圆曲线进行签名

在 Starknet 上每个钱包都是智能钱包，没有外部账户（EOA）

### 2024.09.24

问题：

```shell
hellostarknet on  main [?] via 🅒 base took 4.7s 
➜ scarb test 
     Running test hellostarknet (snforge test)
   Compiling snforge_scarb_plugin v0.1.0 (git+https://github.com/foundry-rs/starknet-foundry?tag=v0.30.0#196f06b251926697c3d66800f2a93ae595e76496)
    Finished `release` profile [optimized] target(s) in 0.17s
   Compiling test(hellostarknet_unittest) hellostarknet v0.1.0 (/Users/qiaopengjun/Code/starknet-code/hello_starknet/hellostarknet/Scarb.toml)
   Compiling test(hellostarknet_integrationtest) hellostarknet_integrationtest v0.1.0 (/Users/qiaopengjun/Code/starknet-code/hello_starknet/hellostarknet/Scarb.toml)
    Finished release target(s) in 8 seconds
   Compiling snforge_scarb_plugin v0.1.0 (git+https://github.com/foundry-rs/starknet-foundry?tag=v0.30.0#196f06b251926697c3d66800f2a93ae595e76496)
    Finished `release` profile [optimized] target(s) in 0.16s
   Compiling hellostarknet v0.1.0 (/Users/qiaopengjun/Code/starknet-code/hello_starknet/hellostarknet/Scarb.toml)
    Finished release target(s) in 4 seconds
[ERROR] Error while compiling Sierra. Make sure you have the latest universal-sierra-compiler binary installed. Contact us if it doesn't help: Command universal-sierra-compiler failed with status exit status: 2
```

解决：

```shell
cargo install universal-sierra-compiler --force
```

`sncast` 和 `starkli` 都可以用来与 Starknet 交互，但它们的用途略有不同，具体选择取决于你的工作流和项目需求。下面是它们的区别：

### 1. **sncast**

`sncast` 是 Starknet Foundry 工具的一部分，通常与 Foundry 集成使用，它专注于 Starknet 的开发、测试和部署。它的主要用途包括：

- **合约声明**：支持声明合约（Declare），并且与 Foundry 无缝集成。
- **部署和调用合约**：提供类似于 Ethereum 上 `cast` 的命令行工具，用于部署、调用合约以及其他链上交互。
- **开发工具链**：专注于开发者工具，特别是在 Solidity 和 Starknet 开发者的工作流中很有用。

`sncast` 适合那些已经熟悉 Foundry 开发环境并希望集成 Starknet 工作流的人群。

### 2. **starkli**

`starkli` 是 Starkware 的官方命令行工具，用于直接与 Starknet 交互。它的主要用途包括：

- **合约声明和部署**：通过 `declare` 和 `deploy` 命令来声明和部署 Cairo 合约。
- **合约调用**：能够查询、调用已经部署的合约函数。
- **官方工具链**：`starkli` 是由 Starkware 官方提供的工具，功能全面且适合与 Starknet 进行低级别交互。它对于那些使用 Cairo 开发合约并直接部署到 Starknet 上的用户特别有用。

`starkli` 更适合于想要使用 Starknet 官方工具链并直接与网络交互的用户。

### 为什么你看到两个教程？

不同的教程可能面向不同的开发者工作流：

- 如果你主要是使用 Foundry 或者已经熟悉以太坊开发工具链，那么 `sncast` 是一种方便的选择。
- 如果你更接近 Starkware 官方工具链，或者你只专注于 Cairo 和 Starknet，那么 `starkli` 可能是更好的选择。

### 如何选择？

- 如果你偏向于使用 Solidity 与 Starknet 进行交互，或者已经习惯了 Foundry 的开发工具链，**选择 `sncast`**。
- 如果你是 Cairo 开发者，想要使用 Starknet 的官方工具链，**选择 `starkli`**。

你可以根据个人开发环境和项目需求选择适合的工具。

### 2024.09.25

Cairo 是一种可证明的编程语言，它的语法类似于Rust。Cairo 不直接编译为 Cairo AM 字节码

这个编译过程是由排序器 Sequencer 完成的

Sierra 确保即使交易失败，它也会以一种与可证明系统兼容的方式失败，如果不这样做会有一个拒绝服务的漏洞。

Sierra 允许 Cairo VM 和 字节码独立于 Cairo 语言本身的演变

因此我们可以对两端进行修改、而不必修改整个系统

证明者会输出有效性证明和计算结果

排序器作为 Starknet 中的一个节点

Cairo Program
Compile Sierra
Send Sequencer
Sequencer compile CASM (Sierra)
Run Cairo VM
Prover (SHARP) RUN trace
validity proof 作为一个交易发送到 以太坊 Ethereum 进行 Verifier
result

声明和部署是Starknet 上两个不同的操作

声明智能合约只是在 Starknet 上注册代码

新的代码只需要声明一次

如果代码已经声明过，你不需要重新声明

声明的智能合约称为合约类

合约类是用来派生智能合约实例的蓝图

合约类由类哈希值标识，合约类是纯代码，没有内部存储，仅仅是蓝图，不用于直接调用或交易

要部署合约类的实例，你需要从合约类派生它并执行构造函数，然后得到一个智能合约实例，这就是我们通常指的智能合约。

智能合约有内部存储、这个合约实例由其地址标识，从同一个合约类或代码，可以通过调用构造函数部署多个实例。它们将拥有不同的地址。即使它们源自同一个合约类，但存储是不同的。

```rust
const ONE_HOUR_IN_SECONDS: u32 = 3600;

#[derive(Drop)]
struct Rectangle {
    width: u64,
    height: u64
}

#[derive(Drop)]
struct Rectangle1<T> {
    width: T,
    height: T
}

trait RectangleTrait {
    fn area(self: @Rectangle) -> u64;
}

trait RectangleTrait1<T> {
    fn area(self: @Rectangle1<T>) -> T;
}

impl RectangleImpl1<T, +Mul<T>, +Copy<T>> of RectangleTrait1<T> {
    fn area(self: @Rectangle1<T>) -> T {
        *self.width * *self.height
    }
}

fn main() {
    let mut x = 5;
    println!("Hello, world! {}", x);

    x = 6;
    println!("Hello, world! {}", x);

    println!("ONE_HOUR_IN_SECONDS is {ONE_HOUR_IN_SECONDS}");

    let mut y: u16 = 10;
    y = y / 2;
    println!("y is {y}");

    let z: u256 = 10;
    let l = 5_u8;
    println!("z is {z} and l is {l}");
    println!("z + l is {}", z + l.into());
    println!("l / y is {}", l / y.try_into().unwrap());

    let x = 'Hello World';
    println!("x is {x}"); // x is 87521618088882533792115812

    let x = 25_u16;
    println!("{}", format!("https://example.com/{}", x));

    let y: ByteArray = "Hello World";
    println!("y is {y}");
    println!("{y:?}");

    println!("{}", sum_three(1, 2, 3));

    println!("{}", min(1, 2));
    println!("{}", min2(1, 2, 3));
    println!("fib: {}", fib(1, 2, 5));

    let a = array![1, 2, 3, 4, 5];
    println!("sum_array! {}", sum_array(a));
    // println!("Arr Len is {}", a.len());  error: Variable was previously moved.

    let (a, b, c) = (1, 2, 3);
    println!("sum_three: {}", sum_three(a, b, c));
    println!("A is {a}");

    let arr = array![1, 2, 3, 4, 5];
    // println!("arr len is {}", return_len(@arr));
    println!("arr len is {}", return_len(arr.span()));
    // println!("arr len {}", arr.len());  error: Variable was previously moved.
    println!("arr len {}", arr.len());
    // 快照传参 @ 会获得变量的不可变引用
    // 可变引用传参

    println!("sum_array2: {}", sum_array2(arr.span()));

    let mut arr = array![1, 2, 3, 4];
    println!("sum_array3: {}", sum_array3(ref arr));
    println!("arr len is {}", arr.len());

    let rectangle = Rectangle { width: 30, height: 50 };
    let area = area(@rectangle);
    println!("area is {}", area);
    println!(
        "Width is {}", rectangle.width
    ); // Variable not dropped.  Variable was previously moved.

    println!("Rectangle is {}", rectangle);

    println!("Area is {}", rectangle.area());
    let rectangle1 = Rectangle1 { width: 30_u32, height: 50 };
    println!("Area is rectangle1 {}", rectangle1.area());
}

fn sum_three(a: u32, b: u32, c: u32) -> u32 {
    a + b + c
}

fn min(a: u32, b: u32) -> u32 {
    if a < b {
        a
    } else {
        b
    }
}

fn min2(a: u32, b: u32, c: u32) -> u32 {
    if (a <= b) & (a <= c) {
        a
    } else if (b <= a) & (b <= c) {
        b
    } else {
        c
    }
}

fn fib(mut a: felt252, mut b: felt252, mut n: felt252) -> felt252 {
    loop {
        if n == 0 {
            break a;
        }
        n -= 1;
        let temp = b;
        b = a + b;
        a = temp;
    }
}

fn sum_array(mut arr: Array<u32>) -> u32 {
    let mut sum = 0_u32;

    loop {
        match arr.pop_front() {
            Option::Some(current_value) => { sum += current_value },
            Option::None => { break; },
        }
    };
    sum
}

// fn return_len(arr: Array<u32>) -> u32 {
// fn return_len(arr: @Array<u32>) -> u32 {
fn return_len(arr: Span<u32>) -> u32 {
    arr.len()
}

fn sum_array2(mut arr: Span<u32>) -> u32 {
    let mut sum: u32 = 0;

    loop {
        match arr.pop_front() {
            Option::Some(current_value) => { sum += *current_value },
            Option::None => { break; },
        }
    };
    sum
}

fn sum_array3(ref arr: Array<u32>) -> u32 {
    let mut sum: u32 = 0;

    loop {
        match arr.pop_front() {
            Option::Some(current_value) => { sum += current_value },
            Option::None => { break; },
        }
    };
    sum
}

fn area(rectangle: @Rectangle) -> u64 {
    *rectangle.width * *rectangle.height
}

impl RectangleDisplay of core::fmt::Display<Rectangle> {
    fn fmt(self: @Rectangle, ref f: core::fmt::Formatter) -> Result<(), core::fmt::Error> {
        write!(f, "width: ")?;
        core::fmt::Display::fmt(self.width, ref f)?;
        write!(f, ", height: ")?;
        core::fmt::Display::fmt(self.height, ref f)
    }
}

impl RectangleImpl of RectangleTrait {
    fn area(self: @Rectangle) -> u64 {
        *self.width * *self.height
    }
}

#[cfg(test)]
mod tests {
    use super::sum_three;

    #[test]
    fn it_works() {
        assert(sum_three(1, 2, 3) == 6, 'Sum Fail');
        assert_eq!(sum_three(1, 2, 3), 6);
        assert_eq!(sum_three(10, 20, 30), 60);
    }
}
// 当我们使用简单类型 （u8 u16 u32） 时， 不需要关注所有权类型，只有报错的时候才关注
// 当遇到所有权的时候，不想改变则使用 @ Span 快照类型  修改则使用 ref 要求是可变的变量 使用 mut 

```

### 2024.09.26

<https://learnblockchain.cn/article/9415>
Transactions
transaction 是由你的钱包发起的，可以是智能手机或笔记本电脑中的钱包
你签署一笔交易，并将其发送到Starknet 上
接受该交易的 Starknet 节点称为 Sequencer 排序器
目前 Starknet 只有一个排序器，它具有类似内存池的功能
接收你的交易，并在实际执行交易前进行一些基本的交易验证
由于Starknet 智能合约实际上时 Cairo 程序，因此必须在Cairo 虚拟机上执行
交易从内存池发送到Cairo虚拟机，一旦执行完成，该执行的 trace 会发送到证明器，我们称其为 SHARP
被称为 SHARP的原因是它不只是给 Starknet 使用，也给STARKEx 使用
`SHARP· 中的证明模块创建了有效性证明，确保其计算的完整性
交易执行的结果，有效性证明会发送到以太坊上一个名为验证器的智能合约，如果验证器认为此证明正确，则该执行结果就是正确的。

### 2024.09.27

Tx 生命周期
你发送一笔交易，需要对其进行签署，然后该交易被发送到内存池，内存池会检查该交易结构是否正确、字段是否正确以及格式是否正确
当交易被确认时，Starknet 就会接收它， 这时候它的状态就会变成 RECEIVED
如果发生某些事情，比如智能手机和排序器直接的连接中断了，你的交易将被忽略，故它的状态会变成 IGNORED
这个状态并不是一个标准状态，它意味着Starknet不会知道你的交易
有可能发生交易已经到了内存池，但因为格式不正确，比如使用了错误的客户端或SDK。在这种情况下，Sequencer 排序器会忽略该交易，不会解析其中的数据。
如果交易格式正确，被排序器和内存池接收，下一步就到签名验证阶段了，每笔交易都必须签名，如果签名不正确，意味着它的公私钥不对应，交易会被拒绝。如果签名有效，它就继续在CairoVM 虚拟机中运行。
如果排序器能成功使用 CairoVM 执行该交易，它的状态会变为ACCEPTEN_ON_L2。也就是在L2 上被接受。这就是在L2 上最终被确认的状态。是在Starknet 上执行你的交易后网络的新状态。
如果在执行过程中发生某些事情，例如、燃气耗尽或者断言错误，交易将停止并执行回滚。但你仍然会被收取执行交易从发生到回滚哪一刻产生的费用，最终的状态会变为 REVERTED。
无论交易成功或失败，最终都会生成 trace，并发送给证明者，证明者会生成有效证明，如果被以太坊接受，交易状态将变为ACCEPTED_ON_L1，也就是说在 L1 上被接受。
总结：你的交易首先被内存池接收并确认，如果结构正确，通过签名验证，它将进入CairoVM 虚拟机执行，如果执行失败，交易将被拒绝。如果执行成功，交易将获得在L2 上被接受的状态，即 ACCEPTED_ON_L2。并在L2 上达到最终确认。有效性证明生成后发送给以太坊的验证器，如果被接受，交易状态将变为在L1上被接受，即 ACCEPTED_ON_L1。这就是整个生命周期

Tx 类型
声明 Declare

在 SN 注册新的类
调用 Invoke

执行 write 函数
部署账户 deploy_account

部署账户合约
假设性部署 - 部署账户合约
没有账户合约的前提下如何部署账户合约

预先计算合约地址
给这个地址发送资金
发送 deploy_account tx
序列器扣减 gas 后部署
部署账户合约与常规的智能合约是不同的

要部署智能合约你需要先有智能钱包

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
