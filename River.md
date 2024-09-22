---
timezone: Pacific/Auckland
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

# River

1. 自我介绍

   有3年全栈软件开发经验，熟悉Java、Go、JS、Rust、Solidity等开发语言。目前有考虑在Starknet上构建项目的想法，因此来学习Starknet相关开发知识。

2. 你认为你会完成本次残酷学习吗？

   一定会完成。

## Notes

<!-- Content_START -->

### 2024.09.18

#### 1. 环境准备

1. 编程语言

   * `Cairo`: 通过下载`Scarb`即可安装使用

2. 编码环境

   * `asdf`: 是一个工具版本管理器，能以项目为维度管理多种编程语言的运行时版本

   * `Scarb`: 是`Cairo`的包管理器，将`Cairo`编译器和`Cairo`语言服务器打包到了一起

#### 2. 安装环境

操作系统：MacOS Big Sur

1. 安装`asdf`

   1. 安装依赖`coreutils`、`curl`、`git`，如果已经安装过了就无需再安装

      `brew install coreutils curl git`

   2. 下载`asdf`

      * 官方下载方式：

        `git clone https://github.com/asdf-vm/asdf.git ~/.asdf --branch {version}`

      * 使用`MacOS`自带工具下载：

        `brew install asdf`

   3. 安装`asdf`

      * 使用的官方的下载方式

        安装时需要在`~/.bash_profile`文件下添加以下配置：

        ~~~shell
        . "$HOME/.asdf/asdf.sh"
        . "$HOME/.asdf/completions/asdf.bash"
        ~~~

      * 使用`brew`方式安装

        安装完成后会提示设置环境变量

        ~~~shell
        To use asdf, add the following line (or equivalent) to your shell profile
        e.g. ~/.profile or ~/.zshrc:
          . /opt/homebrew/opt/asdf/libexec/asdf.sh
        e.g. ~/.config/fish/config.fish
          source /opt/homebrew/opt/asdf/libexec/asdf.fish
        Restart your terminal for the settings to take effect.
        ~~~

        

   4. 验证

      执行`source ~/.bash_profile `使上面的配置生效

      执行`asdf --version`后，显示以下内容：

      ~~~shell
      v0.14.1-f00f759
      ~~~

2. 安装`Scarb`

   **通过`asdf`安装**

   1. 添加`scarb`插件

      ~~~shell
      asdf plugin add scarb
      ~~~

   2. 查看所有可安装的版本

      ~~~shell
      asdf list-all scarb
      ~~~

   3. 安装指定版本

      ~~~shell
      # 安装最新版本
      asdf install scarb latest
      
      # 或者根据版本号安装
      asdf install scarb 2.8.2
      ~~~

   4. 设置全局版本

      ~~~shell
      asdf global scarb latest
      ~~~

   **通过`curl`命令安装**

   ~~~shell
   curl --proto '=https' --tlsv1.2 -sSf https://docs.swmansion.com/scarb/install.sh | sh
   ~~~

### 2024.09.19

#### 变量与可变性

* `Cairo`使用的是**不可变性**的内存模型，一旦写入内存块后就**只读**，不能被重写。

声明的变量默认是**不可变**的。

如果需要声明可变的变量，需要使用关键字`mut`显示指定，例如：

~~~rust
let mut x = 7;
~~~

#### 常量

声明常量使用关键字`const`，例如：

~~~rust
const ONE_HOUR_IN_SECONDS: u32 = 3600;
~~~

* 常量和变量的区别：
  * 相同：默认都是不可变的
  * 不同：常量不可使用关键字`mut`修饰

#### 变量遮蔽

在不同的**作用域**之间，声明多个**同名变量**，后声明的变量在其**作用域内**会遮蔽前面声明的变量。

* 变量遮蔽和可变变量在底层上是等价的，不同的地方在于通过变量遮蔽可以修改变量的类型。

##### 💡建议

（来自`Rust`编码规范）

变量遮蔽功能在功能上属于一种继承式可变。他会覆盖之前的变量绑定，而创建一个新的同名的变量绑定。

1. 在同一个作用域中，非必要时不宜通过新变量声明遮蔽旧变量声明的方式来修改变量。
2. 在子作用域内修改“哨兵变量”时，应该避免使用变量遮蔽功能，防止引起逻辑bug。
3. 如果使用变量遮蔽，禁止用不同类型的变量遮蔽前一个变量，如果实现同一个 `trait` 的可以例外。

### 2024.09.20

#### 数据类型

在`Cairo`中，每个值都有明确的数据类型。

* `Cairo`是一门**静态类型语言**，意味着在编译期就要知道所有变量的类型。



##### 标量类型（Scalar Types）

标量类型代表的是单个值，有三个主要的标量类型：`felts`、`integers`、`booleans`

###### Felt Type

如果变量或者参数没有被指定明确的类型，它的类型默认是一个`field element`，用关键字`felt252`表示。

* `field element`：一个在$0 \leq x < P$范围内的整型。其中`P`是一个非常大的素数，目前等于$2^{251} + 17 * 2^{192} + 1$。如果数值在做加法、减法、或者乘法时，结果的大小超过这个范围，则对`P`进行模运算。

* `integers`与`field elements`最重要的区别在于除法：`integers`的除法结果是向下取整，不一定满足$\frac{x}{y} * y == x$。而`field elements`总是满足这一等式。



###### Integer Types

 在任何时候都建议使用`integer`类型，而不是`felt252`类型，因为`integer`类型有额外的安全特征来避免代码中潜在的安全隐患，比如上溢和下溢检查。



###### Boolean Types

使用`true`和`false`这两个字面量作为值，`Boolean`类型的大小为一个`felt252`。声明时使用关键字`bool`。



###### String Types

`Cairo`中没有为字符串提供原生类型。短字符串使用单引号表示，`ByteArray`字符串使用双引号表示

* 短字符串：是`ASCII`码字符串。每个字符编码为**一个字节**。

  `Cairo`中字符串的类型使用`felt252`，由于`felt252`有251比特大小，因此一个短字符串的大小不能超过**31个字符**（$31 * 8 = 248bi$t）

* `ByteArray`字符串：使用`ByteArray`类型来处理超过短字符串大小的字符串和字节序列。

  `ByteArray`的实现有两部分组成：

  1. 一个`bytes31`个字的数组，其中每个字包含31个字节的数据
  2. 一个待定的`felt252`的字作为尚未填满完整`bytes31`个字的字节缓冲区



##### 复合类型（Compounds Types）

###### 元组类型（Tuple Type）

一个元组是将许多的多种类型的变量分组为一个复合类型的通用方法。元组的长度是固定的，一旦声明后，其大小无法增加或者减少。

~~~rust
fn main() {
    let tup: (u32, u64, bool) = (10, 20, true);
  
  	let (x, y, z) = tup;

    if y == 6 {
        println!("y is 6!");
    }
  
  	let (a, b): (felt252, felt252) = (2, 3);
}
~~~

**Unit Type**

一个单元类型只有一个值`()`。它表示一个没有元素的元组，它的大小总是0。在编译的代码中是不存在的。



###### 大小固定的数组类型

一个大小固定的数组是一个包含多个值的集合，其中每个值的类型必须相同。

~~~rust
fn main() {
    let arr1: [u64; 5] = [1, 2, 3, 4, 5];
  
    // [3, 3, 3, 3, 3]
  	let arr2 = [3; 5];
}
~~~



##### 类型转换

###### Into

`Into`特征允许一个类型来定义如何转换为另一种类型。可以被用于确保能转换成功的类型转换。

执行变量的`into()`方法进行类型转换。转换的变量的类型必须显式声明

~~~rust
fn main() {
    let my_u8: u8 = 10;
    let my_u16: u16 = my_u8.into();
    let my_u32: u32 = my_u16.into();
    let my_u64: u64 = my_u32.into();
    let my_u128: u128 = my_u64.into();

    let my_felt252 = 10;
    // As a felt252 is smaller than a u256, we can use the into() method
    let my_u256: u256 = my_felt252.into();
    let my_other_felt252: felt252 = my_u8.into();
    let my_third_felt252: felt252 = my_u16.into();
}
~~~



###### TryInto

功能与`Into`一样用于类型转换，不同的地方在于，`TryInto`在可能会转换失败的场景下使用，返回`Option<T>`，需要使用`unwrap()`方法获取转换后的变量值。

~~~rust
fn main() {
    let my_u256: u256 = 10;

    // Since a u256 might not fit in a felt252, we need to unwrap the Option<T> type
    let my_felt252: felt252 = my_u256.try_into().unwrap();
    let my_u128: u128 = my_felt252.try_into().unwrap();
    let my_u64: u64 = my_u128.try_into().unwrap();
    let my_u32: u32 = my_u64.try_into().unwrap();
    let my_u16: u16 = my_u32.try_into().unwrap();
    let my_u8: u8 = my_u16.try_into().unwrap();

    let my_large_u16: u16 = 2048;
    let my_large_u8: u8 = my_large_u16.try_into().unwrap(); // panics with 'Option::unwrap failed.'
}
~~~



### 2024.09.21

#### 函数

使用关键字`fn`声明一个函数。

函数的名称格式通常是下划线格式。如：

~~~rust
fn another_function() {
    println!("Another function.");
}
~~~

#### 参数

参数是函数签名的一部分。在函数签名中，必须声明参数的类型。

~~~rust
fn print_labeled_measurement(value: u128, unit_label: ByteArray) {
    println!("The measurement is: {value}{unit_label}");
}
~~~

#### 命名参数（Named Parameters）

在`Cairo`中，当调用函数时，可以指定参数的名称。可以让函数调用有可读性和自描述性。

语法：`parameter_name: value`，如果传递的变量与参数的名称一样时，可以简写为`:parameter_name`。

~~~rust
fn foo(x: u8, y: u8) {}

fn main() {
    let first_arg = 3;
    let second_arg = 4;
    foo(x: first_arg, y: second_arg);
    let x = 1;
    let y = 2;
    foo(:x, :y)
}
~~~



#### 语句与表达式

* 语句：执行一些操作的指令，没有返回值

  ~~~rust
  let y = 6;
  ~~~

* 表达式：进行求值并得到结果值。可以是一行代码，也可以是代码块。**末尾没有分号**。

  ~~~rust
  let y = {
    let x = 3;
    x + 1
  };
  ~~~



#### 方法返回值

在`Cairo`中，在函数签名后面的`->`之后来声明返回值类型

~~~rust
fn plus_one(x: u32) -> u32 {
    x + 1
}
~~~



### 2024.09.21

#### 注释

* 普通注释：以`//`开头

  ~~~rust
  fn main() -> felt252 {
      // this function performs a simple addition
      1 + 4
  }
  ~~~

* 项目级文档：以`///`开头。提供项目的详细描述，比如用法、任何可能造成`panic`的条件

  ~~~rust
  /// Returns the sum of `arg1` and `arg2`.
  /// `arg1` cannot be zero.
  ///
  /// # Panics
  ///
  /// This function will panic if `arg1` is `0`.
  ///
  /// # Examples
  ///
  /// ```
  /// let a: felt252 = 2;
  /// let b: felt252 = 3;
  /// let c: felt252 = add(a, b);
  /// assert(c == a + b, "Should equal a + b");
  /// ```
  fn add(arg1: felt252, arg2: felt252) -> felt252 {
      assert(arg1 != 0, 'Cannot be zero');
      arg1 + arg2
  }
  ~~~

* 模块级文档：以`//!`开头。提供整个模块的概述，包括其意图和用例。这种文档类型通常描述模块是做什么的以及如何使用。

  ~~~rust
  //! # my_module and implementation
  //!
  //! This is an example description of my_module and some of its features.
  //!
  //! # Examples
  //!
  //! ```
  //! mod my_other_module {
  //!   use path::to::my_module;
  //!
  //!   fn foo() {
  //!     my_module.bar();
  //!   }
  //! }
  //! ```
  mod my_module { // rest of implementation...
  }
  ~~~

  

<!-- Content_END -->
