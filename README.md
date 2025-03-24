加个英文，方便牛马们search(BSC chain transfer parse / pancake swap V2 transfer parse)

编译(二进制文件运行)环境：

- Mac/m1

如何使用

- clone仓库后改修parser文件的权限(直接上777)，直接执行 `./parser <交易hash>`
- 或者`export RPC_URL=<rpc节点> && ./parser <交易hash> -v`
- 在命令行末尾加上-v可以现实更加详细的信息
- 可以自己设置RPC节点，如：`export RPC_URL="https://bsc-dataseed.binance.org/"`

已实现✅
- [x] pancake swap V2版本的所有交易解析，如下所示
 
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
/parser 0xe216607d3d95f3db8b847157d2be325985767b2f4a9421e2d084b582eaab3060
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

注意⚠️⚠️：当前只支持BSC chain 的 pancake swap V2版本的解析

最后说一下为什么写这么个傻逼玩意儿吧：
就两个字：“装逼”！当然这是其一，主要还是因为高薪入职了某企，然后给我安排了这么个活，但是呢，排工期的时候呢，
我的大哥（Leader）居然把晚上默认算进去加班，然后默认算半个工期，周末两天也给我排进去，
好了，哥不乐意，TMD，没加班工资，我刚来第二天和咱这么玩是吧？当牛也得有时间喝口水吧？
爷不干了，关键是一周的活，给我压缩到2天，我笑了，所以，我做了个不想短择的短择，最后，提交了一份长得像💩的代码，
say byebye，心里爽啊😄😄！！！！
说实在的，咱也不知道写这么个解析的玩意儿要花多久，有多少代码量，出于好奇，决定花几天搞一下，毕竟对一个做链开发
的coder来说，做block transfer解析就是儿科中的儿科，不试不知道，一试吓一跳，写了四天，大概 5K 行代码，还只是
单链单版本的解析，我他妈就好奇，是我菜吗？花四天？大哥们四天可以搞一个terminal上运行的scan出来吗？
我只要单链单dex！！千言万语，尽在吃屎中，放个二进制文件出来玩！！！㊗️牛马们开心！！！！