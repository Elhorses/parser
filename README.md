编译(二进制文件运行)环境：

- Mac/m1

如何使用

- clone仓库后改修parser文件的权限(直接上777)，直接执行 `./parser <交易hash>`
- 在命令行末尾加上-v可以现实更加详细的信息
- 注意default链的BSC链，其他链的交易解析需要加上`CHAIN`环境变量
- 可以自己设置RPC节点，如：`export RPC_URL="https://bsc-dataseed.binance.org/"` ，注意，修改了RPC节点一定要加上链`CHAIN`环境变量
- 可以选择链，如：`export CHAIN="bsc"`
- 完整示例，如`export CHAIN="bsc" && export RPC_URL="https://bsc-dataseed.binance.org/" && ./parser 0xe216607d3d95f3db8b847157d2be325985767b2f4a9421e2d084b582eaab3060`

已实现✅
- [x] PancakeSwap/UniSwap/SushiSwap(但不限于这三个DEX)的所有交易解析，如下所示
 
  - swapExactTokensForTokens(0x38ed1739)
  - swapTokensForExactTokens(0x8803dbee)
  - swapExactETHForTokens(0x7ff36ab5)
  - swapETHForExactTokens(0xfb3bdb41)
  - swapTokensForExactETH(0x4a25d94a)
  - swapExactTokensForETH(0x18cbafe5)
  - swapExactTokensForTokensSupportingFeeOnTransferTokens(0x5c11d795)
  - swapExactETHForTokensSupportingFeeOnTransferTokens(0xb6f9de95)
  - swapExactTokensForETHSupportingFeeOnTransferTokens(0x791ac947)
  - addLiquidity(0xe8e33700)
  - addLiquidityETH(0xf305d719)
  - removeLiquidity(0xbaa2abde)
  - removeLiquidityETH(0x02751cec)
  - removeLiquidityETHWithPermit(0xded9382a)
  - removeLiquidityETHSupportingFeeOnTransferTokens(0xaf2979eb)
  - removeLiquidityETHWithPermitSupportingFeeOnTransferTokens(0x5b0d5984)
  - removeLiquidityWithPermit(0x2195995c)

运行命令

```./parser <交易hash>```

示例1

```shell
./parser 0xe216607d3d95f3db8b847157d2be325985767b2f4a9421e2d084b582eaab3060
```

输出

![image](/image/0xf305d719/localTerminal.png)

BscScan对比

![image](/image/0xf305d719/bscScan_1.png)

![image](/image/0xf305d719/bscScan_2.png)

示例2

```shell
./parser 0xb1db92d3f0a6a873deedbfb190307aba75cc9d60206bca038297f363bfee7ff4
```

输出

![image](/image/0x8803dbee/localTerminal.png)

BscScan对比

![image](/image/0x8803dbee/bscScan_1.png)

![image](/image/0x8803dbee/bscScan_2.png)

提示🔔🔔：其他交易的输出打印可以自己从github上下载后运行命令即可

注意⚠️⚠️：当前只支持EVM chain 系列的上述方法的解析，其他方法逻辑上也可以解析，但是没有添加方法名，直接运行即可
