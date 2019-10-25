# Protocol Documentation
<a name="top"></a>

## Table of Contents

- [proto/api/v1/quote.proto](#proto/api/v1/quote.proto)
    - [ContractRealTime](#biss.api.v1.quote.ContractRealTime)
    - [FundRealTime](#biss.api.v1.quote.FundRealTime)
    - [FundRealTime.ETFFundRealTime](#biss.api.v1.quote.FundRealTime.ETFFundRealTime)
    - [KLineData](#biss.api.v1.quote.KLineData)
    - [KLineHistoryReq](#biss.api.v1.quote.KLineHistoryReq)
    - [KLineHistoryResp](#biss.api.v1.quote.KLineHistoryResp)
    - [KLineReq](#biss.api.v1.quote.KLineReq)
    - [KLineUpdate](#biss.api.v1.quote.KLineUpdate)
    - [PeroidData](#biss.api.v1.quote.PeroidData)
    - [PositionData](#biss.api.v1.quote.PositionData)
    - [PositionReq](#biss.api.v1.quote.PositionReq)
    - [PositionUpdate](#biss.api.v1.quote.PositionUpdate)
    - [PositionUpdateItem](#biss.api.v1.quote.PositionUpdateItem)
    - [RealTimeReq](#biss.api.v1.quote.RealTimeReq)
    - [RealTimeUpdate](#biss.api.v1.quote.RealTimeUpdate)
    - [RealTimeUpdates](#biss.api.v1.quote.RealTimeUpdates)
    - [SubTickReq](#biss.api.v1.quote.SubTickReq)
    - [TickData](#biss.api.v1.quote.TickData)
    - [TickHistoryReq](#biss.api.v1.quote.TickHistoryReq)
    - [TickHistoryResp](#biss.api.v1.quote.TickHistoryResp)
    - [TickUpdate](#biss.api.v1.quote.TickUpdate)
    - [UsStockRealTime](#biss.api.v1.quote.UsStockRealTime)
  
    - [KLinePeroid](#biss.api.v1.quote.KLinePeroid)
    - [UpdateMode](#biss.api.v1.quote.UpdateMode)
  
  
    - [Quote](#biss.api.v1.quote.Quote)
  

- [Scalar Value Types](#scalar-value-types)



<a name="proto/api/v1/quote.proto"></a>
<p align="right"><a href="#top">Top</a></p>

## proto/api/v1/quote.proto



<a name="biss.api.v1.quote.ContractRealTime"></a>

### ContractRealTime
合约行情


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| mark_price | [string](#string) |  | 标记价格 |
| index_price | [string](#string) |  | 指数价格 |
| open_interest | [string](#string) |  | 未平仓合约数量 |
| funding_rate | [string](#string) |  | 资金费率 |
| predicted_funding_rate | [string](#string) |  | 预期资金费率 |
| countdown_hour | [string](#string) |  | 结算时间间隔 |






<a name="biss.api.v1.quote.FundRealTime"></a>

### FundRealTime
基金行情


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| nav | [string](#string) |  | 基金净值 |
| iopv | [string](#string) |  | 基金净值预估 |
| etf | [FundRealTime.ETFFundRealTime](#biss.api.v1.quote.FundRealTime.ETFFundRealTime) |  | ETF 基金参数 |






<a name="biss.api.v1.quote.FundRealTime.ETFFundRealTime"></a>

### FundRealTime.ETFFundRealTime



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| tracker | [biss.common.trade.Ticker](#biss.common.trade.Ticker) |  | 锚定对象 |
| price | [string](#string) |  | 当前价 |
| ratio | [string](#string) |  | 涨跌幅 |






<a name="biss.api.v1.quote.KLineData"></a>

### KLineData
单条 K 线数据


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| time | [uint64](#uint64) |  | K 线周期开始时间，纳秒精度 |
| data | [PeroidData](#biss.api.v1.quote.PeroidData) |  | K 线数据 |






<a name="biss.api.v1.quote.KLineHistoryReq"></a>

### KLineHistoryReq
K 线历史数据请求


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| ticker | [biss.common.trade.Ticker](#biss.common.trade.Ticker) |  | 标的 |
| peroid | [KLinePeroid](#biss.api.v1.quote.KLinePeroid) |  | 周期 |
| offset | [uint64](#uint64) |  | 读取起始位置，0 表示最新位置 |
| count | [uint32](#uint32) |  | 读取记录数量 |
| data_direction | [biss.common.SortDirection](#biss.common.SortDirection) |  | 数据读取方向, 默认倒序 |
| sort_direction | [biss.common.SortDirection](#biss.common.SortDirection) |  | 结果排序方向，默认增序 |






<a name="biss.api.v1.quote.KLineHistoryResp"></a>

### KLineHistoryResp
K 线历史数据请求应答


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| ticker | [biss.common.trade.Ticker](#biss.common.trade.Ticker) |  | 标的 |
| peroid | [KLinePeroid](#biss.api.v1.quote.KLinePeroid) |  | 周期 |
| offset | [uint64](#uint64) |  | 读取起始位置，0 表示最新位置 |
| count | [uint32](#uint32) |  | 读取记录数量 |
| data_direction | [biss.common.SortDirection](#biss.common.SortDirection) |  | 数据读取方向, 默认倒序 |
| sort_direction | [biss.common.SortDirection](#biss.common.SortDirection) |  | 结果排序方向，默认增序 |
| lines | [KLineData](#biss.api.v1.quote.KLineData) | repeated | 历史 K 线数据列表 |






<a name="biss.api.v1.quote.KLineReq"></a>

### KLineReq
K 线数据订阅请求


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| ticker | [biss.common.trade.Ticker](#biss.common.trade.Ticker) |  | 标的 |
| peroid | [KLinePeroid](#biss.api.v1.quote.KLinePeroid) |  | K 线数据 |






<a name="biss.api.v1.quote.KLineUpdate"></a>

### KLineUpdate
K 线数据更新


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| ticker | [biss.common.trade.Ticker](#biss.common.trade.Ticker) |  | 标的 |
| peroid | [KLinePeroid](#biss.api.v1.quote.KLinePeroid) |  | K 线周期 |
| line | [KLineData](#biss.api.v1.quote.KLineData) |  | K 线数据 |






<a name="biss.api.v1.quote.PeroidData"></a>

### PeroidData
行情周期性数据，如 24 小时周期数据、2 小时涨停板周期数据、K 线数据


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| open | [string](#string) |  | 开盘价 |
| close | [string](#string) |  | 收盘价 |
| volume | [string](#string) |  | 成交量 |
| change | [string](#string) |  | 涨跌价 |
| ratio | [string](#string) |  | 涨跌幅 |
| high | [string](#string) |  | 最高价 |
| low | [string](#string) |  | 最低价 |
| amount | [string](#string) |  | 成交额 |
| avg | [string](#string) |  | 均价 |
| start_time | [uint64](#uint64) |  | 周期开始时间 |
| end_time | [uint64](#uint64) |  | 周期结束时间 |
| price_up_limit | [string](#string) |  | 周期最高价格 |
| price_down_limit | [string](#string) |  | 周期最低价格 |






<a name="biss.api.v1.quote.PositionData"></a>

### PositionData
盘口数据


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| level | [uint32](#uint32) |  | 盘口深度级别 |
| price | [string](#string) |  | 价格 |
| volume | [string](#string) |  | 数量 |
| amount | [string](#string) |  | 总额 |
| order_qty | [string](#string) | repeated | 当前报价的委托队列 |






<a name="biss.api.v1.quote.PositionReq"></a>

### PositionReq
盘口深度行情数据请求


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| ticker | [biss.common.trade.Ticker](#biss.common.trade.Ticker) |  | 成交 |
| precision | [string](#string) |  | 盘口合并深度 |






<a name="biss.api.v1.quote.PositionUpdate"></a>

### PositionUpdate
盘口数据更新请求应答


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| ticker | [biss.common.trade.Ticker](#biss.common.trade.Ticker) |  | 标的 |
| precision | [string](#string) |  | 盘口合并深度 |
| items | [PositionUpdateItem](#biss.api.v1.quote.PositionUpdateItem) | repeated | 数据列表 |






<a name="biss.api.v1.quote.PositionUpdateItem"></a>

### PositionUpdateItem
单条盘口数据更新


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| mode | [UpdateMode](#biss.api.v1.quote.UpdateMode) |  | 更新模式 |
| bids | [PositionData](#biss.api.v1.quote.PositionData) | repeated | 买单更新列表 |
| asks | [PositionData](#biss.api.v1.quote.PositionData) | repeated | 卖单更新列表 |






<a name="biss.api.v1.quote.RealTimeReq"></a>

### RealTimeReq
实时行情请求


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| tickers | [biss.common.trade.Ticker](#biss.common.trade.Ticker) | repeated | 请求的ticker列表，包含请求单个ticker |






<a name="biss.api.v1.quote.RealTimeUpdate"></a>

### RealTimeUpdate
实时行情更新数据


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| ticker | [biss.common.trade.Ticker](#biss.common.trade.Ticker) |  | 标的 |
| price | [string](#string) |  | biss.common.trade.TickerInfo info = 2;

现价 |
| h24 | [PeroidData](#biss.api.v1.quote.PeroidData) |  | 24 小时周期数据 |
| tick_time | [uint64](#uint64) |  | 最新的tick的时间 |
| quote_time | [uint64](#uint64) |  | tick时间对应的行情服务器的时间 |
| cirulating_supply | [string](#string) |  | 当前流通量 |
| max_supply | [string](#string) |  | 总发行量 |
| usstock | [UsStockRealTime](#biss.api.v1.quote.UsStockRealTime) |  | 美股周期数据 |
| trade_peroid | [PeroidData](#biss.api.v1.quote.PeroidData) |  | 周期数据 |
| category | [biss.common.trade.Category](#biss.common.trade.Category) |  | 类型 |
| sub_category | [biss.common.trade.SubCategory](#biss.common.trade.SubCategory) |  | 类型 |
| fund | [FundRealTime](#biss.api.v1.quote.FundRealTime) |  | 基金行情 |
| contract | [ContractRealTime](#biss.api.v1.quote.ContractRealTime) |  | 合约行情 |






<a name="biss.api.v1.quote.RealTimeUpdates"></a>

### RealTimeUpdates
实时行情更新数据列表，即实时行情请求应答


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| updates | [RealTimeUpdate](#biss.api.v1.quote.RealTimeUpdate) | repeated | 数据列表 |






<a name="biss.api.v1.quote.SubTickReq"></a>

### SubTickReq
成交推送订阅请求


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| ticker | [biss.common.trade.Ticker](#biss.common.trade.Ticker) |  | 标的 |
| last | [uint32](#uint32) |  | 订阅成功后，立即返回的历史最新 Tick 数量 |






<a name="biss.api.v1.quote.TickData"></a>

### TickData
单笔成交 (Tick) 数据


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| id | [uint64](#uint64) |  | 成交序号 |
| time | [uint64](#uint64) |  | 成交时间 |
| price | [string](#string) |  | 成交价格 |
| volume | [string](#string) |  | 成交数量 |
| amount | [string](#string) |  | 成交额 |
| side | [biss.common.trade.TradeSide](#biss.common.trade.TradeSide) |  | 主买主卖方向 |
| bid_order_no | [uint64](#uint64) |  | 买单编号 |
| bid_order_qty | [string](#string) |  | 买单数量 |
| ask_order_no | [uint64](#uint64) |  | 卖单编号 |
| ask_order_qty | [string](#string) |  | 卖单数量 |






<a name="biss.api.v1.quote.TickHistoryReq"></a>

### TickHistoryReq
历史逐笔成交数据请求


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| ticker | [biss.common.trade.Ticker](#biss.common.trade.Ticker) |  | 标的 |
| start | [uint64](#uint64) |  | 起始成交标号 |
| count | [uint32](#uint32) |  | 数量 |






<a name="biss.api.v1.quote.TickHistoryResp"></a>

### TickHistoryResp
历史逐笔成交数据请求应答


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| ticker | [biss.common.trade.Ticker](#biss.common.trade.Ticker) |  | 标的 |
| start | [uint64](#uint64) |  | 其实成交编号 |
| count | [uint32](#uint32) |  | 数量 |
| ticks | [TickData](#biss.api.v1.quote.TickData) | repeated | 成交数据列表 |






<a name="biss.api.v1.quote.TickUpdate"></a>

### TickUpdate
逐笔成交数据更新


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| ticker | [biss.common.trade.Ticker](#biss.common.trade.Ticker) |  | 标的 |
| tick | [TickData](#biss.api.v1.quote.TickData) |  | 数据 |






<a name="biss.api.v1.quote.UsStockRealTime"></a>

### UsStockRealTime
美股实时行情周期性数据


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| base | [PeroidData](#biss.api.v1.quote.PeroidData) |  |  |
| high52 | [string](#string) |  |  |
| low52 | [string](#string) |  |  |
| mktcap | [string](#string) |  | 市值 |
| qpr2rev | [string](#string) |  | 市盈率 |
| apenorm | [string](#string) |  | 市盈率动 |
| price2bk | [string](#string) |  | 市净率 |
| ttmpr2rev | [string](#string) |  | 市销率 |
| state | [uint32](#uint32) |  | 0: 闭盘 1:开盘 |
| open_min | [uint32](#uint32) |  | 距离开盘时间（分钟） |





 


<a name="biss.api.v1.quote.KLinePeroid"></a>

### KLinePeroid
K 线周期

| Name | Number | Description |
| ---- | ------ | ----------- |
| KP_NONE | 0 |  |
| KP_MIN | 1 |  |
| KP_5_MIN | 2 |  |
| KP_15_MIN | 3 |  |
| KP_30_MIN | 4 |  |
| KP_HOUR | 5 |  |
| KP_2_HOUR | 6 |  |
| KP_4_HOUR | 7 |  |
| KP_8_HOUR | 8 |  |
| KP_12_HOUR | 9 |  |
| KP_DAY | 10 |  |
| KP_WEEK | 11 |  |
| KP_MONTH | 12 |  |
| KP_QUAR | 13 |  |
| KP_YEAR | 14 |  |



<a name="biss.api.v1.quote.UpdateMode"></a>

### UpdateMode
更新模式

| Name | Number | Description |
| ---- | ------ | ----------- |
| UM_NONE | 0 |  |
| UM_OVERRIDE | 1 | 全局覆盖 |
| UM_MODIFY | 2 | 修改 |
| UM_ADD | 3 | 添加 |
| UM_DELETE | 4 | 删除 |


 

 


<a name="biss.api.v1.quote.Quote"></a>

### Quote


| Method Name | Request Type | Response Type | Description |
| ----------- | ------------ | ------------- | ------------|
| RealTime | [.biss.common.trade.Ticker](#biss.common.trade.Ticker) | [RealTimeUpdate](#biss.api.v1.quote.RealTimeUpdate) | 请求实时行情 |
| BatchRealTime | [.biss.common.trade.Market](#biss.common.trade.Market) | [RealTimeUpdates](#biss.api.v1.quote.RealTimeUpdates) | 批量请求实时行情 |
| KLineHistory | [KLineHistoryReq](#biss.api.v1.quote.KLineHistoryReq) | [KLineHistoryResp](#biss.api.v1.quote.KLineHistoryResp) | 请求 K 线历史数据 |
| TickHistory | [TickHistoryReq](#biss.api.v1.quote.TickHistoryReq) | [TickHistoryResp](#biss.api.v1.quote.TickHistoryResp) | 请求逐笔成交 (Tick) 历史数据 |
| Position | [PositionReq](#biss.api.v1.quote.PositionReq) | [PositionUpdate](#biss.api.v1.quote.PositionUpdate) | 请求盘口深度数据 |
| SubRealTime | [RealTimeReq](#biss.api.v1.quote.RealTimeReq) | [RealTimeUpdate](#biss.api.v1.quote.RealTimeUpdate) stream | 订阅实时行情 |
| SubTick | [SubTickReq](#biss.api.v1.quote.SubTickReq) | [TickUpdate](#biss.api.v1.quote.TickUpdate) stream | 订阅逐笔 (Tick) 行情 |
| SubKLine | [KLineReq](#biss.api.v1.quote.KLineReq) | [KLineUpdate](#biss.api.v1.quote.KLineUpdate) stream | 订阅 K 线行情 |
| SubPosition | [PositionReq](#biss.api.v1.quote.PositionReq) | [PositionUpdate](#biss.api.v1.quote.PositionUpdate) stream | 订阅盘口行情 |

 



## Scalar Value Types

| .proto Type | Notes | C++ Type | Java Type | Python Type |
| ----------- | ----- | -------- | --------- | ----------- |
| <a name="double" /> double |  | double | double | float |
| <a name="float" /> float |  | float | float | float |
| <a name="int32" /> int32 | Uses variable-length encoding. Inefficient for encoding negative numbers – if your field is likely to have negative values, use sint32 instead. | int32 | int | int |
| <a name="int64" /> int64 | Uses variable-length encoding. Inefficient for encoding negative numbers – if your field is likely to have negative values, use sint64 instead. | int64 | long | int/long |
| <a name="uint32" /> uint32 | Uses variable-length encoding. | uint32 | int | int/long |
| <a name="uint64" /> uint64 | Uses variable-length encoding. | uint64 | long | int/long |
| <a name="sint32" /> sint32 | Uses variable-length encoding. Signed int value. These more efficiently encode negative numbers than regular int32s. | int32 | int | int |
| <a name="sint64" /> sint64 | Uses variable-length encoding. Signed int value. These more efficiently encode negative numbers than regular int64s. | int64 | long | int/long |
| <a name="fixed32" /> fixed32 | Always four bytes. More efficient than uint32 if values are often greater than 2^28. | uint32 | int | int |
| <a name="fixed64" /> fixed64 | Always eight bytes. More efficient than uint64 if values are often greater than 2^56. | uint64 | long | int/long |
| <a name="sfixed32" /> sfixed32 | Always four bytes. | int32 | int | int |
| <a name="sfixed64" /> sfixed64 | Always eight bytes. | int64 | long | int/long |
| <a name="bool" /> bool |  | bool | boolean | boolean |
| <a name="string" /> string | A string must always contain UTF-8 encoded or 7-bit ASCII text. | string | String | str/unicode |
| <a name="bytes" /> bytes | May contain any arbitrary sequence of bytes. | string | ByteString | str |

