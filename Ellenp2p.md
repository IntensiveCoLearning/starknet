# Ellen

1. 自我介绍
2. 你认为你会完成本次残酷学习吗？

## Notes

<!-- Content_START -->

### 2024.09.18

- 根据 [cario book](https://book.cairo-lang.org/ch01-01-installation.html) 安装 scarb
- 根据 [foundry rs](https://foundry-rs.github.io/starknet-foundry/getting-started/installation.html) 安装 snforge
- 执行 `snforge init hello_world`
- 执行 `scarb build` 失败，预计在 19 号查原因

### 2024.09.19

### 2024.09.21

- 重新安装 foundry
- 执行 test hello world 成功
- 学习合约逻辑，了解存储结构

### 2024.09.22

- 学习 https://docs.openzeppelin.com/contracts-cairo/0.16.0/erc20

### 2024.09.23

- 听分享部署合约
- sncast account deploy --fee-token eth --name Test1
- sncast --account Test1 declare --fee-token eth --contract-name HelloStarknet
- sncast deploy --class-hash 0x1a6835329277e9a402a747e041546d418cee105c2a8de41c6dd4930e80c8681 --fee-token eth

<!-- Content_END -->
