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
![alt text](https://github.com/MartinYeung5/20240918_starknet/blob/main/20240919_1.png?raw=true)

2. deploy 成功
![alt text](https://github.com/MartinYeung5/20240918_starknet/blob/main/20240919_2.png?raw=true)

<!-- Content_END -->
