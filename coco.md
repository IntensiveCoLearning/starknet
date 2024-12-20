---
timezone: Pacific/Auckland
---

---

# River

1. 自我介绍

   有 3 年全栈软件开发经验，熟悉 Java、Go、JS、Rust、Solidity 等开发语言。目前有考虑在 Starknet 上构建项目的想法，因此来学习 Starknet 相关开发知识。

2. 你认为你会完成本次残酷学习吗？

   一定会完成。

## Notes

<!-- Content_START -->

### 2024.09.18

#### 1. 环境准备

1. 编程语言

   - `Cairo`: 通过下载`Scarb`即可安装使用

2. 编码环境

   - `asdf`: 是一个工具版本管理器，能以项目为维度管理多种编程语言的运行时版本

   - `Scarb`: 是`Cairo`的包管理器，将`Cairo`编译器和`Cairo`语言服务器打包到了一起

#### 2. 安装环境

操作系统：MacOS Big Sur

1. 安装`asdf`

   1. 安装依赖`coreutils`、`curl`、`git`，如果已经安装过了就无需再安装

      `brew install coreutils curl git`

   2. 下载`asdf`

      - 官方下载方式：

        `git clone https://github.com/asdf-vm/asdf.git ~/.asdf --branch {version}`

      - 使用`MacOS`自带工具下载：

        `brew install asdf`

   3. 安装`asdf`

      - 使用的官方的下载方式

        安装时需要在`~/.bash_profile`文件下添加以下配置：

        ```shell
        . "$HOME/.asdf/asdf.sh"
        . "$HOME/.asdf/completions/asdf.bash"
        ```

      - 使用`brew`方式安装

        安装完成后会提示设置环境变量

        ```shell
        To use asdf, add the following line (or equivalent) to your shell profile
        e.g. ~/.profile or ~/.zshrc:
          . /opt/homebrew/opt/asdf/libexec/asdf.sh
        e.g. ~/.config/fish/config.fish
          source /opt/homebrew/opt/asdf/libexec/asdf.fish
        Restart your terminal for the settings to take effect.
        ```

   4. 验证

      执行`source ~/.bash_profile `使上面的配置生效

      执行`asdf --version`后，显示以下内容：

      ```shell
      v0.14.1-f00f759
      ```

2. 安装`Scarb`

   **通过`asdf`安装**

   1. 添加`scarb`插件

      ```shell
      asdf plugin add scarb
      ```

   2. 查看所有可安装的版本

      ```shell
      asdf list-all scarb
      ```

   3. 安装指定版本

      ```shell
      # 安装最新版本
      asdf install scarb latest

      # 或者根据版本号安装
      asdf install scarb 2.8.2
      ```

   4. 设置全局版本

      ```shell
      asdf global scarb latest
      ```

   **通过`curl`命令安装**

   ```shell
   curl --proto '=https' --tlsv1.2 -sSf https://docs.swmansion.com/scarb/install.sh | sh
   ```

### 2024.09.19

#### 变量与可变性

- `Cairo`使用的是**不可变性**的内存模型，一旦写入内存块后就**只读**，不能被重写。

声明的变量默认是**不可变**的。

如果需要声明可变的变量，需要使用关键字`mut`显示指定，例如：

```rust
let mut x = 7;
```

#### 常量

声明常量使用关键字`const`，例如：

```rust
const ONE_HOUR_IN_SECONDS: u32 = 3600;
```

- 常量和变量的区别：
  - 相同：默认都是不可变的
  - 不同：常量不可使用关键字`mut`修饰

#### 变量遮蔽

在不同的**作用域**之间，声明多个**同名变量**，后声明的变量在其**作用域内**会遮蔽前面声明的变量。

- 变量遮蔽和可变变量在底层上是等价的，不同的地方在于通过变量遮蔽可以修改变量的类型。

##### 💡 建议

（来自`Rust`编码规范）

变量遮蔽功能在功能上属于一种继承式可变。他会覆盖之前的变量绑定，而创建一个新的同名的变量绑定。

1. 在同一个作用域中，非必要时不宜通过新变量声明遮蔽旧变量声明的方式来修改变量。
2. 在子作用域内修改“哨兵变量”时，应该避免使用变量遮蔽功能，防止引起逻辑 bug。
3. 如果使用变量遮蔽，禁止用不同类型的变量遮蔽前一个变量，如果实现同一个 `trait` 的可以例外。

### 2024.09.20

#### 数据类型

在`Cairo`中，每个值都有明确的数据类型。

- `Cairo`是一门**静态类型语言**，意味着在编译期就要知道所有变量的类型。

##### 标量类型（Scalar Types）

标量类型代表的是单个值，有三个主要的标量类型：`felts`、`integers`、`booleans`

###### Felt Type

如果变量或者参数没有被指定明确的类型，它的类型默认是一个`field element`，用关键字`felt252`表示。

- `field element`：一个在$0 \leq x < P$范围内的整型。其中`P`是一个非常大的素数，目前等于$2^{251} + 17 * 2^{192} + 1$。如果数值在做加法、减法、或者乘法时，结果的大小超过这个范围，则对`P`进行模运算。

- `integers`与`field elements`最重要的区别在于除法：`integers`的除法结果是向下取整，不一定满足$\frac{x}{y} * y == x$。而`field elements`总是满足这一等式。

###### Integer Types

在任何时候都建议使用`integer`类型，而不是`felt252`类型，因为`integer`类型有额外的安全特征来避免代码中潜在的安全隐患，比如上溢和下溢检查。

###### Boolean Types

使用`true`和`false`这两个字面量作为值，`Boolean`类型的大小为一个`felt252`。声明时使用关键字`bool`。

###### String Types

`Cairo`中没有为字符串提供原生类型。短字符串使用单引号表示，`ByteArray`字符串使用双引号表示

- 短字符串：是`ASCII`码字符串。每个字符编码为**一个字节**。

  `Cairo`中字符串的类型使用`felt252`，由于`felt252`有 251 比特大小，因此一个短字符串的大小不能超过**31 个字符**（$31 * 8 = 248bi$t）

- `ByteArray`字符串：使用`ByteArray`类型来处理超过短字符串大小的字符串和字节序列。

  `ByteArray`的实现有两部分组成：

  1. 一个`bytes31`个字的数组，其中每个字包含 31 个字节的数据
  2. 一个待定的`felt252`的字作为尚未填满完整`bytes31`个字的字节缓冲区

##### 复合类型（Compounds Types）

###### 元组类型（Tuple Type）

一个元组是将许多的多种类型的变量分组为一个复合类型的通用方法。元组的长度是固定的，一旦声明后，其大小无法增加或者减少。

```rust
fn main() {
    let tup: (u32, u64, bool) = (10, 20, true);

  	let (x, y, z) = tup;

    if y == 6 {
        println!("y is 6!");
    }

  	let (a, b): (felt252, felt252) = (2, 3);
}
```

**Unit Type**

一个单元类型只有一个值`()`。它表示一个没有元素的元组，它的大小总是 0。在编译的代码中是不存在的。

###### 大小固定的数组类型

一个大小固定的数组是一个包含多个值的集合，其中每个值的类型必须相同。

```rust
fn main() {
    let arr1: [u64; 5] = [1, 2, 3, 4, 5];

    // [3, 3, 3, 3, 3]
  	let arr2 = [3; 5];
}
```

##### 类型转换

###### Into

`Into`特征允许一个类型来定义如何转换为另一种类型。可以被用于确保能转换成功的类型转换。

执行变量的`into()`方法进行类型转换。转换的变量的类型必须显式声明

```rust
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
```

###### TryInto

功能与`Into`一样用于类型转换，不同的地方在于，`TryInto`在可能会转换失败的场景下使用，返回`Option<T>`，需要使用`unwrap()`方法获取转换后的变量值。

```rust
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
```

### 2024.09.21

#### 函数

使用关键字`fn`声明一个函数。

函数的名称格式通常是下划线格式。如：

```rust
fn another_function() {
    println!("Another function.");
}
```

#### 参数

参数是函数签名的一部分。在函数签名中，必须声明参数的类型。

```rust
fn print_labeled_measurement(value: u128, unit_label: ByteArray) {
    println!("The measurement is: {value}{unit_label}");
}
```

#### 命名参数（Named Parameters）

在`Cairo`中，当调用函数时，可以指定参数的名称。可以让函数调用有可读性和自描述性。

语法：`parameter_name: value`，如果传递的变量与参数的名称一样时，可以简写为`:parameter_name`。

```rust
fn foo(x: u8, y: u8) {}

fn main() {
    let first_arg = 3;
    let second_arg = 4;
    foo(x: first_arg, y: second_arg);
    let x = 1;
    let y = 2;
    foo(:x, :y)
}
```

#### 语句与表达式

- 语句：执行一些操作的指令，没有返回值

  ```rust
  let y = 6;
  ```

- 表达式：进行求值并得到结果值。可以是一行代码，也可以是代码块。**末尾没有分号**。

  ```rust
  let y = {
    let x = 3;
    x + 1
  };
  ```

#### 方法返回值

在`Cairo`中，在函数签名后面的`->`之后来声明返回值类型

```rust
fn plus_one(x: u32) -> u32 {
    x + 1
}
```

### 2024.09.22

#### 注释

- 普通注释：以`//`开头

  ```rust
  fn main() -> felt252 {
      // this function performs a simple addition
      1 + 4
  }
  ```

- 项目级文档：以`///`开头。提供项目的详细描述，比如用法、任何可能造成`panic`的条件

  ````rust
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
  ````

- 模块级文档：以`//!`开头。提供整个模块的概述，包括其意图和用例。这种文档类型通常描述模块是做什么的以及如何使用。

  ````rust
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
  ````

### 2024.09.23

#### 流程控制

##### if 表达式

###### 常规写法

```rust
fn main() {
    let number = 3;

    if number == 12 {
        println!("number is 12");
    } else if number == 3 {
        println!("number is 3");
    } else if number - 2 == 1 {
        println!("number minus 2 is 1");
    } else {
        println!("number not found");
    }
}
```

###### 在 let 语句中使用 if

```rust
fn main() {
    let condition = true;
    let number = if condition {
        5
    } else {
        6
    };
}
```

##### 循环控制

在`Cairo`中有三种 Loop 循环类型：`loop`、`while`、`for`

###### `loop`

- 常规

  ```rust
  fn main() {
      loop {
          println!("again!");
      }
  }
  ```

- 带有`break`关键字

  ```rust
  fn main() {
      let mut i: usize = 0;
      loop {
          if i > 10 {
              break;
          }
          println!("i = {}", i);
          i += 1;
      }
  }
  ```

- 带有`continue`关键字

  ```rust
  fn main() {
      let mut i: usize = 0;
      loop {
          if i > 10 {
              break;
          }
          if i == 5 {
              i += 1;
              continue;
          }
          println!("i = {}", i);
          i += 1;
      }
  }
  ```

- 带有返回值

  ```rust
  fn main() {
      let mut counter = 0;

      let result = loop {
          if counter == 10 {
              break counter * 2;
          }
          counter += 1;
      };

      println!("The result is {}", result);
  }
  ```

###### `while`

```rust
fn main() {
    let mut number = 3;

    while number != 0 {
        println!("{number}!");
        number -= 1;
    };

    println!("LIFTOFF!!!");
}
```

###### `for`

```rust
fn main() {
    let a = [10, 20, 30, 40, 50].span();

    for element in a {
        println!("the value is: {element}");
    }

  	for number in 1..4_u8 {
        println!("{number}!");
    };
}
```

###### Loops 与递归

Loops 和递归是两种重复执行代码的方式。

- `loop`关键字用来创建一个无限循环，同时使用`break`关键字退出循环。

  ```rust
  fn main() -> felt252 {
      let mut x: felt252 = 0;
      loop {
          if x == 2 {
              break;
          } else {
              x += 1;
          }
      };
      x
  }
  ```

- 递归通过在函数内部调用自身来实现

  ```rust
  fn main() -> felt252 {
      recursive_function(0)
  }

  fn recursive_function(mut x: felt252) -> felt252 {
      if x == 2 {
          x
      } else {
          recursive_function(x + 1)
      }
  }
  ```

在`Cairo`中，Loops 与递归不仅仅在概念上是等价的，同时通过编译在底层表达上也类似。

### 2024.09.24

#### 数组

数组是一系列具有相同类型的元素的集合。可以使用核心库的特征`ArrayTrait`来创建和使用数组。

⚠️ 数组是一种队列，里面的值无法修改。事实上一旦写入到内存槽中就无法重写，只能读取。在数组中，只能在最后添加元素，以及从前面删除元素。

###### 创建数组

- `ArrayTrait::new()`
- `ArrayTrait::<T>::new();`

```rust
fn main() {
    let mut a = ArrayTrait::new();
    a.append(0);
    a.append(1);
    a.append(2);

  	let mut arr1 = ArrayTrait::<u128>::new();

		let mut arr2:Array<u128> = ArrayTrait::new();
}
```

###### 更新数组

- 添加元素：`append()`

- 删除元素：`pop_front()`。会返回`Option`，使用`unwrap()`获取删除的元素，如果返回`Option::None`表示数组是空的

  ```rust
  fn main() {
      let mut a = ArrayTrait::new();
      a.append(10);
      a.append(1);
      a.append(2);

      let first_value = a.pop_front().unwrap();
      println!("The first value is {}", first_value);
  }
  ```

###### 读取数组

- `get()`：返回`Option<Box<@T>>`，如果元素不存在则返回 None，
- `at()`：`arr.at(index)`和`arr[index]`等价，如果下标益处则会 Panic

###### 容量相关的方法

- `len()`：确定数组的元素个数，返回`usize`类型的值
- `is_empty()`：判断数组是否为空

###### `array!`Macro

如果需要创建在编译期就能确定值的数组时，可以使用`array!`来简化创建带有元素的数组

```rust
let arr = array![1, 2, 3, 4, 5];
```

###### 存储多种类型

可以使用`Enum`自定义的数据类型在数组中存储多种数据类型

```rust
#[derive(Copy, Drop)]
enum Data {
    Integer: u128,
    Felt: felt252,
    Tuple: (u32, u32),
}

fn main() {
    let mut messages: Array<Data> = array![];
    messages.append(Data::Integer(100));
    messages.append(Data::Felt('hello world'));
    messages.append(Data::Tuple((10, 30)));
}
```

###### `Span`

`Span`是一种表示数组快照的结构。

用来在不修改原数组的前提下，提供数组中元素的安全以及访问控制。

在函数间传递数组或者执行只读操作的时候，保证数据完整性和避免借用问题时非常有用。

使用方法：`array.span()`

### 2024.09.25

#### 字典

##### 字典的基础用法

在`Cairo`中，键的类型被限制为`felt252`，只能指定值的数据类型，在`Felt252Dict<T>`中由`T`表示。

`Felt252Dict<T>`的核心功能实现于特征`Felt252DictTrait`，其中包含所有基础的操作：

1. `insert(felt252, T) -> ()`：写入值到字典实例中
2. `get(felt252) -> T`：从字典中读取值

🌰 例子：创建一个字典来表示个人与余额之间的映射：

```rust
use core::dict::Felt252Dict;

fn main() {
    let mut balances: Felt252Dict<u64> = Default::default();

    balances.insert('Alex', 100);
    balances.insert('Maria', 200);

    let alex_balance = balances.get('Alex');
    assert!(alex_balance == 100, "Balance is not 100");

    let maria_balance = balances.get('Maria');
    assert!(maria_balance == 200, "Balance is not 200");
}
```

💡 尽管在`Cairo`中内存是不可变的，意味着一个内存单元只能写入一次，但是`Felt252Dict<T>`类型展示了一种克服这个障碍的方法。

使用上面的例子，对其中的一个用户修改其余额：

```rust
use core::dict::Felt252Dict;

fn main() {
    let mut balances: Felt252Dict<u64> = Default::default();

    // Insert Alex with 100 balance
    balances.insert('Alex', 100);
    // Check that Alex has indeed 100 associated with him
    let alex_balance = balances.get('Alex');
    assert!(alex_balance == 100, "Alex balance is not 100");

    // Insert Alex again, this time with 200 balance
    balances.insert('Alex', 200);
    // Check the new balance is correct
    let alex_balance_2 = balances.get('Alex');
    assert!(alex_balance_2 == 200, "Alex balance is not 200");
}
```

`Felt252Dict<T>`允许“重写”任何键对应的值。

当实例化`Felt252Dict<T>`后，所有的键关联的值被实例化为 0。意味着如果读取一个不存在的数据则会返回 0，而不是错误或者未定义的值。也意味着无法从字典中删除数据。

### 2024.09.26

##### 字典底层结构

`Cairo`使用 Entry 列表来实现`Felt252Dict<T>`。每个 Entry 表示一条可以进行读取、更新、写入操作的记录。

Entry 结构包含三个值：

1. `key`：用于识别字典的键值对
2. `previous_value`：表示`key`的前一个值
3. `new_value`：表示`key`更新的值

如果使用高级结构来实现`Felt252Dict<T>`， 可以定义`Array<Entry<T>>`，`Entry<T>`的结构可以是：

```rust
struct Entry<T> {
    key: felt252,
    previous_value: T,
    new_value: T,
}
```

每一次与`Felt252Dict<T>`交互，就会注册一个新的`Entry<T>`：

1. `get`操作将注册一个状态未改变的 entry，然后`previous_value`和`new_value`存储为同一个值。
2. `insert`操作将注册一个新的`Entry<T>`，`new_value`为写入的值，`previous_value`则是写入操作之前的值，如果是第一次写入，则为 0。

使用 Entry 列表展示了为何不存在重写，仅仅是在每次与`Felt252Dict<T>`交互创建一个新的内存单元。

🌰 例子：分别更新字典 balance 的'Alex'和'Maria'两个值：

```rust
balances.insert('Alex', 100_u64);
balances.insert('Maria', 50_u64);
balances.insert('Alex', 200_u64);
balances.get('Maria');
```

上面的操作将产生如下 entry 列表：

|  key  | previous | new |
| :---: | :------: | :-: |
| Alex  |    0     | 100 |
| Maria |    0     | 50  |
| Alex  |   100    | 200 |
| Maria |    50    | 50  |

这种实现方式意味着每次读取或者写入操作，都会遍历整个 entry 列表来查找与`key`相同的最近的那个 entry。一旦找到对应的 entry，它的`new_value`会被提取出来，并添加到新的 entry 的`previous_value`中。

与常规语言不同，`Cairo`的目的之一是使用 STARK 证明系统生成计算完整性的证明。这意味着需要验证程序的执行是正确的，并且在`Cairo`限制的范围内。其中一个边界检查包括“**字典压缩**”（dictionary squashing），它需要每个条目的旧值和新值的信息。

### 2024.09.27

#### 字典压缩

为了验证`Cairo`程序使用`Felt252Dict<T>`执行生成的证明是正确的，需要检查字典没有被非法篡改。这里通过`squash_dict`方法来实现，该方法检查 entry 列表中的每个 entry，并且检查对字典的访问在整个执行过程中是否保持一致。

压缩过程：给定所有键为 k 的 entry，按照插入顺序，验证第 i 个 entry 的`new_value`是否等于第 i+1 个 entry 的`previous_value`。

🌰 例子：给定一张 entry 列表：

|   key   | previous | new |
| :-----: | :------: | :-: |
|  Alex   |    0     | 150 |
|  Maria  |    0     | 100 |
| Charles |    0     | 70  |
|  Maria  |   100    | 250 |
|  Alex   |   150    | 40  |
|  Alex   |    40    | 300 |
|  Maria  |   250    | 190 |
|  Alex   |   300    | 90  |

在压缩之后，entry 列表将为精简为：

|   key   | previous | new |
| :-----: | :------: | :-: |
|  Alex   |    0     | 90  |
|  Maria  |    0     | 190 |
| Charles |    0     | 70  |

如果第一张表的值有任何修改，在运行时压缩操作将会失败。

#### 字典解构

当运行“字典的基础用法”一节中的例子时，并不会执行字典压缩的操作，但是程序还是会编译成功。这是因为压缩操作会通过`Felt252Dict<T>`所实现的`Destruct<T>`特征来自动调用，这个调用仅仅在字典离开其作用域前执行

### 2024.09.28

#### 字典的`Entry`和`Finalize`

`Cairo`提供了`entry`和`finalize`方法来复制字典数据。

- `entry`：通过给定的`key`来创建一个新的 entry。一旦被调用，这个方法会获得字典的所有权，并返回要更新的 entry。方法签名如下：

  ```rust
  fn entry(self: Felt252Dict<T>, key: felt252) -> (Felt252DictEntry<T>, T) nopanic
  ```

  第一个参数来获取字典的所有权，第二个参数是用来创建合适的 entry。该方法返回一个元组：`Felt252DictEntry<T>`表示字典的 entry，`T`表示 entry 的前一个值。`nopanic`表示该方法不会发生 panic

- `finalize`：向字典中插入 entry，并返回其所有权。方法签名如下：

  ```rust
  fn finalize(self: Felt252DictEntry<T>, new_value: T) -> Felt252Dict<T>
  ```

🌰 例子：

自定义`get`方法：

```rust
use core::dict::{Felt252Dict, Felt252DictEntryTrait};

fn custom_get<T, +Felt252DictValue<T>, +Drop<T>, +Copy<T>>(
    ref dict: Felt252Dict<T>, key: felt252
) -> T {
    // Get the new entry and the previous value held at `key`
    let (entry, prev_value) = dict.entry(key);

    // Store the value to return
    let return_value = prev_value;

    // Update the entry with `prev_value` and get back ownership of the dictionary
    dict = entry.finalize(prev_value);

    // Return the read value
    return_value
}
```

自定义`insert`方法：

```rust
use core::dict::{Felt252Dict, Felt252DictEntryTrait};

fn custom_insert<T, +Felt252DictValue<T>, +Destruct<T>, +Drop<T>>(
    ref dict: Felt252Dict<T>, key: felt252, value: T
) {
    // Get the last entry associated with `key`
    // Notice that if `key` does not exist, `_prev_value` will
    // be the default value of T.
    let (entry, _prev_value) = dict.entry(key);

    // Insert `entry` back in the dictionary with the updated value,
    // and receive ownership of the dictionary
    dict = entry.finalize(value);
}
```

使用上面自定义的`get`和`insert`方法：

```rust
fn main() {
    let mut dict: Felt252Dict<u64> = Default::default();

    custom_insert(ref dict, '0', 100);

    let val = custom_get(ref dict, '0');

    assert!(val == 100, "Expecting 100");
}
```

### 2024.09.29

#### 原生不支持的类型的字典

​ 使用`Felt252Dict<T>`其中的一条限制来自`Felt252DictValue<T>`特征。这个特征定义了`zero_default`方法，当一个值在字典中不存在时会调用该方法。只有部分公共数据类型（比如大多数的无符号整型、`bool`和`felt252`）实现了该方法。但是一些更复杂的类型（数组、结构包括`u256`）则没有实现。

​ 如果要创建原生不支持的类型的字典时，需要手动实现一些特征，来让这些数据类型有合法的字典值类型，可以使用`Nullable<T>`来包装数据类型。`Nullable<T>`是一个智能指针类型，它能指向一个值或者值不存在时为`null`。

🌰 例子：将`Span<felt252>`存储到字典中（使用`Span<T>`而不是`Array<T>`的原因是后者没有实现字典的读取操作所需要的`Copy<T>`特征）

```rust
use core::dict::Felt252Dict;
use core::nullable::{NullableTrait, match_nullable, FromNullableResult};

fn main() {
    // Create the dictionary
    let mut d: Felt252Dict<Nullable<Span<felt252>>> = Default::default();

    // Create the array to insert
    let a = array![8, 9, 10];

    // Insert it as a `Span`
    d.insert(0, NullableTrait::new(a.span()));

    // Get value back
    let val = d.get(0);

    // Search the value and assert it is not null
    let span = match match_nullable(val) {
        FromNullableResult::Null => panic!("No value found"),
        FromNullableResult::NotNull(val) => val.unbox(),
    };

    // Verify we are having the right values
    assert!(*span.at(0) == 8, "Expecting 8");
    assert!(*span.at(1) == 9, "Expecting 9");
    assert!(*span.at(2) == 10, "Expecting 10");
}
```

### 2024.09.30

#### 使用字典存储数组

- 插入操作：简单，与插入其他类型的数据相似

  ```rust
  use core::dict::Felt252Dict;

  fn main() {
      let arr = array![20, 19, 26];
      let mut dict: Felt252Dict<Nullable<Array<u8>>> = Default::default();
      dict.insert(0, NullableTrait::new(arr));
      println!("Array inserted successfully.");
  }
  ```

- 读取操作：使用`get`方法读取字典会在编译时报错。因为`get`方法会尝试在内存中复制数组，但是`Array<T>`没有实现`Copy<T>`特征，无法进行复制操作。

  ```rust
  use core::nullable::{match_nullable, FromNullableResult};
  use core::dict::Felt252Dict;

  fn main() {
      let arr = array![20, 19, 26];
      let mut dict: Felt252Dict<Nullable<Array<u8>>> = Default::default();
      dict.insert(0, NullableTrait::new(arr));
      println!("Array: {:?}", get_array_entry(ref dict, 0));
  }

  fn get_array_entry(ref dict: Felt252Dict<Nullable<Array<u8>>>, index: felt252) -> Span<u8> {
      let val = dict.get(0); // This will cause a compiler error
      let arr = match match_nullable(val) {
          FromNullableResult::Null => panic!("No value!"),
          FromNullableResult::NotNull(val) => val.unbox()
      };
      arr.span()
  }
  ```

  正确的读取方式需要使用到字典的 entry，这样可以获取数组的引用而不需要进行复制。

  ```rust
  fn get_array_entry(ref dict: Felt252Dict<Nullable<Array<u8>>>, index: felt252) -> Span<u8> {
      let (entry, _arr) = dict.entry(index);
      let mut arr = _arr.deref_or(array![]);
      let span = arr.span();
      dict = entry.finalize(NullableTrait::new(arr));
      span
  }
  ```

- 修改操作：同样使用字典的 entry 进行操作

  ```rust
  fn append_value(ref dict: Felt252Dict<Nullable<Array<u8>>>, index: felt252, value: u8) {
      let (entry, arr) = dict.entry(index);
      let mut unboxed_val = arr.deref_or(array![]);
      unboxed_val.append(value);
      dict = entry.finalize(NullableTrait::new(unboxed_val));
  }
  ```

### 2024.10.01

#### 线性类型系统的所有权

​ 在线性类型系统中，任何值（基础类型、结构体、枚举等）必须被使用，且仅被使用一次。“使用”的意思是值被销毁或者被转移。

- **解构**(Destruction)在下面几种情况下会发生：

  1. 变量在作用域之外
  2. 结构体被解构
  3. 调用`destruct()`显式解构

- **移动**一个值仅仅表示将值传递到另一个函数

​ 这些约束与`Rust`的所有权模型有些类似，但有些不同。不同之处在于，`Rust`的所有权模型的存在(部分)是为了避免数据冲突与对内存值的并发可变访问。而在`Cairo`中内存是**不可变**的。

`Cairo`使用线性类型系统的两个主要目的：

1.  确保所有的代码是可证明，因此是可验证的。

        2. 抽象掉`Cairo VM`的不可变内存。（为什么要进行抽象，如何进行抽象的？）

#### 所有权

在`Cairo`中，所有权应用与变量而不是值。因为值本身总是不可变的，而变量可以是可变的，因此编译器必须保证常量不能被编程者意外地修改。

​ 一句话概括所有权：所有者就是能够读取（以及写入，如果是可变的）变量的代码。

- 变量遵循以下类似`Rust`语言的规则：

1. 每一个变量都有一个所有者
2. 同一时刻只有一个所有者
3. 所有者超出作用域时，变量将被销毁

### 2024.10.02

#### 所有权

##### 移动变量

移动一个值只是将其传递给另一个函数。在原有的作用域下引用这个值的变量会被销毁，并且不能再被使用，同时一个新的变量被创建来持有相同的值。

🌰 例子：

```rust
fn foo(mut arr: Array<u128>) {
    arr.pop_front();
}

fn main() {
    let mut arr: Array<u128> = array![];
    foo(arr);
    foo(arr);
}
```

例子中`arr`变量中的数组会传递到`foo()`函数两次，将会对同一个存储单元写入两次，这是`Cairo`不允许发生的，会导致运行时错误。会提示：

```shell
note: Trait has no implementation in context: core::traits::Copy::<core::array::Array::<core::integer::u128>>.
```

一旦将数组传递到`foo()`后，变量`arr`将不是可使用的。运行时错误会提示需要实现`Copy`特征。

### 2024.10.03

#### `Copy`特征

`Copy`特征可以在不需要分别新的内存块的情况下，通过复制 felts 来实现对简单类型的复制。

- copy 和 move 对比：
  - `Cairo`默认的”移动“语义是转移值的所有权来确保内存安全以及避免多次写入相同内存单元的问题。
  - `Copy`是为安全且高效的类型复制而实现的，避免直接使用移动语义。

​ 像`Array`和`Felt252Dict`这种类型是不能实现`Copy`特征，因为在不同的作用域操作他们是被类型系统所禁止的。

​ 在前面”数据类型“一节提到的所有的基础类型默认实现了`Copy`特征。

​ 数组和字典是不能被复制的，但是不包含这两种类型的自定义类型是可被复制的。可以在类型定义上面加上`#[derive(Copy)]`注解来实现`Copy`特征。如果类型本身或者其组成的类型没有实现`Copy`特征，那么不允许使用 Copy 注解。

🌰 例子：

```rust
#[derive(Copy, Drop)]
struct Point {
    x: u128,
    y: u128,
}

fn main() {
    let p1 = Point { x: 5, y: 10 };
    foo(p1);
    foo(p1);
}

fn foo(p: Point) { // do something with p
}
```

在上面的例子中，能将`p1`两次传递到`foo`函数，是因为`Point`类型实现了`Copy`特征。这意味着将`p1`传递到`foo`

函数，实际上传递的是`p1`的副本，因此`p1`仍然有效。从所有权角度来讲，`p1`的所有权仍然属于`main`函数。如果移除`Point`类型上`Copy`特征的注解，在编译时就会产生编译期错误。

🤔️ 疑问：

1. 对于像`Array`和`Felt252Dict`这种类型如何在函数间传递？

### 2024.10.04

#### 值的销毁

​ 线性类型其他的使用方式是销毁操作。销毁时必须确保“资源”被正确地释放掉。在`Rust`中可以是文件访问的关闭或者对互斥量加锁。在`Cairo`中`Felt252Dict`类型具有这样的行为。为了可验证性，字典在被销毁时必须被“压缩”。这个很容易被忽视，因此由类型系统和编译器执行。

#### `Drop`特征

​ 实现了`Drop`特征的类型在超出作用域时会自动被销毁。这种销毁不做任何事，他是无操作的(no-op)，仅仅提示编译器这个类型一旦不被再使用就能够被安全地销毁。称之为“dropping”.

​ `Drop`特征除了字典(`Felt252Dict`)和包含字典的类型，其他的所有类型都可以通过`Drop`实现派生。

```rust
#[derive(Drop)]
struct A {}

fn main() {
    A {}; // Now there is no error.
}
```

#### `Destruct`特征

​ 当一个值被销毁时，编译器首先尝试调用`drop`方法，如果不存在，则编译器尝试调用`destruct`方法，这个方法有`Destruct`特征提供。

​ 在`Cairo`中字典类型在销毁时必须被“压缩”，以便访问顺序可以被证明。由于开发者容易忘记这一点，因此字典实现了`Destruct`特征来确保所有的字典在超出作用域时被压缩。

🌰 例子：

下面代码中，结构体`A`中包含类型`Felt252Dict`，但没有实现`Destruct`特征，编译将会报错

```rust
use core::dict::Felt252Dict;

struct A {
    dict: Felt252Dict<u128>
}

fn main() {
    A { dict: Default::default() };
}
```

正确写法应当为结构体`A`实现`Destruct`特征

```rust
use core::dict::Felt252Dict;

#[derive(Destruct)]
struct A {
    dict: Felt252Dict<u128>
}

fn main() {
    A { dict: Default::default() }; // No error here
}
```

### 2024.10.05

#### 使用`clone`复制数组

如果想要深拷贝数组，可以使用公共方法`clone`。

🌰 例子：

```rust
fn main() {
    let arr1: Array<u128> = array![];
    let arr2 = arr1.clone();
}
```

`arr1`指向的值被复制，会使用新的内存单元，并且新的值`arr2`被创建并指向复制的值。

#### 返回值与作用域

返回值等价于移动值

🌰 例子：

```rust
#[derive(Drop)]
struct A {}

fn main() {
    let a1 = gives_ownership();           // gives_ownership moves its return
                                          // value into a1

    let a2 = A {};                        // a2 comes into scope

    let a3 = takes_and_gives_back(a2);    // a2 is moved into
                                          // takes_and_gives_back, which also
                                          // moves its return value into a3

} // Here, a3 goes out of scope and is dropped. a2 was moved, so nothing
  // happens. a1 goes out of scope and is dropped.

fn gives_ownership() -> A {               // gives_ownership will move its
                                          // return value into the function
                                          // that calls it

    let some_a = A {};                    // some_a comes into scope

    some_a                                // some_a is returned and
                                          // moves ownership to the calling
                                          // function
}

// This function takes an instance some_a of A and returns it
fn takes_and_gives_back(some_a: A) -> A { // some_a comes into scope

    some_a                                // some_a is returned and
                                          // moves ownership to the calling
                                          // function
}
```

虽然这段代码可以运行，但是将值移动到函数中并移出来会有些繁琐。任何传进去的东西，只要还要再次使用，则需要传回来。下面是使用元组返回多个值：

```rust
fn main() {
    let arr1: Array<u128> = array![];

    let (arr2, len) = calculate_length(arr1);
}

fn calculate_length(arr: Array<u128>) -> (Array<u128>, usize) {
    let length = arr.len(); // len() returns the length of an array

    (arr, length)
}
```

🤔️ 如果想要函数仅使用值但不进行移动应该怎么办？

`Cairo`有两种方式在传递值的同时无需销毁或者移动——`references`和`snapshots`

### 2024.10.06

​ `Cairo`的所有权系统防止在变量移动后再次被使用，避免在同一个内存单元写入多次。但是这样并不是很便利。因此提供了快照的方式在调用函数时保留变量的所有权。

​ 快照是一个变量在某个时间点上的**不可变视图**。要知道内存时不可变的，因此**修改一个值实际上是创建一个新的内存单元**。旧的内存单元依旧存在，快照是指向“旧”值的变量。

🌰 例子：

```rust
fn main() {
    let mut arr1: Array<u128> = array![];
    let first_snapshot = @arr1; // Take a snapshot of `arr1` at this point in time
    arr1.append(1); // Mutate `arr1` by appending a value
    let first_length = calculate_length(
        first_snapshot
    ); // Calculate the length of the array when the snapshot was taken
    let second_length = calculate_length(@arr1); // Calculate the current length of the array
    println!("The length of the array when the snapshot was taken is {}", first_length);
    println!("The current length of the array is {}", second_length);
}

fn calculate_length(arr: @Array<u128>) -> usize {
    arr.len()
}

// 打印结果
// The length of the array when the snapshot was taken is 0
// The current length of the array is 1
```

​ 上面例子中，`calculate_length`函数是将`arr`的快照而不是底层值的所有权作为参数。当传递的参数是快照时，也就是数组的不可变视图，就能保证`calculate_length`函数不会修改数组，并且数组的所有权依旧在`main`函数中。

⚠️ 只能调用数组快照的`len()`方法，因为它在`ArrayTrait`特征中定义了。如果尝试调用快照中一个没有为快照定义过的方法时就会编译出错。但是可以在非快照类型上调用一个期望成为快照的方法。

- 语法：使用`@`创建值的快照

​ 由于快照是一个值在特定时间点的不可变视图，因此线性类型系统的常用规则不会生效。特别是，快照变量总是实现了`Drop`特征，而不是`Destruct`特征，即使是字典快照也是这样的。

​ 对于使用快照参数的函数的返回值，也无需返回参数的所有权，因为这个函数从未拥有快照参数的所有权。

### 2024.10.07

#### `desnap`操作符

​ 使用`desnap`操作符`*`可以将快照变量转换为常规变量，它的作用与快照操作符`@`相反。

​ 只有`Copy`类型可以被解快照。在通常情况下，因为值是不能被修改的，通过`desnap`操作符创建的新变量会重用旧的值，所以解快照是完全自由的操作，就像`Copy`一样。

🌰 例子：

```rust
#[derive(Drop)]
struct Rectangle {
    height: u64,
    width: u64,
}

fn main() {
    let rec = Rectangle { height: 3, width: 10 };
    let area = calculate_area(@rec);
    println!("Area: {}", area);
}

fn calculate_area(rec: @Rectangle) -> u64 {
    // As rec is a snapshot to a Rectangle, its fields are also snapshots of the fields types.
    // We need to transform the snapshots back into values using the desnap operator `*`.
    // This is only possible if the type is copyable, which is the case for u64.
    // Here, `*` is used for both multiplying the height and width and for desnapping the snapshots.
    *rec.height * *rec.width
}
```

如果想要在传递快照时修改一些东西会发生什么？

```rust
#[derive(Copy, Drop)]
struct Rectangle {
    height: u64,
    width: u64,
}

fn main() {
    let rec = Rectangle { height: 3, width: 10 };
    flip(@rec);
}

fn flip(rec: @Rectangle) {
    let temp = rec.height;
    rec.height = rec.width;
    rec.width = temp;
}
```

上面例子会报错：

```shell
error: Invalid left-hand side of assignment
error: could not compile `listing_04_04` due to previous error
error: `scarb metadata` exited with error
```

编译器不允许修改与快照关联的值。

### 2024.10.08

#### 可变引用

如果想要在函数中对参数相关联的值进行修改操作时，可以使用可变引用而不是快照的方式。

可变引用实际上是传递给函数的可变值，在函数结尾隐式返回值，会自动返回所有权给调用函数的上下文。

使用`ref`修饰符对传递的参数进行修饰。

⚠️ 只有用`mut`声明的可变变量才能使用`ref`修饰符进行传参。

🌰 例子：

```rust
#[derive(Drop)]
struct Rectangle {
    height: u64,
    width: u64,
}

fn main() {
    let mut rec = Rectangle { height: 3, width: 10 };
    flip(ref rec);
    println!("height: {}, width: {}", rec.height, rec.width);
}

fn flip(ref rec: Rectangle) {
    let temp = rec.height;
    rec.height = rec.width;
    rec.width = temp;
}
```

<!-- Content_END -->
