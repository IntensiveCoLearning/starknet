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

      这里使用的官方的下载方式

      因此安装时需要在`~/.bash_profile`文件下添加以下配置：

      ~~~shell
      . "$HOME/.asdf/asdf.sh"
      . "$HOME/.asdf/completions/asdf.bash"
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

<!-- Content_END -->
