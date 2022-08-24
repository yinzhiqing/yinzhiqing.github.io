---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_json_rpc
title: Json rpc Apis

# post specific
# if not specified, .name will be used from _data/owner/[language].yml
author: yinzhiqing
# multiple category is not supported
category: jekyll
# multiple tag entries are possible
tags: [interface, new feature]
# thumbnail image for post
img: ":eth-json-rpc.jpg"
# disable comments on this page
#comments_disable: true

# publish date
date: 2022-08-16 15:32:10 +0800

# seo
# if not specified, date will be used.
#meta_modify_date: 2022-03-03 12:32:10 +0900
# check the meta_common_description in _data/owner/[language].yml
#meta_description: ""

# optional
# if you enabled image_viewer_posts you don't need to enable this. This is only if image_viewer_posts = false
#image_viewer_on: true
# if you enabled image_lazy_loader_posts you don't need to enable this. This is only if image_lazy_loader_posts = false
#image_lazy_loader_on: true
# exclude from on site search
#on_site_search_exclude: true
# exclude from search engines
#search_engine_exclude: true
# to disable this page, simply set published: false or delete this file
#published: false
---


<!-- outline-start -->

链Json-Rpc接口. <!-- outline-end -->

### 版本
　json-rpc 规范没有看到时间，以整理时间作为标记. Date: 2022-08-18
 
### 接口列表


#### eth_getBlockByHash 

**接口描述**
```

通过块hash返回块的信息．

```

**参数**

|名称|类型|说明|备注|
|:---|:---|:---|:---|
|blockhash|string|块hash值|32 byte|
|hydrated|boolean|返回值内容|如果true它返回完整的交易对象，如果false只有交易的哈希值|

**返回值**

|名称|类型|说明|备注|
|:---|:---|:---|:---|
|hash|string|块hash值|null当它的待处理块|
|parentHash|string|父块hash值||
|sha3Uncles|string|块中叔块数据的 SHA3||
|miner|string|获得挖矿奖励的受益人地址||
|stateRoot|string|块的最终状态树的根||
|transactionsRoot|string|区块的交易树的根||
|receiptsRoot|string|区块收据树的根||
|logsBloom|string|块日志的布隆过滤器|null当它的待处理块|
|difficulty|string|此块难度的整数||
|number|string|块号|null当它的待处理块|
|gasLimit|string|此块中允许的最大气体||
|gasUsed|string|该区块中所有交易的总gas使用量||
|timestamp|string|整理块时的 unix 时间戳||
|extraData|string|此块的“额外数据”字段||
|mixHash|string|混合hash|与nonce来计算难度|
|nonce|string|生成的工作量证明的哈希值|null当它的待处理块|
|totalDifficulty|string|直到这个块的链总难度的整数||
|size|string|这个块的大小，以字节为单位||
|transactions|string|||
|uncles|string|叔哈希数组||


#### eth_getBlockByNumber   

**接口描述**
```
 
 通过块号返回块的信息．

```

**参数**

|名称|类型|说明|备注|
|:---|:---|:---|:---|
|blocknumber/blocktag|string|块编号的整数，或字符串|earliest finalized safe latest pending|
|hydrated|boolean|返回值内容|如果true它返回完整的交易对象，如果false只有交易的哈希值|

**返回值**

参照[eth_getBlockByHash](## eth_getBlockByHash)


#### eth_getBlockTransactionCountByHash

**接口描述**
```

从与给定块哈希匹配的块中返回块中的事务数。 

```

**参数**

|名称|类型|说明|备注|
|:---|:---|:---|:---|
|blockhash|string|块hash值|32 byte|

**返回值**

|名称|类型|说明|备注|
|:---|:---|:---|:---|
|count|string|该区块中交易数量(十六进制编码的无符号整数)||


#### eth_getBlockTransactionCountByNumber

**接口描述**
```
 
返回与给定块号匹配的块中的事务数

```

**参数**

|名称|类型|说明|备注|
|:---|:---|:---|:---|
|blocknumber/blocktag|string|块编号的整数，或字符串|earliest finalized safe latest pending|

**返回值**

|名称|类型|说明|备注|
|:---|:---|:---|:---|
|count|string|该区块中交易数量(十六进制编码的无符号整数)||


#### eth_getUncleCountByBlockHash

**接口描述**
```
 
从匹配给定块哈希的块中返回块中的叔块数

```

**参数**

|名称|类型|说明|备注|
|:---|:---|:---|:---|
|blockhash|string|块hash值|32 byte|

**返回值**

|名称|类型|说明|备注|
|:---|:---|:---|:---|
|count|string|该块中叔叔数量(十六进制编码的无符号整数)||


#### eth_getUncleCountByBlockNumber

**接口描述**
```
 
从与给定块号匹配的块中返回块中的叔块数。

```

**参数**

|名称|类型|说明|备注|
|:---|:---|:---|:---|
|blocknumber/blocktag|string|块编号的整数，或字符串|earliest finalized safe latest pending|

**返回值**

|名称|类型|说明|备注|
|:---|:---|:---|:---|
|count|string|该区块中交易数量(十六进制编码的无符号整数)||


#### eth_chainId

**接口描述**
```
 
返回当前网络的链ID．

```

**参数**

 无

**返回值**

|名称|类型|说明|备注|
|:---|:---|:---|:---|
|chainId|string|链ID(十六进制编码的无符号整数)||


#### eth_syncing

**接口描述**
```
 
返回一个对象，其中包含有关同步状态的数据或false.

```

**参数**

　无

**返回值**

|名称|类型|说明|备注|
|:---|:---|:---|:---|
|staringBlock|string|起始块(十六进制编码的无符号整数)|同步的时候|
|currentBlock|string|当前块(十六进制编码的无符号整数)|同步的时候|
|highestBlock|string|最高块(十六进制编码的无符号整数)|同步的时候|
|state|boolean|不同步false|不同步的时候|


#### eth_coinbase

**接口描述**
```
 
返回客户端 coinbase 地址。

```

**参数**

  无

**返回值**

|名称|类型|说明|备注|
|:---|:---|:---|:---|
|address|string|当前的 coinbase 地址|20字节|


#### eth_accounts 

**接口描述**
```
 
返回客户端拥有的地址列表

```

**参数**

  无

**返回值**

|名称|类型|说明|备注|
|:---|:---|:---|:---|
|addresses|array|客户端拥有的地址|数组中存储的是多个地址|


#### eth_blockNumber

**接口描述**
```
 
返回最近块的数量

```

**参数**

  无

**返回值**

|名称|类型|说明|备注|
|:---|:---|:---|:---|
|blocknumber|string|客户端所在的当前块号的整数(十六进制编码的无符号整数)||

<a id="eth_call"></a>
#### eth_call

**接口描述**
```
 
立即执行新的消息调用，而不在区块链上创建交易。

```

**参数**

***参数１：交易调用对象Object***

|名称|类型|说明|备注|
|:---|:---|:---|:---|
|type|string|交易类型||
|nonce|string|交易序号(十六进制编码的无符号整数)||
|to|string|交易指向的地址||
|from|string|(可选)发送交易的地址||
|gas|string|(可选)为交易执行提供的气体的整数(十六进制编码的无符号整数)||
|value|string|(可选)与此交易一起发送的值的整数(十六进制编码的无符号整数)||
|input|string|(可选)方法签名和编码参数的哈希||
|gasPrice|string|（可选）用于每个付费气体的 gasPrice 的整数(十六进制编码的无符号整数)||
|maxPriorityFeePerGas|string|每gas的最高优先费用(十六进制编码的无符号整数)|发送人愿意向矿工支付的最高费用/gas 单位: wei|
|maxFeePerGas|string|每gas的最高费用|发送方愿意支付的最高费用（包括网络 基本费用　矿工/优先权费用）单位: wei|
|chainId|string|链ID(十六进制编码的无符号整数)||

***参数２：块号***

|名称|类型|说明|备注|
|:---|:---|:---|:---|
|blocknumber/blocktag|string|块编号的整数，或字符串|earliest finalized safe latest pending|

**返回值**

|名称|类型|说明|备注|
|:---|:---|:---|:---|
|data|string|已执行合约的返回值(十六进制编码)||
|||||


#### eth_estimateGas

**接口描述**
```
 
生成并返回允许交易完成所需的气体估计值。交易不会被添加到区块链中。
请注意，出于各种原因，包括 虚拟机机制和节点性能，估计值可能远远超过交易实际使用的 gas 量。

```

**参数**

 参照[eth_call](#eth_call)

**返回值**

|名称|类型|说明|备注|
|:---|:---|:---|:---|
|gasUsed|string|估值|十六进制编码的无符号整数|


#### eth_gasPrice

**接口描述**
```
 
返回以 wei 为单位的每 gas 的当前价格。

```

**参数**

 无

**返回值**

|名称|类型|说明|备注|
|:---|:---|:---|:---|
|gasPrice|string|gas当前价格|十六进制编码的无符号整数|


#### eth_newFilter

**接口描述**
```
 
根据过滤器选项创建一个过滤器对象，以在状态更改（日志）时发出通知。

```

**参数**

|名称|类型|说明|备注|
|:---|:---|:---|:---|
|fromBlock/blocktag|string|(可选)块编号的整数，或字符串|earliest finalized safe latest pending|
|toBlock/blocktag|string|(可选)块编号的整数，或字符串|earliest finalized safe latest pending|
|address|string/array|(可选)合约地址或记录日志的地址列表||
|topics|string/array|(可选) 32 字节DATA主题数组||

**返回值**

|名称|类型|说明|备注|
|:---|:---|:---|:---|
|id|string|过滤器ID|十六进制编码的无符号整数|


#### eth_newBlockFilter

**接口描述**
```
 
在节点中创建一个过滤器，以在新块到达时通知。

```

**参数**

  无

**返回值**

|名称|类型|说明|备注|
|:---|:---|:---|:---|
|id|string|过滤器ID|十六进制编码的无符号整数|


#### eth_newPendingTransactionFilter

**接口描述**
```

在节点中创建一个过滤器，以在新的待处理事务到达时发出通知。

```

**参数**

  无

**返回值**

|名称|类型|说明|备注|
|:---|:---|:---|:---|
|id|string|过滤器ID|十六进制编码的无符号整数|


#### eth_uninstallFilter

**接口描述**
```

卸载具有给定 ID 的过滤器。

```

**参数**

|名称|类型|说明|备注|
|:---|:---|:---|:---|
|id|string|过滤器ID|十六进制编码的无符号整数|

**返回值**

|名称|类型|说明|备注|
|:---|:---|:---|:---|
|state|boolean|true如果过滤器成功卸载，否则false||


#### eth_getFilterChanges

**接口描述**
```
 
过滤器的轮询方法，它返回自上次轮询以来发生的日志数组。

```

**参数**

|名称|类型|说明|备注|
|:---|:---|:---|:---|
|id|string|过滤器ID|十六进制编码的无符号整数|

**返回值**

日志对象数组，如果自上次轮询以来没有任何更改，则返回一个空数组。

- eth_newBlockFilter对应的id查询的结果

|名称|类型|说明|备注|
|:---|:---|:---|:---|
|blockHash|array(string)|块hash数组||

- eth_newPendingTransactionFilter对应的id查询的结果

|名称|类型|说明|备注|
|:---|:---|:---|:---|
|tranHash|array(string)|事务hash数组||

- eth_newFilter对应的id查询的结果

|名称|类型|说明|备注|
|:---|:---|:---|:---|
|removed|string|日志状态|true当日志被删除时，由于链重组。false如果它是有效的日志。|
|logIndex|string|块中日志索引位置的整数|null当其挂起的日志|
|transactionIndex|string|创建事务日志索引位置|十六进制编码的无符号整数, null当其挂起的日志|
|transactionHash|string|创建此日志的事务的哈希值|null当其挂起的日志|
|blockHash|string|此日志所在的块的哈希值|null当其挂起的日志|
|blockNumber|string|此日志所在的块号|null当其挂起的日志|
|address|string|此日志的来源地址||
|data|string|包含一个或多个 32 字节非索引参数的日志||
|topics|array|0 到 4 个 32 字节DATA的索引日志参数数组||


#### eth_getFilterLogs

**接口描述**
```
 
返回具有给定 id 的所有与过滤器匹配的日志的数组。

```

**参数**

|名称|类型|说明|备注|
|:---|:---|:---|:---|
|id|string|过滤器ID|十六进制编码的无符号整数|

**返回值**

参见[eth_getFilterChanges](##eth_getFilterChanges)


#### eth_getLogs

**接口描述**
```
 
返回与给定过滤器对象匹配的所有日志的数组。

```

**参数**

|名称|类型|说明|备注|
|:---|:---|:---|:---|
|fromBlock/blocktag|string|(可选)块编号的整数，或字符串|earliest finalized safe latest pending|
|toBlock/blocktag|string|(可选)块编号的整数，或字符串|earliest finalized safe latest pending|
|address|string/array|(可选)合约地址或记录日志的地址列表||
|topics|string/array|(可选) 32 字节DATA主题数组||

**返回值**

参见[eth_getFilterChanges](##eth_getFilterChanges)


#### eth_mining

**接口描述**
```
 
返回客户端是否在挖掘新块

```

**参数**

  无

**返回值**

|名称|类型|说明|备注|
|:---|:---|:---|:---|
|state|boolean|挖矿状态||


#### eth_getWork

**接口描述**
```
 
返回当前区块的哈希值、种子哈希值和要满足的边界条件（“目标”）

```

**参数**

  无

**返回值**

|名称|类型|说明|备注|
|:---|:---|:---|:---|
|powHash|string|当前区块头 pow-hash||
|seedHash|string|用于 DAG 的种子哈希||
|difficulty|string|边界条件（“目标”），2^256 / 难度||


#### eth_submitWork

**接口描述**
```

用于提交工作证明解决方案

```

**参数**

|名称|类型|说明|备注|
|:---|:---|:---|:---|
|nonce|string|随机数|64位, 16进制|
|hash|string|标头的 pow-hash|256位, 16进制|
|digest|string|混合摘要|256位, 16进制|

**返回值**

|名称|类型|说明|备注|
|:---|:---|:---|:---|
|state|boolean|提交状态||


#### eth_submitHashrate

**接口描述**
```

用于提交挖矿算力。

```

**参数**

|名称|类型|说明|备注|
|:---|:---|:---|:---|
|hashRate|string|哈希率的十六进制字符串表示||
|id|string|客户端ID|十六进制编码|

**返回值**

|名称|类型|说明|备注|
|:---|:---|:---|:---|
|state|boolean|提交状态||


#### eth_sign

**接口描述**
```
 
sign 方法计算以太坊特定的签名：sign(keccak256("\x19Ethereum Signed Message:\n" + len(message) + message)))。

通过在消息中添加前缀，可以将计算出的签名识别为以太坊特定的签名。这可以防止恶意 dapp 可以签署任意数据（例如交易）并使用签名来冒充受害者的滥用行为。

注意：要签名的地址必须是解锁的。

```

**参数**

|名称|类型|说明|备注|
|:---|:---|:---|:---|
|address|string|地址||
|message|string|要签名的消息|

**返回值**

|名称|类型|说明|备注|
|:---|:---|:---|:---|
|signData|string|签名字符串||


#### eth_signTransaction

**接口描述**
```
 
使用eth_sendRawTransaction签署可以在以后提交到网络的交易。

```

**参数**

|名称|类型|说明|备注|
|:---|:---|:---|:---|
|type|string|交易类型||
|nonce|string|交易序号(十六进制编码的无符号整数)||
|to|string|交易指向的地址||
|from|string|(可选)发送交易的地址||
|gas|string|(可选)为交易执行提供的气体的整数(十六进制编码的无符号整数)||
|value|string|(可选)与此交易一起发送的值的整数(十六进制编码的无符号整数)||
|input|string|(可选)方法签名和编码参数的哈希||
|gasPrice|string|（可选）用于每个付费气体的 gasPrice 的整数(十六进制编码的无符号整数)||
|maxPriorityFeePerGas|string|每gas的最高优先费用(十六进制编码的无符号整数)|发送人愿意向矿工支付的最高费用/gas 单位: wei|
|maxFeePerGas|string|每gas的最高费用|发送方愿意支付的最高费用（包括网络 基本费用　矿工/优先权费用）单位: wei|
|chainId|string|链ID(十六进制编码的无符号整数)||


**返回值**

|名称|类型|说明|备注|
|:---|:---|:---|:---|
|signData|string|签名字符串||


#### eth_getBalance

**接口描述**
```
 
返回给定地址的账户余额。

```

**参数**

|名称|类型|说明|备注|
|:---|:---|:---|:---|
|address|string|获取余额的地址||
|blocknumberortag|string|(可选)块编号的整数，或字符串|earliest finalized safe latest pending|

**返回值**

|名称|类型|说明|备注|
|:---|:---|:---|:---|
|balance|string|当前余额　单位 wei|十六进制|


#### eth_getStorageAt

**接口描述**
```
 
从给定地址的存储位置返回值。

```

**参数**

|名称|类型|说明|备注|
|:---|:---|:---|:---|
|address|string|存储地址||
|slot|string|存储位置|十六进制编码的无符号整数|
|blocknumberortag|string|(可选)块编号的整数，或字符串|earliest finalized safe latest pending|

**返回值**

|名称|类型|说明|备注|
|:---|:---|:---|:---|
|data|string|此存储位置值|十六进制编码|


#### eth_getTransactionCount

**接口描述**
```
 
返回从地址发送的事务数。

```

**参数**

|名称|类型|说明|备注|
|:---|:---|:---|:---|
|address|string|地址||
|blocknumberortag|string|(可选)块编号的整数，或字符串|earliest finalized safe latest pending|

**返回值**

|名称|类型|说明|备注|
|:---|:---|:---|:---|
|count|string|事务数|十六进制|


#### eth_getCode

**接口描述**
```
 
返回给定地址的代码.

```

**参数**

|名称|类型|说明|备注|
|:---|:---|:---|:---|
|address|string|地址||
|blocknumberortag|string|(可选)块编号的整数，或字符串|earliest finalized safe latest pending|

**返回值**

|名称|类型|说明|备注|
|:---|:---|:---|:---|
|code|string|代码|十六进制|


#### eth_sendTransaction

**接口描述**
```
 
创建新的消息调用交易或合约创建.

```

**参数**

|名称|类型|说明|备注|
|:---|:---|:---|:---|
|type|string|交易类型||
|nonce|string|交易序号(十六进制编码的无符号整数)||
|to|string|交易指向的地址||
|from|string|(可选)发送交易的地址||
|gas|string|(可选)为交易执行提供的气体的整数(十六进制编码的无符号整数)||
|value|string|(可选)与此交易一起发送的值的整数(十六进制编码的无符号整数)||
|input|string|(可选)方法签名和编码参数的哈希||
|gasPrice|string|（可选）用于每个付费气体的 gasPrice 的整数(十六进制编码的无符号整数)||
|maxPriorityFeePerGas|string|每gas的最高优先费用(十六进制编码的无符号整数)|发送人愿意向矿工支付的最高费用/gas 单位: wei|
|maxFeePerGas|string|每gas的最高费用|发送方愿意支付的最高费用（包括网络 基本费用　矿工/优先权费用）单位: wei|
|chainId|string|链ID(十六进制编码的无符号整数)||

**返回值**

|名称|类型|说明|备注|
|:---|:---|:---|:---|
|hash|string|交易哈希，如果交易尚不可用，则为零哈希||


#### eth_sendRawTransaction

**接口描述**
```
 
为已签名的交易创建新的消息调用交易或合同创建。

```

**参数**

|名称|类型|说明|备注|
|:---|:---|:---|:---|
|signTran|string|签名的交易数据||

**返回值**

|名称|类型|说明|备注|
|:---|:---|:---|:---|
|hash|string|交易哈希，如果交易尚不可用，则为零哈希||


#### eth_getTransactionByHash

**接口描述**
```

返回交易哈希请求的交易信息。 

```

**参数**

|名称|类型|说明|备注|
|:---|:---|:---|:---|
|hash|string|交易的哈希||

**返回值**

|名称|类型|说明|备注|
|:---|:---|:---|:---|
|blockHash|string|该交易所在区块的哈希值。null当它挂起时||
|blockNumber|string|该交易所在的区块号。null当它挂起时||
|from|string|发送者的地址||
|gas|string|发件人提供的gas||
|gasPrice|string|发件人提供的 gas 价格 wei||
|hash|string|交易的哈希值||
|input|string|与交易一起发送的数据||
|nonce|string|发件人在此之前进行的交易数量||
|to|string|接收者的地址。null当它是合同创建交易时||
|transactionIndex|string|块中交易索引位置的整数。null当它待定时||
|value|string|转移的值 Wei||
|v|string|ECDSA 恢复 ID||
|r|string|ECDSA 签名 r||
|s|string|ECDSA 签名||


#### eth_getTransactionByBlockHashAndIndex

**接口描述**
```
 
通过块哈希和交易索引位置返回有关交易的信息。

```

**参数**

|名称|类型|说明|备注|
|:---|:---|:---|:---|
|blockHash|string|块的哈希||
|index|string|交易索引|十六进制编码的无符号整数|

**返回值**

参照[eth_getTransactionByHash](##eth_getTransactionByHash)


#### eth_getTransactionByBlockNumberAndIndex

**接口描述**
```
 
按块号和交易索引位置返回有关交易的信息。

```

**参数**

|名称|类型|说明|备注|
|:---|:---|:---|:---|
|blocknumberortag|string|(可选)块编号的整数，或字符串|earliest finalized safe latest pending|
|index|string|交易索引|十六进制编码的无符号整数|

**返回值**

参照[eth_getTransactionByHash](##eth_getTransactionByHash)


#### eth_getTransactionReceipt

**接口描述**
```
 
通过交易哈希返回交易的收据。

收据不可用于待处理的交易。

```

**参数**

|名称|类型|说明|备注|
|:---|:---|:---|:---|
|hash|string|交易的哈希||

**返回值**

|名称|类型|说明|备注|
|:---|:---|:---|:---|
|transactionHash|string|交易的哈希值||
|transactionIndex|string|块中交易索引位置的整数|十六进制编码的无符号整数|
|blockHash|string|该交易所在区块的哈希值||
|blockNumber|string|该交易所在的区块号|十六进制编码的无符号整数|
|from|string|发送者的地址||
|to|string|接收者的地址。合约创建交易时为空||
|cumulativeGasUsed|string|此交易在区块中执行时使用的总gas|十六进制编码的无符号整数|
|gasUsed|string|仅此特定交易使用的gas|十六进制编码的无符号整数|
|contractAddress|string|创建的合约地址，如果交易是合约创建，否则null||
|logs|string|此事务生成的日志对象数组||
|logsBloom|string|用于轻客户端快速检索相关日志的布隆过滤器||
|root|string|32 字节的交易后 stateroot（拜占庭前）||
|status|string|要么1（成功）要么0（失败）|十六进制编码的无符号整数|


