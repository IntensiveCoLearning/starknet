---
timezone: Asia/Shanghai
---

# MartinYewung5
1. 自我介绍
* Martin Yeung, 來自中國香港，計算機科學+電商專業，香港城市大學理學碩士畢業，專注於區塊鏈技術研究和應用。
2. 你认为你会完成本次残酷学习吗？
* 會的。

## Notes

<!-- Content_START -->

### 2024.09.18

Starknet 是一個第2層網絡，它使用 zk-STARKs 技術使以太坊交易更快、更便宜、更安全。
將其視為以太坊之上的增強層，針對速度和成本進行了最佳化。

Starknet跨越了可擴展性和廣泛共識之間的差距，而且更整合了一個數學框架去平衡容量和包容性之間的平衡。
其完整性取決於簡潔、具透明度的計算完整性證明的穩健性。
這種方法讓強大的操作者可以增強Starknet能力，以確保每個人都可以使用通用工具來驗證 Starknet 的完整性。

Starknet 的價值
核心原則:
1. 持續開放:
Starknet 持續抵制權力整合。要點包括：
* 開放的權力分配是支持 Starknet 合法性的基礎，而且必須在經營和執行決策中持續存在。
雖然有時可能需要中心化的經營，但應該是短暫的。
* Starknet協議和治理應該一直公開和透明。
* 治理應加強包容性，及使用能夠發展的靈活結構以確保持續的包容性。

2. 中立性:
Starknet對支持社會功能方面的事情保持公正立場。
* Starknet上功能的目的和風氣是取決於它們的創建者。
* 抗審查性: Starknet對使用者交易的性質和意義會保持一個不過問的原則。

3. 個人授權:
S​​tarknet的蓬勃發展有賴於消息可以自由流通及用戶的自主權。
這會以一個習慣培養來強調可以透過培育植根於其核心使命和價值來實現的。

### 2024.09.19

Starknet的一些主要功能：
* 成本低：Starknet上的交易成本低於以太坊。
* 對開發人員友好：Starknet 讓開發人員可以使用native language - Cairo 來輕鬆地建立去中心化應用程式。
* 速度和效率：即將發布的版本會在交易上有更快的速度及更便宜的成本。
* CVM：受惠於使用Cairo，Starknet能在自己的VM上運行，稱為 Cairo VM (CVM)，
這樣使我們能夠超越以太坊虛擬機 (EVM) 進行創新，也為去中心化應用程式創建一個新的範例。

以下是其中一些例子:
* Account Abstraction: 在協議層面實現，有利於多樣化的簽名方案，同時確保用戶安全和資產的自我託管。
* Paymaster：Starknet 將允許使用者選擇如何支付交易費用，遵循 EIP 4337 中規則，允許交易指定的合約（Paymaster）來支付其交易。支援無gas fee的交易，從而便利用戶使用。

Cairo: Starknet的語言
Cairo 是一種基於 STARK 的智能合約而度身定制開發的。
作為 Starknet 的native language，它對於建立一個可擴展而且安全的去中心化應用程式十分重要。
受 Rust 啟發，Cairo 讓您可以安全、方便地編寫合約。

* 治理
Starknet 基金會負責監督 Starknet 的治理。
職責包括:
* 管理 Starknet 的開發和經營
* 監督 Starknet DAO，進一步推動社區參與
* 設定規則以維持網路的完整性
我們的重點是通過技術投入和討論來改進協議。
雖然starknet重視所有觀點，但能夠引領前進的往往是技術的洞察力。

成員可以通過投票來影響Starknet發展。
流程如下:
* 新版本在 Goerli 測試網路上進行測試。
* 成員們有六天的時間進行審查。
* 提出快照提案，讓社群對提案進行投票。
* 當贊成票佔大多數，就表示提案可以升級到主網。

實操:
首先訪問一個以開啟動Starknet插件的Remix IDE.
https://remix.ethereum.org/#activate=Starknet&lang=en&optimize=false&runs=200&evmVersion=null&version=soljson-v0.8.24+commit.e11b9ed9.js

1. 注意:
1.1 過程中可能會出現問題，例如沒有成功獲得完整的sample project.
解決 - 需要重新打開網址，再觀察是否成功獲得完整的sample project.

### 2024.09.20
實操:
首先訪問一個以開啟動Starknet插件的Remix IDE.
https://remix.ethereum.org/#activate=Starknet&lang=en&optimize=false&runs=200&evmVersion=null&version=soljson-v0.8.24+commit.e11b9ed9.js

1. compile 成功
![alt text](https://github.com/MartinYeung5/starknet/blob/main//MartinYeung5/20240919_1.png?raw=true)

2. deploy 成功
![alt text](https://github.com/MartinYeung5/starknet/blob/main//MartinYeung5/20240919_2.png?raw=true)

### 2024.09.21
實操:Remix IDE

* interact 失敗 (Opera)
![alt text](https://github.com/MartinYeung5/starknet/blob/main//MartinYeung5/20240921_interact_error_opera.png?raw=true)

* interact 成功 (Opera)
試過重新刪所有cache、緩沖等，再重新開機，最後成功
![alt text](https://github.com/MartinYeung5/starknet/blob/main//MartinYeung5/20240921_interact_done.png?raw=true)

### 2024.09.22
實操:Remix IDE
* 心得
當透過官方提供的link進行時，會出現如下圖的popup提示: (需要下載整個repo, 要按6次"Accept", 否則就不能獲得完整repo)
![alt text](https://github.com/MartinYeung5/starknet/blob/main//MartinYeung5/20240922_remix_start_1.png?raw=true)
另外在deploy時也會出現2次popup，要求你去"Accept"。
最後，在按"Accept"時也要快，如果錯過了，就要刪緩沖的所有紀錄，重新開始，有需要時要重開機。

### 2024.09.23
執行安裝工具的部分
https://asdf-vm.com/guide/getting-started.html
我的本機環境:
* WSL Ubuntu 24.04 LTS

開始安裝相關工具:
Starkli Installation

curl https://get.starkli.sh | sh
![alt text](https://github.com/MartinYeung5/starknet/blob/main/MartinYeung5/20240923_1.png?raw=true)

starkliup
![alt text](https://github.com/MartinYeung5/starknet/blob/main/MartinYeung5/20240923_2.png?raw=true)

starkli --version
![alt text](https://github.com/MartinYeung5/starknet/blob/main/MartinYeung5/20240923_3.png?raw=true)

asdf installation
* apt install curl git
![alt text](https://github.com/MartinYeung5/starknet/blob/main/MartinYeung5/20240923_4.png?raw=true)

* git clone https://github.com/asdf-vm/asdf.git ~/.asdf --branch v0.14.1
![alt text](https://github.com/MartinYeung5/starknet/blob/main/MartinYeung5/20240923_5.png?raw=true)

* open .bashrc (at root / ~) in Vscode
update .bashrc (只要加入以下2句)
* . "$HOME/.asdf/asdf.sh"
* . "$HOME/.asdf/completions/asdf.bash"

![alt text](https://github.com/MartinYeung5/starknet/blob/main/MartinYeung5/20240923_6.png?raw=true)

然後執行
* code ~/.bashrc
![alt text](https://github.com/MartinYeung5/starknet/blob/main/MartinYeung5/20240923_7.png?raw=true)


測試一下
* asdf
成功安裝asdf
![alt text](https://github.com/MartinYeung5/starknet/blob/main/MartinYeung5/20240923_8.png?raw=true)

4. Install a Plugin
asdf plugin add nodejs https://github.com/asdf-vm/asdf-nodejs.git

5. Install a Version
asdf install nodejs latest

![alt text](https://github.com/MartinYeung5/starknet/blob/main/MartinYeung5/20240923_9.png?raw=true)

6. Set a Version

Add to global
* asdf global nodejs latest

檢查
* asdf current

![alt text](https://github.com/MartinYeung5/starknet/blob/main/MartinYeung5/20240923_10.png?raw=true)

Scarb Package Manager Installation

### 2024.09.24
Scarb Package Manager Installation
* asdf plugin add scarb
![alt text](https://github.com/MartinYeung5/starknet/blob/main/MartinYeung5/20240924_1.png?raw=true)

下一步就是要download scarb的版本，如果不download及于設置就會顯示沒有版本
![alt text](https://github.com/MartinYeung5/starknet/blob/main/MartinYeung5/20240924_2.png?raw=true)

download specific versions:
* asdf install scarb 2.5.4
![alt text](https://github.com/MartinYeung5/starknet/blob/main/MartinYeung5/20240924_3.png?raw=true)

如果不設置就會繼續顯示沒有版本
![alt text](https://github.com/MartinYeung5/starknet/blob/main/MartinYeung5/20240924_4.png?raw=true)

要設置版本
* asdf global scarb 2.5.4
![alt text](https://github.com/MartinYeung5/starknet/blob/main/MartinYeung5/20240924_5.png?raw=true)

再一次確認有沒有成功
* scarb --version
![alt text](https://github.com/MartinYeung5/starknet/blob/main/MartinYeung5/20240924_6.png?raw=true)

* Katana Node Installation
開始安裝
* curl -L https://install.dojoengine.org | bash
![alt text](https://github.com/MartinYeung5/starknet/blob/main/MartinYeung5/20240924_7.png?raw=true)

* dojoup
![alt text](https://github.com/MartinYeung5/starknet/blob/main/MartinYeung5/20240924_8.png?raw=true)

進行版本檢查
* katana --version
![alt text](https://github.com/MartinYeung5/starknet/blob/main/MartinYeung5/20240924_9.png?raw=true)

### 2024.09.25
* initiating a Scarb project

* scarb new my_contract
![alt text](https://github.com/MartinYeung5/starknet/blob/main/MartinYeung5/20240925_1.png?raw=true)

* update Scarb.toml
```
[package]
name = "my_contract"
version = "0.1.0"
edition = "2023_11"

[dependencies]
starknet = ">=2.5.4"

[[target.starknet-contract]]

```

有2個變數是必需要的，1個是starknet戶口，另一個是starknet代理: 用於設置使用網絡。
* 創建一個src/.env，
然後加入以下修改:
```
export STARKNET_ACCOUNT=katana-0
export STARKNET_RPC=http://0.0.0.0:5050
```

* 更新src/lib.cairo
```
#[starknet::interface]
trait IHello<T> {
    fn get_name(self: @T) -> felt252;
    fn set_name(ref self: T, name: felt252);
}

#[starknet::contract]
mod hello {
    #[storage]
    struct Storage {
        name: felt252,
    }

    #[constructor]
    fn constructor(ref self: ContractState, name: felt252) {
        self.name.write(name);
    }

    #[abi(embed_v0)]
    impl HelloImpl of super::IHello<ContractState> {
        fn get_name(self: @ContractState) -> felt252 {
            self.name.read()
        }

        fn set_name(ref self: ContractState, name: felt252) {
            self.name.write(name);
        }
    }
}
```

Compile the contract with the Scarb compiler:
* scarb build
![alt text](https://github.com/MartinYeung5/starknet/blob/main/MartinYeung5/20240925_1.png?raw=true)

The above command results in a compiled contract under target/dev/, named "my_contract_hello.contract_class.json"

去src, 執行:
* source .env

如果沒有執行 source src/.env , 會有以下錯誤訊息:
![alt text](https://github.com/MartinYeung5/starknet/blob/main/MartinYeung5/20240925_3.png?raw=true)

執行
* katanakatana
如下圖所示
![alt text](https://github.com/MartinYeung5/starknet/blob/main/MartinYeung5/20240925_4.png?raw=true)

去my_contract
To declare your contract, execute:
* starkli declare target/dev/my_contract_hello.contract_class.json
正常會出現以下錯誤訊息:
![alt text](https://github.com/MartinYeung5/starknet/blob/main/MartinYeung5/20240925_5.png?raw=true)

### 2024.09.26
應該要先做設置Account:
https://docs.starknet.io/quick-start/set-up-an-account/
* starkli --version
* mkdir -p ~/.starkli-wallets/deployer

在執行下一步前，必須要有Wallet
Argent X or Braavos wallet
https://braavos.app/download-braavos-wallet/

測試用:
siren thought depart stem cycle lazy reunion spatial shock local six there

account address:0x07bf212a91454ec1f129a8f4a29054211dc013f73bbbe50374426a41ce0a68ea
private:
0x0364fb6a326af3224b7fffd73731cd99f81e2c655eb84996ec66736c2cc6fd51
public:
0x44c91132de72543b5b92eae7875876f281d4706fc57b95c277ad7ced13aa4e

* starkli signer keystore from-key ~/.starkli-wallets/deployer/keystore.json
1. 需要輸入private key
2. 需要輸入密碼 (自設)

去新增STARKNET_KEYSTORE
https://docs.starknet.io/quick-start/environment-setup/#setting_up_starkli_environment_variables

更新.env

* starkli declare target/dev/my_contract_hello.contract_class.json
都是有錯誤訊息
Error: account config file not found
![alt text](https://github.com/MartinYeung5/starknet/blob/main/MartinYeung5/20240925_9.png?raw=true)

starkli account fetch 0x07bf212a91454ec1f129a8f4a29054211dc013f73bbbe50374426a41ce0a68ea --output ~/.starkli-wallets/deployer/account.json --rpc https://starknet-sepolia.g.alchemy.com/starknet/version/rpc/v0_7/xx

get faucet:
https://starknet-faucet.vercel.app/


starkli account fetch 0x07bf212a91454ec1f129a8f4a29054211dc013f73bbbe50374426a41ce0a68ea --output ~/.starkli-wallets/deployer/account.json

* starkli declare target/dev/my_contract_hello.contract_class.json
都是有錯誤訊息
Error: account config file not found
![alt text](https://github.com/MartinYeung5/starknet/blob/main/MartinYeung5/20240925_10.png?raw=true)

### 2024.09.27
starkli account fetch 0x07bf212a91454ec1f129a8f4a29054211dc013f73bbbe50374426a41ce0a68ea --output ~/.starkli-wallets/deployer/account.json --rpc https://starknet-sepolia.g.alchemy.com/starknet/version/rpc/v0_7/x

* 關鍵點: Braavos wallet 需要先deploy

成功:
![alt text](https://github.com/MartinYeung5/starknet/blob/main/MartinYeung5/20240925_11.png?raw=true)

檢查:
* cat ~/.starkli-wallets/deployer/account.json
![alt text](https://github.com/MartinYeung5/starknet/blob/main/MartinYeung5/20240925_12.png?raw=true)

* starkli account deploy ~/.starkli-wallets/deployer/account.json
但我的wallet已經deployed，因為Braavos wallet的已經在錢包上deployed
![alt text](https://github.com/MartinYeung5/starknet/blob/main/MartinYeung5/20240925_13.png?raw=true)

### 2024.09.28
下一部分
https://docs.starknet.io/quick-start/declare-a-smart-contract/
Declaring a smart contract

* 更新 Scarb.toml
```
[package]
name = "my_contract"
version = "0.1.0"
edition = "2023_11"

[dependencies]
starknet = ">=2.5.4"

[[target.starknet-contract]]
sierra = true

```

* update rpc at .env

starkli declare target/dev/my_contract_hello.contract_class.json --network=sepolia --compiler-version=2.7.1
有錯誤訊息:
![alt text](https://github.com/MartinYeung5/starknet/blob/main/MartinYeung5/20240925_14.png?raw=true)

my_contract.starknet_artifacts
starkli declare target/dev/my_contract.starknet_artifacts.json --network=sepolia --compiler-version=2.7.1

每次打開terminal
每次都要執行source src/.env 

### 2024.09.30

starkli declare target/dev/my_contract.starknet_artifacts.json \
    --rpc=https://starknet-sepolia.g.alchemy.com/starknet/version/rpc/v0_7/bG3D2u3pNQ0XI5lXiWcaGWGEzmA2G5zw\
    --compiler-version=2.7.1\
    --keystore=/root/.starkli-wallets/deployer/keystore.json\

都是有錯誤
![alt text](https://github.com/MartinYeung5/starknet/blob/main/MartinYeung5/20240925_15.png?raw=true)

starkli declare target/dev/my_contract.starknet_artifacts.json \
    --rpc=https://starknet-sepolia.g.alchemy.com/starknet/version/rpc/v0_7/bG3D2u3pNQ0XI5lXiWcaGWGEzmA2G5zw\
    --compiler-version=2.7.1\
    --keystore=/root/.starkli-wallets/deployer/keystore.json\
    --account=/root/.starkli-wallets/deployer/account.json

* 暫時不知道可以怎樣做，不能成功declare

### 2024.10.01
Starknet 工具鏈與開發環境

一般安裝:
curl --proto '=https' --tlsv1.2 -sSf https://docs.swmansion.com/scarb/install.sh | sh
最新版本的安裝:
curl --proto '=https' --tlsv1.2 -sSf https://docs.swmansion.com/scarb/install.sh | sh -s -- -v nightly
![alt text](https://github.com/MartinYeung5/starknet/blob/main/MartinYeung5/20241001_1.png?raw=true)
* source /root/.bashrc
* scarb --version
![alt text](https://github.com/MartinYeung5/starknet/blob/main/MartinYeung5/20241001_2.png?raw=true)

創建新的項目:
* scarb init --name hello_world
![alt text](https://github.com/MartinYeung5/starknet/blob/main/MartinYeung5/20241001_3.png?raw=true)
但就不能創建帶有項目名稱的目錄，要自行創建。


### 2024.10.02
參考:
https://github.com/software-mansion/scarb/tree/main/examples/hello_world

* cario book
https://book.cairo-lang.org/

寫一個計數器合約
創建一個counter.cairo
* 增加counter.cairo
* 更新lib.cairo
* scarb build
![alt text](https://github.com/MartinYeung5/starknet/blob/main/MartinYeung5/20241002_1.png?raw=true)
如果成功，會看到一個target文件，裡面有3個.json的文件。

### 2024.10.03
參考:
https://github.com/PhilippeR26/starknet.js-workshop-typescript

通過JS-SDK部署合約

* mkdir js
* cd js
* npm init
* npm install starknet

### 2024.10.04
在根據教學影片中的步驟，
需要自行編寫declare.js, deploy.js，
雖然可以根據影片中的代碼，但有些地方不太清晰，如有文檣提供就好。

### 2024.10.05
在互聯網上查看declare.js, deploy.js的寫法，但各有不同，不太知道哪個是正確

Starknet 殘酷共學分享會 #3: 開發框架 Scaffold-Stark
* https://github.com/Scaffold-Stark/scaffold-stark-2
Scaffold-Starknet與Scaffold-ETH-2有相似的地方。
Scaffold-Starknet包含Starknet React, Starknet.js, Cairo, Next.js, Starknet Foundry。


* git clone https://github.com/Scaffold-Stark/scaffold-stark-2.git
* 新文件: scaffold-stark-2
* yarn install
![alt text](https://github.com/MartinYeung5/starknet/blob/main/MartinYeung5/20241006_1.png?raw=true)
* yarn chain
有錯誤:
![alt text](https://github.com/MartinYeung5/starknet/blob/main/MartinYeung5/20241006_2.png?raw=true)

參考安裝步驟:
https://medium.com/spaceshard/how-to-run-starknet-devnet-on-windows-tech-tutorial-f8447c131193

* sudo apt install python3-pip
* sudo apt install -y libgmp3-dev
安裝成功:
![alt text](https://github.com/MartinYeung5/starknet/blob/main/MartinYeung5/20241006_4.png?raw=true)

* pip install starknet-devnet
都係有錯誤
![alt text](https://github.com/MartinYeung5/starknet/blob/main/MartinYeung5/20241006_3.png?raw=true)

* 使用另一方式安裝
https://book.starknet.io/ch02-07-starknet-devnet.html
* git clone https://github.com/0xSpaceShard/starknet-devnet-rs.git

### 2024.10.07
* 運行 a local network 
* cd starknet-devnet-rs
* cargo on (不要用yarn chain)
* 運行成功:
![alt text](https://github.com/MartinYeung5/starknet/blob/main/MartinYeung5/20241006_5.png?raw=true)

* 打開新的terminal
* cd scaffold-stark-2/
* yarn deploy
有錯誤:
![alt text](https://github.com/MartinYeung5/starknet/blob/main/MartinYeung5/20241006_6.png?raw=true)

* 需要安裝以下工具
* asdf install scarb 2.8.3
![alt text](https://github.com/MartinYeung5/starknet/blob/main/MartinYeung5/20241006_7.png?raw=true)

再次執行:
* cd scaffold-stark-2/
* yarn deploy

有錯誤:
Error: The wallet you're using to deploy the contract is not deployed in the devnet network.
![alt text](https://github.com/MartinYeung5/starknet/blob/main/MartinYeung5/20241006_8.png?raw=true)

* 需要修改/packages/nextjs/scaffold.config
如果沒發現問題，就要修改
* /packages/snfoundry/scripts-ts/helpers/networks.ts

再次執行:
* cd scaffold-stark-2/
* yarn deploy
成功Deploy:
![alt text](https://github.com/MartinYeung5/starknet/blob/main/MartinYeung5/20241006_9.png?raw=true)



<!-- Content_END -->
