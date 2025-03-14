---
timezone: Asia/Shanghai # 中国标准时间 (UTC+8)
---

---

# {你的名字}

1. 自我介绍
   Qiao Pengjun 乔鹏军。有 Python、Go、Rust、solidity 的开发经验。大约是去年开始了解 Web3，最近在学习 solidity。对区块链技术很感兴趣。了解了一点 Solana、Sui、Starknet... 正在继续学习。希望本次学习能让我更深入的了解 Web3。拥抱 Web3，拥抱未来。

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

Cairo 在 `Starknet` 智能合约中怎么写？

- 需要定义一个模块 mod
- 需要使用属性 `#[starknet::contract]`
- 这种编程类型被称为元编程
- 属性是宏
- 宏的作用是消耗你在宏下定义的代码，并转换为其它代码
- 在这种情况下，转化是将模块转换为智能合约，所以这就是所谓的元编程
- 元编程在 Rust 当中流行起来、同样也在 cairo 中使用，只是使用了不同的宏或属性
- 当我们想要定义合约的存储时，实际上是定义了一个结构体，这个结构体必须叫 `Storage`
- 这个存储必须使用属性 `#[storage]` 来注解
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

STARKWARE ：是位于以色列的公司，开发了 Starknet，包括 Starknet 相关的技术，目前负责构建和发展， Starknet 的核心团队是 Starkware 的员工。 Starkware 的创始人及现任的 CEO 发明了 Starks ZK

的证明，这种证明推动了所有这些创新。 STARKWARE 做的第一个 ZKSTARKS 的实现被称为 STARKEx，STARKEx 是一个需要授权的系统，所以你不能直接使用 STARKEx，你需要与 STARKWARE 签订合同协议才能使用它。STARKEx 有一些固定的功能，比如说你可以交易代币，做期货合约、资产交易等待。例如：DYDXVERSION3 实际就是运行在 STARKEx 上的。许多应用程序幕后都是使用的是 STARKEx。 这是 STARKWARE 开发的第一个产品。

实际上 Cairo 就是为 STARKEx 开发的。最初是作为一种内部工具，以便更容易提高系统的能力，一段时间以后，它们希望创建一种系统，使用相同的技术、相同类型的零知识证明，使得人们可以自己使用 Cairo 创建智能合约，并随时部署它们，无须任何许可。这就是 STARKNET。因此 STARKNET 是一个无需许可的系统。是一个二层汇总。使用以太坊作为安全层，你可以通过智能合约部署你的代码逻辑，无需得到 STARKWARE 的任何许可。

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
元编程在 Rust 当中流行起来、同样也在 cairo 中使用，只是使用了不同的宏或属性
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
以太坊的最终确认大约是每 6 分钟实现一次

在乐观汇总中，从 L2 提取资金到 L1，大约需要一周的时间

在 Starknet 的情况下，这个等待时间只有 2 个小时

每 2 个小时就从 Starknet 发送有效性证明到 L1

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

Cairo 是一种可证明的编程语言，它的语法类似于 Rust。Cairo 不直接编译为 Cairo AM 字节码

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

声明和部署是 Starknet 上两个不同的操作

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
你签署一笔交易，并将其发送到 Starknet 上
接受该交易的 Starknet 节点称为 Sequencer 排序器
目前 Starknet 只有一个排序器，它具有类似内存池的功能
接收你的交易，并在实际执行交易前进行一些基本的交易验证
由于 Starknet 智能合约实际上时 Cairo 程序，因此必须在 Cairo 虚拟机上执行
交易从内存池发送到 Cairo 虚拟机，一旦执行完成，该执行的 trace 会发送到证明器，我们称其为 SHARP
被称为 SHARP 的原因是它不只是给 Starknet 使用，也给 STARKEx 使用
`SHARP· 中的证明模块创建了有效性证明，确保其计算的完整性
交易执行的结果，有效性证明会发送到以太坊上一个名为验证器的智能合约，如果验证器认为此证明正确，则该执行结果就是正确的。

### 2024.09.27

Tx 生命周期
你发送一笔交易，需要对其进行签署，然后该交易被发送到内存池，内存池会检查该交易结构是否正确、字段是否正确以及格式是否正确
当交易被确认时，Starknet 就会接收它， 这时候它的状态就会变成 RECEIVED
如果发生某些事情，比如智能手机和排序器直接的连接中断了，你的交易将被忽略，故它的状态会变成 IGNORED
这个状态并不是一个标准状态，它意味着 Starknet 不会知道你的交易
有可能发生交易已经到了内存池，但因为格式不正确，比如使用了错误的客户端或 SDK。在这种情况下，Sequencer 排序器会忽略该交易，不会解析其中的数据。
如果交易格式正确，被排序器和内存池接收，下一步就到签名验证阶段了，每笔交易都必须签名，如果签名不正确，意味着它的公私钥不对应，交易会被拒绝。如果签名有效，它就继续在 CairoVM 虚拟机中运行。
如果排序器能成功使用 CairoVM 执行该交易，它的状态会变为 ACCEPTEN_ON_L2。也就是在 L2 上被接受。这就是在 L2 上最终被确认的状态。是在 Starknet 上执行你的交易后网络的新状态。
如果在执行过程中发生某些事情，例如、燃气耗尽或者断言错误，交易将停止并执行回滚。但你仍然会被收取执行交易从发生到回滚哪一刻产生的费用，最终的状态会变为 REVERTED。
无论交易成功或失败，最终都会生成 trace，并发送给证明者，证明者会生成有效证明，如果被以太坊接受，交易状态将变为 ACCEPTED_ON_L1，也就是说在 L1 上被接受。
总结：你的交易首先被内存池接收并确认，如果结构正确，通过签名验证，它将进入 CairoVM 虚拟机执行，如果执行失败，交易将被拒绝。如果执行成功，交易将获得在 L2 上被接受的状态，即 ACCEPTED_ON_L2。并在 L2 上达到最终确认。有效性证明生成后发送给以太坊的验证器，如果被接受，交易状态将变为在 L1 上被接受，即 ACCEPTED_ON_L1。这就是整个生命周期

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

### 主题

1. 设置开发工具
2. 合约类和实例
3. 合约剖析
4. 实战

### 设置开发工具

#### `Scarb`的介绍与安装

- 包管理
- 处理依赖
- 项目编译
- 与 Foundry 集成

- <https://asdf-vm.com/guide/getting-started.html>
- <https://www.cairo-lang.org/tutorial/>

```shell
brew install asdf

asdf plugin add scarb
asdf install scarb latest
asdf global scarb latest

scarb --version
```

#### `Starknet Foundry`

专为 `Starknet` 合约的开发和测试而设计

组成部分：

- Forge
- Cast

<https://foundry-rs.github.io/starknet-foundry/index.html>

```shell
curl -L https://raw.githubusercontent.com/foundry-rs/starknet-foundry/master/scripts/install.sh | sh

snfoundryup

asdf plugin add starknet-foundry
asdf install starknet-foundry latest

snforge --version
sncast --version

```

### [Universal-Sierra-Compiler update](https://foundry-rs.github.io/starknet-foundry/getting-started/installation.html#universal-sierra-compiler-update)

If you would like to bump the USC manually (e.g. when the new Sierra version is released) you can do it by running:

```shell
curl -L https://raw.githubusercontent.com/software-mansion/universal-sierra-compiler/master/scripts/install.sh | sh
```

### 2 合约类和实例

#### 合约类

Contract Class

- Code (cairo => Compiled to sierra)
- ABI (which functions are accessible)
- Class HASH

声明合约生成类哈希

#### 合约实例

Contract instance

- Storage
- Associated class hash
- Contract ADDRESS

工厂模式

READ => CALLS(free)

WRITE => INVOKE (it's a transaction = gas to pay)

| Declare | Invoke   | Deploy_account |
| ------- | -------- | -------------- |
| class   | instance | instance       |

可以用智能合约做什么

- 链游
- 可验证神经网络
- AppChains
- zkEVM
- ...

### 3 智能合约剖析

#### 最基本的合约

```rust
#[starknet::contract]
mod CounterContract {

  #[storage]
  struct Storage {

  }
}
```

#### 构造函数

```rust
#[starknet::contract]
mod CounterContract {
  #[storage]
  struct Storage {
    counter: u32,
  }

  #[constructor]
  fn constructor(ref self: ContractState, initial_counter: u32) {
    self.counter.write(initial_counter);
  }
}
```

#### 特征实现 trait

```rust
#[abi(embed_v0)]
impl CounterContract of super::ICounterContract<ContractState> {
  fn get_counter(self: @ContractState) -> u32 {
    self.counter.read()
  }

  fn increase_counter(ref self: ContractState) {
    let current_counter = self.counter.read();
    self.counter.write(current_counter + 1);
  }
}
```

#### 特征

```rust
#[starknet::interface]
trait ICounterContract<TContractState> {
  fn get_counter(self: @TContractState) -> u32;
  fn increase_counter(ref self: TContractState);
}
```

#### 事件

```rust
#[event]
#[derive(Drop, starknet::Event)]
enum Event {
  OwnershipTransferred: OwnershipTransferred,
}

#[derive(Drop, starknet::Event)]
struct OwnershipTransferred {
  #[key]
  previous_owner: ContractAddress,
  new_owner: ContractAddress,
}
```

#### Dispatcher

```rust
#[starknet::interface]
trait IData<T>{
  fn get_data(self: @T) -> felt252;
  fn set_data(ref self: T, data: felt252);
}

#[starknet::contract]
mod MyContract {
  use starknet::ContractAddress;
  use super::{IDataDispatcher, IDataDispatcherTrait};

  #[storage]
  struct Storage {

  }

  #[abi(embed_v0)]
  fn get_data_call(self: @ContractState, data_address: ContractAddress) -> felt252 {
    let dispatcher = IDataDispatcher {contract_address: data_address};
    dispatcher.get_data()
  }
}
```

#### 组件

```rust
#[starknet::interface]
trait IOwnable<TCcontractState> {
  // CODE
}

#[starknet::component]
mod ownable_component {
  #[storage]
  struct Storage {

  }

  #[event]
  #[derive(Drop, starknet::Event)]
  enum Event {
    OwnershipTransferred: OwnershipTransferred
  }

  #[derive(Drop, starknet::Event)]
  struct OwnershipTransferred {
    // CODE
  }

  #[embeddable_as(OwnableImpl)]
  impl Ownable<TContractState, +HasComponent<TContractState>> of super::IOwnable<ComponentState<TContractState>> {
    // CODE
  }
}
```

组件不能被部署，只能嵌入到合约中，称为合约的一部分

### 4 实战

<https://github.com/starknet-edu/counter-workshop>

使用 vscode 打开并安装 `Cairo 1` 扩展

### 2024.09.29

序列器的角色类似于以太坊的验证者，主要任务是接收用户的 transacton，按顺序排列这些 transaction，处理这些 transaction，然后将它们打包成块。
序列器对 transaction 处理的方法包括：排序、执行、打包以及生成区块。
序列器需要不断的快速的处理 transaction，因此序列器需要强大且可靠的计算基础设施。
Starknet 的发展路线包括将序列器的角色去中心化，从而提高网络的鲁棒性，并减少中心化的风险。

证明器也是 Starknet 一个非常关键的组件，证明器的职责包括：接收区块、处理生成证明、将证明发送到以太坊。
Starknet 中的证明器充当二次验证的角色，在序列器处理并批量将 transaction 打包成区块以后，这些区块会传递给证明器，证明器会重新处理这些区块，以确保所有的 StarkNet 均以正确执行，然后证明器为每个区块生成证明，并将它们发送到以太坊网络进行验证。
这个步骤的计算量是非常巨大的 ，证明器被设计为处理复杂任务的一种组件，它的工作可以是异步的，证明器的工作可以被分成多个部分，允许并行处理和高效的证明生成，这种灵活性的工作方式使得负载可以在多个证明器之间分配，每个证明器可以处理不同的区块，实现并行性和高效的证明生成。
在这种情况下，以太坊托管了一个能够验证这些 Stark 证明的智能合约，如果证明有效，stark 状态根就会在 L1 上更新。

### 2024.09.30

1. ABI 方便合约进行链上调用，规定用户可调用的外部函数
2. Storage 存储状态，正常程序可以直接调用操作系统写入，而区块链则需要使用特定操作码或函数写入
3. Event 事件，主要方便于链下索引，是避免链上状态空间膨胀的重要措施
4. Constructor 构造器，用于合约初始化

StarkNet 中的节点与比特币或以太坊区块链的节点相比，有着独特的功能。
以太坊中的节点充当网络的审计者，维护着网络的状状态，例如每个参与者拥有多少 ETH，或者特定智能合约的当前状态

节点通过处理 transaction，并保存所有的 transaction 记录来实现这一点，StarkNet 节点不一定需要处理所有 transaction 来维护这种状态。

通常节点访问网络状态数据的三种主要方法包括：
第一种方法是重放旧的 transaction，这种方式类似于以太坊或比特币，节点可以取走所有的 transaction，并重新执行它们。尽管这种方法准确，但除非你拥有能够处理这些负载的强大机器，否则它并不可扩展。如果能重放所有的 transaction，这就可以作为一个序列器使用了。

第二种方法是依赖 L2 的共识，所有节点信任序列器能够正确的执行网络，这种方法就涉及到一些信任假设，但是他的资源需求较少。目前 Stacknet 围绕一个序列器进行，所以这些节点是信任 Stackware 不会破坏网络的。

第三种方法是在 L1 上检查证明并验证，节点呢可以通过观察 L1，并确保每次发送证明能收到更新的状态来监控网络的状态，这样他们不必信任任何人，只需要跟踪 StarkNet 上最新的有效的 transaction 就可以。

### 2024.10.01

### 六步：执行测试

<https://foundry-rs.github.io/starknet-foundry/testing/running-tests.html>

#### 运行所有测试

```bash
simple_storage on  main [?] via 🅒 base
➜ scarb test
     Running test simple_storage (snforge test)
   Compiling snforge_scarb_plugin v0.31.0 (git+https://github.com/foundry-rs/starknet-foundry?tag=v0.31.0#72ea785ca354e9e506de3e5d687da9fb2c1b3c67)
    Finished `release` profile [optimized] target(s) in 0.18s
   Compiling simple_storage v0.1.0 (/Users/qiaopengjun/Code/starknet-code/hello_starknet/simple_storage/Scarb.toml)
    Finished release target(s) in 4 seconds
   Compiling snforge_scarb_plugin v0.31.0 (git+https://github.com/foundry-rs/starknet-foundry?tag=v0.31.0#72ea785ca354e9e506de3e5d687da9fb2c1b3c67)
    Finished `release` profile [optimized] target(s) in 0.12s
   Compiling test(simple_storage_unittest) simple_storage v0.1.0 (/Users/qiaopengjun/Code/starknet-code/hello_starknet/simple_storage/Scarb.toml)
   Compiling test(simple_storage_integrationtest) simple_storage_integrationtest v0.1.0 (/Users/qiaopengjun/Code/starknet-code/hello_starknet/simple_storage/Scarb.toml)
    Finished release target(s) in 8 seconds


Collected 5 test(s) from simple_storage package
Running 0 test(s) from src/
Running 5 test(s) from tests/
[PASS] simple_storage_integrationtest::test_contract::test_owner (gas: ~169)
[PASS] simple_storage_integrationtest::test_contract::test_initial_value (gas: ~233)
[PASS] simple_storage_integrationtest::test_contract::test_set_and_get_data (gas: ~245)
[PASS] simple_storage_integrationtest::test_contract::test_zero_value (gas: ~184)
[PASS] simple_storage_integrationtest::test_contract::test_multiple_updates (gas: ~261)
Tests: 5 passed, 0 failed, 0 skipped, 0 ignored, 0 filtered out
```

#### 运行指定测试

```bash
simple_storage on  main [?] via 🅒 base took 14.1s
➜ scarb test test_set_and_get_data
     Running test simple_storage (snforge test)
   Compiling snforge_scarb_plugin v0.31.0 (git+https://github.com/foundry-rs/starknet-foundry?tag=v0.31.0#72ea785ca354e9e506de3e5d687da9fb2c1b3c67)
    Finished `release` profile [optimized] target(s) in 0.18s
   Compiling simple_storage v0.1.0 (/Users/qiaopengjun/Code/starknet-code/hello_starknet/simple_storage/Scarb.toml)
    Finished release target(s) in 4 seconds
   Compiling snforge_scarb_plugin v0.31.0 (git+https://github.com/foundry-rs/starknet-foundry?tag=v0.31.0#72ea785ca354e9e506de3e5d687da9fb2c1b3c67)
    Finished `release` profile [optimized] target(s) in 0.12s
   Compiling test(simple_storage_unittest) simple_storage v0.1.0 (/Users/qiaopengjun/Code/starknet-code/hello_starknet/simple_storage/Scarb.toml)
   Compiling test(simple_storage_integrationtest) simple_storage_integrationtest v0.1.0 (/Users/qiaopengjun/Code/starknet-code/hello_starknet/simple_storage/Scarb.toml)
    Finished release target(s) in 8 seconds


Collected 1 test(s) from simple_storage package
Running 1 test(s) from tests/
[PASS] simple_storage_integrationtest::test_contract::test_set_and_get_data (gas: ~245)
Running 0 test(s) from src/
Tests: 1 passed, 0 failed, 0 skipped, 0 ignored, 4 filtered out

```

#### [显示测试期间使用的资源](https://foundry-rs.github.io/starknet-foundry/testing/running-tests.html#displaying-resources-used-during-tests)

```bash
simple_storage on  main [?] via 🅒 base took 14.6s
➜ scarb test test_set_and_get_data --detailed-resources
     Running test simple_storage (snforge test)
   Compiling snforge_scarb_plugin v0.31.0 (git+https://github.com/foundry-rs/starknet-foundry?tag=v0.31.0#72ea785ca354e9e506de3e5d687da9fb2c1b3c67)
    Finished `release` profile [optimized] target(s) in 0.18s
   Compiling simple_storage v0.1.0 (/Users/qiaopengjun/Code/starknet-code/hello_starknet/simple_storage/Scarb.toml)
    Finished release target(s) in 4 seconds
   Compiling snforge_scarb_plugin v0.31.0 (git+https://github.com/foundry-rs/starknet-foundry?tag=v0.31.0#72ea785ca354e9e506de3e5d687da9fb2c1b3c67)
    Finished `release` profile [optimized] target(s) in 0.12s
   Compiling test(simple_storage_unittest) simple_storage v0.1.0 (/Users/qiaopengjun/Code/starknet-code/hello_starknet/simple_storage/Scarb.toml)
   Compiling test(simple_storage_integrationtest) simple_storage_integrationtest v0.1.0 (/Users/qiaopengjun/Code/starknet-code/hello_starknet/simple_storage/Scarb.toml)
    Finished release target(s) in 8 seconds


Collected 1 test(s) from simple_storage package
Running 1 test(s) from tests/
[PASS] simple_storage_integrationtest::test_contract::test_set_and_get_data (gas: ~245)
        steps: 7255
        memory holes: 1057
        builtins: (range_check: 115, pedersen: 7)
        syscalls: (StorageWrite: 3, StorageRead: 2, CallContract: 2, Deploy: 1, GetExecutionInfo: 1)

Running 0 test(s) from src/
Tests: 1 passed, 0 failed, 0 skipped, 0 ignored, 4 filtered out

```

### 第七步：查看测试覆盖率

<https://github.com/software-mansion/cairo-coverage>

<https://foundry-rs.github.io/starknet-foundry/testing/coverage.html>

#### 1. 安装 `cairo-coverage`

```bash
curl -L https://raw.githubusercontent.com/software-mansion/cairo-coverage/main/scripts/install.sh | sh
```

实操

```bash
~ via 🅒 base took 3.3s
➜
curl -L https://raw.githubusercontent.com/software-mansion/cairo-coverage/main/scripts/install.sh | sh
  % Total    % Received % Xferd  Average Speed   Time    Time     Time  Current
                                 Dload  Upload   Total   Spent    Left  Speed
100  3014  100  3014    0     0   2876      0  0:00:01  0:00:01 --:--:--  2878
Downloading and extracting cairo-coverage-v0.2.0-aarch64-apple-darwin...
  % Total    % Received % Xferd  Average Speed   Time    Time     Time  Current
                                 Dload  Upload   Total   Spent    Left  Speed
  0     0    0     0    0     0      0      0 --:--:-- --:--:-- --:--:--     0
100 2430k  100 2430k    0     0   989k      0  0:00:02  0:00:02 --:--:-- 1695k
cairo-coverage (v0.2.0) has been installed successfully.



~ via 🅒 base
➜
cairo-coverage -V
cairo-coverage 0.2.0

```

#### 2. `Scarb.toml` 文件中进行如下配置

```toml
[profile.dev.cairo]
unstable-add-statements-code-locations-debug-info = true
unstable-add-statements-functions-debug-info = true
inlining-strategy = "avoid"

```

#### 3. 调用 `cairo-coverage` 运行测试生成测试覆盖率文件

```bash
simple_storage on  main [?] via 🅒 base took 14.5s
➜ scarb test --coverage
     Running test simple_storage (snforge test)
   Compiling snforge_scarb_plugin v0.31.0 (git+https://github.com/foundry-rs/starknet-foundry?tag=v0.31.0#72ea785ca354e9e506de3e5d687da9fb2c1b3c67)
    Finished `release` profile [optimized] target(s) in 0.18s
   Compiling simple_storage v0.1.0 (/Users/qiaopengjun/Code/starknet-code/hello_starknet/simple_storage/Scarb.toml)
    Finished release target(s) in 4 seconds
   Compiling snforge_scarb_plugin v0.31.0 (git+https://github.com/foundry-rs/starknet-foundry?tag=v0.31.0#72ea785ca354e9e506de3e5d687da9fb2c1b3c67)
    Finished `release` profile [optimized] target(s) in 0.13s
   Compiling test(simple_storage_unittest) simple_storage v0.1.0 (/Users/qiaopengjun/Code/starknet-code/hello_starknet/simple_storage/Scarb.toml)
   Compiling test(simple_storage_integrationtest) simple_storage_integrationtest v0.1.0 (/Users/qiaopengjun/Code/starknet-code/hello_starknet/simple_storage/Scarb.toml)
    Finished release target(s) in 9 seconds


Collected 5 test(s) from simple_storage package
Running 5 test(s) from tests/
[PASS] simple_storage_integrationtest::test_contract::test_initial_value (gas: ~233)
[PASS] simple_storage_integrationtest::test_contract::test_owner (gas: ~169)
[PASS] simple_storage_integrationtest::test_contract::test_set_and_get_data (gas: ~245)
[PASS] simple_storage_integrationtest::test_contract::test_zero_value (gas: ~184)
[PASS] simple_storage_integrationtest::test_contract::test_multiple_updates (gas: ~261)
Running 0 test(s) from src/
[WARNING] No trace data to generate coverage from
Tests: 5 passed, 0 failed, 0 skipped, 0 ignored, 0 filtered out

```

查看生成的文件：

```bash
simple_storage on  main [?] via 🅒 base
➜ cd coverage

simple_storage/coverage on  main [?] via 🅒 base
➜ ls
coverage.lcov

simple_storage/coverage on  main [?] via 🅒 base
➜ cat coverage.lcov
TN:
SF:/Users/qiaopengjun/Code/starknet-code/hello_starknet/simple_storage/src/simple_storage.cairo
FN:31,simple_storage::simple_storage::SimpleStorage::SimpleStorageImpl::get_data
FNDA:28,simple_storage::simple_storage::SimpleStor
```

#### 4. 使用 `genhtml` 工具生成并查看测试覆盖率报告

##### 安装 `lcov`

```bash
brew install lcov

==> Auto-updating Homebrew...
Adjust how often this is run with HOMEBREW_AUTO_UPDATE_SECS or disable with
HOMEBREW_NO_AUTO_UPDATE. Hide these hints with HOMEBREW_NO_ENV_HINTS (see `man brew`).
==> Auto-updated Homebrew!
Updated 3 taps (surrealdb/tap, homebrew/services and pulumi/tap).

You have 89 outdated formulae installed.

==> Fetching lcov
==> Downloading https://mirrors.tuna.tsinghua.edu.cn/homebrew-bottles//lcov-2.1.arm64_sequoia.bottle.tar.gz
########################################################################################################################################################## 100.0%
==> Pouring lcov-2.1.arm64_sequoia.bottle.tar.gz
🍺  /opt/homebrew/Cellar/lcov/2.1: 64 files, 1.9MB
==> Running `brew cleanup lcov`...
Disable this behaviour by setting HOMEBREW_NO_INSTALL_CLEANUP.
Hide these hints with HOMEBREW_NO_ENV_HINTS (see `man brew`).


genhtml --version
genhtml: LCOV version 2.1-1
```

##### 使用[lcov 包](https://github.com/linux-test-project/lcov/tree/master)中的工具`genhtml`生成 HTML 报告

```bash
simple_storage/coverage on  main [?] via 🅒 base
➜ genhtml -o coverage_report coverage.lcov
Reading tracefile coverage.lcov.
Found 2 entries.
Found common filename prefix "/Users/qiaopengjun/Code/starknet-code/hello_starknet/simple_storage"
Generating output.
Processing file src/simple_storage.cairo
  lines=14 hit=14 functions=7 hit=7
Processing file tests/test_contract.cairo
  lines=6 hit=6 functions=2 hit=2
Overall coverage rate:
  source files: 2
  lines.......: 100.0% (20 of 20 lines)
  functions...: 100.0% (9 of 9 functions)
Message summary:
  no messages were reported

simple_storage/coverage on  main [?] via 🅒 base
➜ ls -l
total 8
-rw-r--r--   1 qiaopengjun  staff  2081 Sep 30 21:57 coverage.lcov
drwxr-xr-x  15 qiaopengjun  staff   480 Sep 30 22:15 coverage_report

```

##### 在浏览器中打开`coverage_report`目录中的`index.html` 文件查看生成的覆盖率报告

### 2024.10.02

# Simple Counter

## 实操

### 项目

```bash

hello_starknet on  main [?] via 🅒 base
➜
snforge --version
sncast --version

snforge 0.31.0
sncast 0.31.0

hello_starknet on  main [?] via 🅒 base
➜
scarb --version
scarb 2.8.2 (a37b4cbfc 2024-09-09)
cairo: 2.8.2 (https://crates.io/crates/cairo-lang-compiler/2.8.2)
sierra: 1.6.0


hello_starknet on  main [?] via 🅒 base
➜
snforge init simple_counter
Created `simple_counter` package.
    Removing cairo_test from dev-dependencies
    Updating git repository https://github.com/foundry-rs/starknet-foundry

hello_starknet on  main [?] via 🅒 base took 19.0s
➜
ls
README.md      classwork      hello_cairo    hellostarknet  simple_counter starknet_erc20
classroom      crossinteract  hello_world    ownable        simple_storage test-cairo

hello_starknet on  main [?] via 🅒 base
➜
cd simple_counter/

simple_counter on  main [?] via 🅒 base
➜
open -a cursor .

simple_counter on  main [?] via 🅒 base
➜


simple_counter on  main [?] via 🅒 base took 10.3s
➜ scarb fmt && scarb build
   Compiling snforge_scarb_plugin v0.31.0 (git+https://github.com/foundry-rs/starknet-foundry?tag=v0.31.0#72ea785ca354e9e506de3e5d687da9fb2c1b3c67)
    Finished `release` profile [optimized] target(s) in 0.10s
   Compiling simple_counter v0.1.0 (/Users/qiaopengjun/Code/starknet-code/hello_starknet/simple_counter/Scarb.toml)
    Finished release target(s) in 3 seconds

simple_counter on  main [?] via 🅒 base took 3.1s
➜ scarb test
     Running test simple_counter (snforge test)
   Compiling snforge_scarb_plugin v0.31.0 (git+https://github.com/foundry-rs/starknet-foundry?tag=v0.31.0#72ea785ca354e9e506de3e5d687da9fb2c1b3c67)
    Finished `release` profile [optimized] target(s) in 0.11s
   Compiling simple_counter v0.1.0 (/Users/qiaopengjun/Code/starknet-code/hello_starknet/simple_counter/Scarb.toml)
    Finished release target(s) in 3 seconds
   Compiling snforge_scarb_plugin v0.31.0 (git+https://github.com/foundry-rs/starknet-foundry?tag=v0.31.0#72ea785ca354e9e506de3e5d687da9fb2c1b3c67)
    Finished `release` profile [optimized] target(s) in 0.10s
   Compiling test(simple_counter_unittest) simple_counter v0.1.0 (/Users/qiaopengjun/Code/starknet-code/hello_starknet/simple_counter/Scarb.toml)
   Compiling test(simple_counter_integrationtest) simple_counter_integrationtest v0.1.0 (/Users/qiaopengjun/Code/starknet-code/hello_starknet/simple_counter/Scarb.toml)
    Finished release target(s) in 6 seconds


Collected 5 test(s) from simple_counter package
Running 0 test(s) from src/
Running 5 test(s) from tests/
[PASS] simple_counter_integrationtest::test_contract::test_initial_count (gas: ~103)
[PASS] simple_counter_integrationtest::test_contract::test_increment_overflow (gas: ~167)
[PASS] simple_counter_integrationtest::test_contract::test_decrement_underflow (gas: ~103)
[PASS] simple_counter_integrationtest::test_contract::test_decrement (gas: ~175)
[PASS] simple_counter_integrationtest::test_contract::test_increment (gas: ~175)
Tests: 5 passed, 0 failed, 0 skipped, 0 ignored, 0 filtered out

```

```rust
#[starknet::interface]
pub trait ISimpleCounter<TContractState> {
    fn increment(ref self: TContractState);
    fn decrement(ref self: TContractState);
    fn get_current_count(self: @TContractState) -> u128;
}

#[starknet::contract]
pub mod SimpleCounter {
    #[storage]
    struct Storage {
        counter: u128,
    }

    #[constructor]
    fn constructor(ref self: ContractState, initial_count: u128) {
        self.counter.write(initial_count);
    }

    #[abi(embed_v0)]
    impl SimpleCounterImpl of super::ISimpleCounter<ContractState> {
        fn increment(ref self: ContractState) {
            let current_count = self.counter.read();
            self.counter.write(current_count + 1);
        }

        fn decrement(ref self: ContractState) {
            let current_count = self.counter.read();
            self.counter.write(current_count - 1);
        }

        fn get_current_count(self: @ContractState) -> u128 {
            self.counter.read()
        }
    }
}

```

```rust
use starknet::ContractAddress;

use snforge_std::{declare, ContractClassTrait, DeclareResultTrait};

use simple_counter::simple_counter::ISimpleCounterDispatcher;
use simple_counter::simple_counter::ISimpleCounterDispatcherTrait;

fn deploy_contract(name: ByteArray, initial_count: u128) -> ContractAddress {
    let contract = declare(name).unwrap().contract_class();
    let constructor_args = array![initial_count.into()];
    let (contract_address, _) = contract.deploy(@constructor_args).unwrap();
    contract_address
}

#[test]
fn test_initial_count() {
    let initial_count: u128 = 0;
    let contract_address = deploy_contract("SimpleCounter", initial_count);
    let dispatcher = ISimpleCounterDispatcher { contract_address };

    assert(dispatcher.get_current_count() == initial_count, 'Initial count should match');
}

#[test]
fn test_increment() {
    let initial_count: u128 = 5;
    let contract_address = deploy_contract("SimpleCounter", initial_count);
    let dispatcher = ISimpleCounterDispatcher { contract_address };

    dispatcher.increment();
    assert(dispatcher.get_current_count() == initial_count + 1, 'Count should increase by 1');

    dispatcher.increment();
    assert(dispatcher.get_current_count() == initial_count + 2, 'Count should increase by 2');
}

#[test]
fn test_decrement() {
    let initial_count: u128 = 10;
    let contract_address = deploy_contract("SimpleCounter", initial_count);
    let dispatcher = ISimpleCounterDispatcher { contract_address };

    dispatcher.decrement();
    assert(dispatcher.get_current_count() == initial_count - 1, 'Count should decrease by 1');

    dispatcher.decrement();
    assert(dispatcher.get_current_count() == initial_count - 2, 'Count should decrease by 2');
}


#[test]
#[should_panic(expected: ('u128_sub Overflow',))]
fn test_decrement_underflow() {
    let initial_count: u128 = 0;
    let contract_address = deploy_contract("SimpleCounter", initial_count);
    let dispatcher = ISimpleCounterDispatcher { contract_address };

    dispatcher.decrement();
}


#[test]
#[should_panic(expected: ('u128_add Overflow',))]
fn test_increment_overflow() {
    let initial_count: u128 = 340282366920938463463374607431768211455; // Max u128 value
    let contract_address = deploy_contract("SimpleCounter", initial_count);
    let dispatcher = ISimpleCounterDispatcher { contract_address };

    dispatcher.increment();
}

```

### 2024.10.03

ERC20

```rust
use starknet::ContractAddress;

#[starknet::interface]
pub trait IERC20<TContractState> {
    fn get_name(self: @TContractState) -> ByteArray;
    fn get_symbol(self: @TContractState) -> ByteArray;
    fn get_decimals(self: @TContractState) -> u8;
    fn get_total_supply(self: @TContractState) -> u256;
    fn balance_of(self: @TContractState, account: ContractAddress) -> u256;
    fn allowance(self: @TContractState, owner: ContractAddress, spender: ContractAddress) -> u256;
    fn transfer(ref self: TContractState, recipient: ContractAddress, amount: u256);
    fn transfer_from(
        ref self: TContractState, sender: ContractAddress, recipient: ContractAddress, amount: u256
    );
    fn approve(ref self: TContractState, spender: ContractAddress, amount: u256);
    fn increase_allowance(ref self: TContractState, spender: ContractAddress, added_value: u256);
    fn decrease_allowance(
        ref self: TContractState, spender: ContractAddress, subtracted_value: u256
    );
    fn mint(ref self: TContractState, recipient: ContractAddress, amount: u256);
}

#[starknet::contract]
mod ERC20 {
    use core::num::traits::Zero;
    use starknet::{get_caller_address, contract_address_const};
    use starknet::event::EventEmitter;
    use starknet::storage::{Map, StorageMapReadAccess, StorageMapWriteAccess};
    use super::IERC20;
    use super::ContractAddress;

    const TOTAL_SUPPLY: u256 = 100_000_000;

    #[storage]
    struct Storage {
        //name of the token
        name: ByteArray,
        //token symbol
        symbol: ByteArray,
        //token decimals e.g 18
        decimals: u8,
        //token max supply
        total_supply: u256,
        //balances of each user
        balances: Map::<ContractAddress, u256>,
        // allownaces for third party contracts
        allowances: Map::<(ContractAddress, ContractAddress), u256>,
    }

    mod Errors {
        pub const APPROVE_FROM_ZERO: felt252 = 'ERC20: approve from 0';
        pub const APPROVE_TO_ZERO: felt252 = 'ERC20: approve to 0';
        pub const TRANSFER_FROM_ZERO: felt252 = 'ERC20: transfer from 0';
        pub const TRANSFER_TO_ZERO: felt252 = 'ERC20: transfer to 0';
        pub const BURN_FROM_ZERO: felt252 = 'ERC20: burn from 0';
        pub const MINT_TO_ZERO: felt252 = 'ERC20: mint to 0';
    }

    #[constructor]
    fn constructor(ref self: ContractState, name: ByteArray, symbol: ByteArray) {
        self.name.write(name);
        self.symbol.write(symbol);
        self.total_supply.write(TOTAL_SUPPLY);
    }
    #[event]
    #[derive(Drop, starknet::Event)]
    pub enum Event {
        Transfer: Transfer,
        Approval: Approval,
    }
    #[derive(Drop, starknet::Event)]
    pub struct Transfer {
        pub from: ContractAddress,
        pub to: ContractAddress,
        pub value: u256,
    }
    #[derive(Drop, starknet::Event)]
    pub struct Approval {
        pub owner: ContractAddress,
        pub spender: ContractAddress,
        pub value: u256,
    }
    #[abi(embed_v0)]
    impl ERC20Impl of super::IERC20<ContractState> {
        // create token for testing
        fn mint(ref self: ContractState, recipient: ContractAddress, amount: u256) {
            // 确保接收者地址不是零地址
            assert(recipient.is_non_zero(), Errors::MINT_TO_ZERO);

            // 增加总供应量
            let supply = self.total_supply.read() + amount;
            self.total_supply.write(supply);

            // 增加接收者的余额
            let balance = self.balances.read(recipient) + amount;
            self.balances.write(recipient, balance);

            // 发出 Transfer 事件
            self
                .emit(
                    Event::Transfer(
                        Transfer {
                            from: contract_address_const::<
                                0
                            >(), // 从零地址转账，表示铸造
                            to: recipient,
                            value: amount
                        }
                    )
                );
        }
        //get the name of the contract
        fn get_name(self: @ContractState) -> ByteArray {
            self.name.read()
        }
        //get the symbol of the contract
        fn get_symbol(self: @ContractState) -> ByteArray {
            self.symbol.read()
        }
        //get the decimals
        fn get_decimals(self: @ContractState) -> u8 {
            self.decimals.read()
        }
        //get the max/total supply
        fn get_total_supply(self: @ContractState) -> u256 {
            self.total_supply.read()
        }
        // get the balance of a contract
        fn balance_of(self: @ContractState, account: ContractAddress) -> u256 {
            self.balances.read(account)
        }
        //transfer a token to a recipient
        fn transfer(ref self: ContractState, recipient: ContractAddress, amount: u256) {
            let sender = get_caller_address();
            self.transfer_from(sender, recipient, amount)
        }
        //transfer with two argument sender and recipient
        fn transfer_from(
            ref self: ContractState,
            sender: ContractAddress,
            recipient: ContractAddress,
            amount: u256
        ) {
            //get the address of the person calling the contract
            let caller = get_caller_address();

            let sender_balance = self.balances.read(sender);
            let recipient_balance = self.balances.read(recipient);
            assert!(sender_balance >= amount, "ERROR: INSUFFICIENT BALANCE");
            if (caller != sender) {
                assert!(self.allowances.read((sender, caller)) >= amount, "ERROR: UNAUTHORISED");
            }
            self.balances.write(sender, sender_balance - amount);
            self.balances.write(recipient, recipient_balance + amount);

            self.emit(Transfer { from: caller, to: recipient, value: amount });
        }
        // approve a contract to spend your token
        fn approve(ref self: ContractState, spender: ContractAddress, amount: u256) {
            let caller = get_caller_address();
            let allowed_person = (caller, spender);
            let previous_allowance = self.allowances.read(allowed_person);
            self.allowances.write(allowed_person, previous_allowance + amount);
            self.emit(Approval { owner: caller, spender, value: amount });
        }


        //Increases the allowance
        fn increase_allowance(
            ref self: ContractState, spender: ContractAddress, added_value: u256
        ) {
            let caller = get_caller_address();
            let allowed_person = (caller, spender);
            let previous_allowance = self.allowances.read(allowed_person);
            self.allowances.write(allowed_person, previous_allowance + added_value);
            self.emit(Approval { owner: caller, spender, value: added_value });
        }
        //reduces  the allowance
        fn decrease_allowance(
            ref self: ContractState, spender: ContractAddress, subtracted_value: u256
        ) {
            let caller = get_caller_address();
            let allowed_person = (caller, spender);
            let previous_allowance = self.allowances.read(allowed_person);
            self.allowances.write(allowed_person, previous_allowance - subtracted_value);
            self.emit(Approval { owner: caller, spender, value: subtracted_value });
        }
        //gets the amount a thirs party contract is allowed to spend
        fn allowance(
            self: @ContractState, owner: ContractAddress, spender: ContractAddress
        ) -> u256 {
            self.allowances.read((owner, spender))
        }
    }
}

```

### 2024.10.04

```rust
#[derive(Copy, Drop)]
struct Package {
    sender_country: felt252,
    recipient_country: felt252,
    weight_in_grams: usize,
}

trait PackageTrait {
    fn new(sender_country: felt252, recipient_country: felt252, weight_in_grams: usize) -> Package;
    fn is_international(ref self: Package) -> bool; //???;
    fn get_fees(ref self: Package, cents_per_gram: usize) -> usize; //???;
}
impl PackageImpl of PackageTrait {
    fn new(sender_country: felt252, recipient_country: felt252, weight_in_grams: usize) -> Package {
        if weight_in_grams <= 0{
            let mut data = ArrayTrait::new();
            data.append('x');
            panic(data);
        }
        Package { sender_country, recipient_country, weight_in_grams,  }
    }

    fn is_international(ref self: Package) -> bool //???
    {
    /// Something goes here...
        if self.sender_country == self.recipient_country {
            return false;
        }
        return true;
    }

    fn get_fees(ref self: Package, cents_per_gram: usize) -> usize //???
    {
    /// Something goes here...
        return cents_per_gram * self.weight_in_grams;
    }
}

#[test]
#[should_panic]
fn fail_creating_weightless_package() {
    let sender_country = 'Spain';
    let recipient_country = 'Austria';
    PackageTrait::new(sender_country, recipient_country, 0);
}

#[test]
fn create_international_package() {
    let sender_country = 'Spain';
    let recipient_country = 'Russia';

    let mut package = PackageTrait::new(sender_country, recipient_country, 1200);

    assert(package.is_international() == true, 'Not international');
}

#[test]
fn create_local_package() {
    let sender_country = 'Canada';
    let recipient_country = sender_country;

    let mut package = PackageTrait::new(sender_country, recipient_country, 1200);

    assert(package.is_international() == false, 'International');
}

#[test]
fn calculate_transport_fees() {
    let sender_country = 'Spain';
    let recipient_country = 'Spain';

    let cents_per_gram = 3;

    let mut package = PackageTrait::new(sender_country, recipient_country, 1500);

    assert(package.get_fees(cents_per_gram) == 4500, 'Wrong fees');
}
```

### 2024.10.05

```bash
hello_starknet/starknet_erc20 on  main [?] via 🅒 base
➜ sncast --version
sncast 0.31.0

hello_starknet/starknet_erc20 on  main [?] via 🅒 base
➜ sncast --help
sncast 0.31.0

hello_starknet/starknet_erc20 on  main [?] via 🅒 base
➜ starknet-devnet
Predeployed FeeToken
ETH Address: 0x49D36570D4E46F48E99674BD3FCC84644DDD6B96F7C741B1562B82F9E004DC7
STRK Address: 0x04718f5a0fc34cc1af16a1cdee98ffb20c31f5cd61d6ab07201858f4287c938d
Class Hash: 0x046ded64ae2dead6448e247234bab192a9c483644395b66f2155f2614e5804b0

Predeployed UDC
Address: 0x41A78E741E5AF2FEC34B695679BC6891742439F7AFB8484ECD7766661AD02BF
Class Hash: 0x7B3E05F48F0C69E4A65CE5E076A66271A527AFF2C34CE1083EC6E1526997A69

Chain ID: SN_SEPOLIA (0x534e5f5345504f4c4941)

| Account address |  0x3db6c9af232edf8c30967fd4b64fc548becd4f116f6f385c5a1a0b1809c3114
| Private key     |  0x524318337149f906e46d2da259025d85
| Public key      |  0x21cfff7154f6d1401a154b255cbe71ce4b36842baf77b549fe01e4811f80534

| Account address |  0x214a8703c0c869dbe7714fb67c9e33e7f2328b07a2fc15e0fad556c0b96f5e2
| Private key     |  0x4c71ab36691675cced37d4d844ccf704
| Public key      |  0x6d106b4c1020773adfbfcc1fa08435b0ea794fe83e7a23e9c36a80c8644203a

| Account address |  0x40d2e0cf6dddb2f71d3742f723d7cd008145aa08367858007b9f3b6ee83fa22
| Private key     |  0xad6f98f49f50c1d11955cbd60eba69f9
| Public key      |  0xd459a874bc03dba484836a4d4fceebe6f9bbe164720fdd6f0b81bad60f6bc

| Account address |  0x1d632ba8bfdb4570d242e0bfc4dfae40a27a7f23e99512b01def0b9fda372cd
| Private key     |  0x561fd040f3a458265b9cebdd64b644ad
| Public key      |  0x7c7343a16d2d8c60489b90c030c1e23becdb98d4364e3d87eadeed782b58b57

| Account address |  0x65538c5ef657bdc9c358dcb4f358b0cde0045d9f6f4bb856ceb4ddbbe15c4cb
| Private key     |  0xfffa8e9f23c6dc32095d97dd92a1dee2
| Public key      |  0x270ef409d10d525c022c46e3815c2fc0cc5652e7be72c3c2d66f8e377f44df0

| Account address |  0x42c64c0f44c6fd4dbd653c4d45af57c58e994d919890eef5bec47bd3e863225
| Private key     |  0xbeda2320770634aeb473dc6ddf835904
| Public key      |  0x6892b4d55d1eb88273abab97a39f0c9f2d582a33f403b614b2a6b8cf301608f

| Account address |  0x716e42aa0855d0ee304c135cfda22281f2c964618c1ed138fee02522f1794f5
| Private key     |  0xca0174c68d484487e9fe8ba6da3c6047
| Public key      |  0x16a28d9ff27495bbc1970ca73727ba9fa460482eacb4bb33671b6a10c9bb933

| Account address |  0x2d4a63b95ca4b01c6557a0c99bb62600f85e93c4cabe6f323615a46a7292f53
| Private key     |  0x14c970177200d955138eb61385e44d66
| Public key      |  0x4187ce34b27cfded378e332a7a4395bca8a064f09959a9859498b8055ef6037

| Account address |  0x7b4b5b7bcb2145d6bbc100c791f1da07070cd49b19ff65d9f472f60f3482623
| Private key     |  0x5f37eee3ec8d96fe9ce804d0ff0b5dfc
| Public key      |  0x260fbc9f9cc7d9750be08c43189fb67ae9f6e0a07ba8ccb5d9d299e78739c7e

| Account address |  0x2491ace3fbf3c8e981350089940f64d609cec2a9a8a3e4ecfd11b0a7767bc7c
| Private key     |  0x58795cd20f7d5a402add71d74777e814
| Public key      |  0x4ea2b3fff7cac42a16e377b7517b6c7e1c3b15a3d39705f78ed42d3ea10292a

Predeployed accounts using class with hash: 0x61dac032f228abef9c6626f995015233097ae253a7f72d68552db02f2971b8f
Initial balance of each account: 1000000000000000000000 WEI and FRI
Seed to replicate this account sequence: 1107456642
2024-10-05T11:13:44.245219Z  INFO starknet_devnet: Starknet Devnet listening on 127.0.0.1:5050

hello_starknet/starknet_erc20 on  main [?] via 🅒 base
➜ sncast account add --address 0x3db6c9af232edf8c30967fd4b64fc548becd4f116f6f385c5a1a0b1809c3114 --private-key 0x524318337149f906e46d2da259025d85 --url http://127.0.0.1:5050 --type oz --name erc20-account --add-pro
file dev-profile
command: account add
add_profile: Profile dev-profile successfully added to snfoundry.toml

```

### 2024.10.06

Starknet 是由 StarkWare 开发的 Layer-2 扩展性解决方案，致力于提高以太坊和其他区块链的性能和扩展性。该平台采用零知识证明技术，旨在为开发者提供一个可扩展、安全和高性能的环境，以构建去中心化应用（DApps）。Starknet 允许用户在去中心化环境中创建和部署高效、低成本的智能合约，并支持跨链通信和互操作性。该平台的目标是通过提供更快、更便宜的交易，以及更高的隐私性和安全性，推动去中心化应用的发展和采用。

在 `self` 前增加了 `ref` 标识，此标识代表该函数可以修改当前合约状态

### 2024.10.07

What's in a Component?
A component is very similar to a contract. It can contain:

Storage variables
Events
External and internal functions
Unlike a contract, a component cannot be deployed on its own. The component's code becomes part of the contract it's embedded to.

`# [starknet::component]`
`[embeddable_as(name)]`

### 2024.10.08

在 Cairo 中，事件是通过事件枚举。
你需要使用#[event]和#[derive(Drop, starknet::Event)]属性，每个事件变体成员必须是一个与变体同名的结构体。
然后，你需要定义事件结构体，它也需要使用#[derive(Drop, starknet::Event)]属性，并将你想要记录的参数添加为成员。

要释放事件，你需要使用 self.emit()方法，并把要记录的数据作为参数。

在 Cairo 中，只有可变变量可以用 ref 标记，因为它们在函数结束时被隐式更新。
在 Cairo 中，接口是用 #[starknet::interface] 属性标记的 trait，功能与 Solidity 中类似。规则如下：

必须明确声明函数的装饰器。
其中的函数不应被实现。
不应声明构造函数。
不应声明状态变量。
不应声明事件（与 Solidity 不同）。
所有 view 函数需要包含参数 self: @TContractState，external 函数需要包含参数 ref self: TContractState。

### 2024.10.09

笔记内容

### 2024.10.10

笔记内容

### 2024.10.11

笔记内容

### 2024.10.12

笔记内容

<!-- Content_END -->
