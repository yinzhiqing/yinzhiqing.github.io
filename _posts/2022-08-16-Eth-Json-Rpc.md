---
# multilingual page pair id, this must pair with translations of this page. (This name must be unique)
lng_pair: id_json_rpc
title: Json rpc Apis

# post specific
# if not specified, .name will be used from _data/owner/[language].yml
author: yinzhiqing
# multiple category is not supported
category: language
# multiple tag entries are possible
tags: [yzq, new feature]
# thumbnail image for post
img: ":mock1.jpg"
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

{%- capture readme_file -%}{%- include_relative _README.md -%}{%- endcapture -%}
{%- assign tmp_content = readme_file | split: "<!-- readme -->" -%}

<!-- outline-start -->

链Json-Rpc接口. <!-- outline-end -->

# 接口列表


## eth_getBlockByHash 

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


## eth_getBlockByNumber   

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


## eth_getBlockTransactionCountByHash

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


## eth_getBlockTransactionCountByNumber

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


## eth_getUncleCountByBlockHash

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


## eth_getUncleCountByBlockNumber

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


## eth_chainId

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


## eth_syncing

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


## eth_coinbase

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


## eth_accounts 

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


## eth_blockNumber

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
## eth_call

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


## eth_estimateGas

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


## eth_gasPrice

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


## eth_newFilter

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


## eth_newBlockFilter

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


## eth_newPendingTransactionFilter

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


## eth_uninstallFilter

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


## eth_getFilterChanges

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


## eth_getFilterLogs

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


## eth_getLogs

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


## eth_mining

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


## 

**接口描述**
```
 

```

**参数**

|名称|类型|说明|备注|
|:---|:---|:---|:---|
|||||
|||||

**返回值**

|名称|类型|说明|备注|
|:---|:---|:---|:---|
|||||
|||||


## 

**接口描述**
```
 

```

**参数**

|名称|类型|说明|备注|
|:---|:---|:---|:---|
|||||
|||||

**返回值**

|名称|类型|说明|备注|
|:---|:---|:---|:---|
|||||
|||||


## 

**接口描述**
```
 

```

**参数**

|名称|类型|说明|备注|
|:---|:---|:---|:---|
|||||
|||||

**返回值**

|名称|类型|说明|备注|
|:---|:---|:---|:---|
|||||
|||||


## 

**接口描述**
```
 

```

**参数**

|名称|类型|说明|备注|
|:---|:---|:---|:---|
|||||
|||||

**返回值**

|名称|类型|说明|备注|
|:---|:---|:---|:---|
|||||
|||||


## 

**接口描述**
```
 

```

**参数**

|名称|类型|说明|备注|
|:---|:---|:---|:---|
|||||
|||||

**返回值**

|名称|类型|说明|备注|
|:---|:---|:---|:---|
|||||
|||||


## 

**接口描述**
```
 

```

**参数**

|名称|类型|说明|备注|
|:---|:---|:---|:---|
|||||
|||||

**返回值**

|名称|类型|说明|备注|
|:---|:---|:---|:---|
|||||
|||||


## 

**接口描述**
```
 

```

**参数**

|名称|类型|说明|备注|
|:---|:---|:---|:---|
|||||
|||||

**返回值**

|名称|类型|说明|备注|
|:---|:---|:---|:---|
|||||
|||||


## 

**接口描述**
```
 

```

**参数**

|名称|类型|说明|备注|
|:---|:---|:---|:---|
|||||
|||||

**返回值**

|名称|类型|说明|备注|
|:---|:---|:---|:---|
|||||
|||||


## 

**接口描述**
```
 

```

**参数**

|名称|类型|说明|备注|
|:---|:---|:---|:---|
|||||
|||||

**返回值**

|名称|类型|说明|备注|
|:---|:---|:---|:---|
|||||
|||||


## 

**接口描述**
```
 

```

**参数**

|名称|类型|说明|备注|
|:---|:---|:---|:---|
|||||
|||||

**返回值**

|名称|类型|说明|备注|
|:---|:---|:---|:---|
|||||
|||||


## 

**接口描述**
```
 

```

**参数**

|名称|类型|说明|备注|
|:---|:---|:---|:---|
|||||
|||||

**返回值**

|名称|类型|说明|备注|
|:---|:---|:---|:---|
|||||
|||||


## 

**接口描述**
```
 

```

**参数**

|名称|类型|说明|备注|
|:---|:---|:---|:---|
|||||
|||||

**返回值**

|名称|类型|说明|备注|
|:---|:---|:---|:---|
|||||
|||||


## 

**接口描述**
```
 

```

**参数**

|名称|类型|说明|备注|
|:---|:---|:---|:---|
|||||
|||||

**返回值**

|名称|类型|说明|备注|
|:---|:---|:---|:---|
|||||
|||||


## 

**接口描述**
```
 

```

**参数**

|名称|类型|说明|备注|
|:---|:---|:---|:---|
|||||
|||||

**返回值**

|名称|类型|说明|备注|
|:---|:---|:---|:---|
|||||
|||||


## 

**接口描述**
```
 

```

**参数**

|名称|类型|说明|备注|
|:---|:---|:---|:---|
|||||
|||||

**返回值**

|名称|类型|说明|备注|
|:---|:---|:---|:---|
|||||
|||||


## 

**接口描述**
```
 

```

**参数**

|名称|类型|说明|备注|
|:---|:---|:---|:---|
|||||
|||||

**返回值**

|名称|类型|说明|备注|
|:---|:---|:---|:---|
|||||
|||||


## 

**接口描述**
```
 

```

**参数**

|名称|类型|说明|备注|
|:---|:---|:---|:---|
|||||
|||||

**返回值**

|名称|类型|说明|备注|
|:---|:---|:---|:---|
|||||
|||||


## 

**接口描述**
```
 

```

**参数**

|名称|类型|说明|备注|
|:---|:---|:---|:---|
|||||
|||||

**返回值**

|名称|类型|说明|备注|
|:---|:---|:---|:---|
|||||
|||||


## 

**接口描述**
```
 

```

**参数**

|名称|类型|说明|备注|
|:---|:---|:---|:---|
|||||
|||||

**返回值**

|名称|类型|说明|备注|
|:---|:---|:---|:---|
|||||
|||||


## 

**接口描述**
```
 

```

**参数**

|名称|类型|说明|备注|
|:---|:---|:---|:---|
|||||
|||||

**返回值**

|名称|类型|说明|备注|
|:---|:---|:---|:---|
|||||
|||||


## 

**接口描述**
```
 

```

**参数**

|名称|类型|说明|备注|
|:---|:---|:---|:---|
|||||
|||||

**返回值**

|名称|类型|说明|备注|
|:---|:---|:---|:---|
|||||
|||||


## 

**接口描述**
```
 

```

**参数**

|名称|类型|说明|备注|
|:---|:---|:---|:---|
|||||
|||||

**返回值**

|名称|类型|说明|备注|
|:---|:---|:---|:---|
|||||
|||||


## 

**接口描述**
```
 

```

**参数**

|名称|类型|说明|备注|
|:---|:---|:---|:---|
|||||
|||||

**返回值**

|名称|类型|说明|备注|
|:---|:---|:---|:---|
|||||
|||||


## 

**接口描述**
```
 

```

**参数**

|名称|类型|说明|备注|
|:---|:---|:---|:---|
|||||
|||||

**返回值**

|名称|类型|说明|备注|
|:---|:---|:---|:---|
|||||
|||||


## 

**接口描述**
```
 

```

**参数**

|名称|类型|说明|备注|
|:---|:---|:---|:---|
|||||
|||||

**返回值**

|名称|类型|说明|备注|
|:---|:---|:---|:---|
|||||
|||||


----------------------


## 

**接口描述**
```
 

```

**参数**

|名称|类型|说明|备注|
|:---|:---|:---|:---|
|||||
|||||

**返回值**

|名称|类型|说明|备注|
|:---|:---|:---|:---|
|||||
|||||



