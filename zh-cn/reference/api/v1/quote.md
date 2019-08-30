



# biss.api.v1.quote.Quote



## RealTime

请求实时行情
    
> `GRPC` RealTime([.biss.common.trade.Ticker](#.biss.common.trade.Ticker)) return [RealTimeUpdate](#RealTimeUpdate)






> `HTTP` `GET` /v1/quote/{symbol}/{market}/realtime
 <!-- end with -->
 <!-- end if -->
 <!-- end if -->
 <!-- end with -->

## BatchRealTime

批量请求实时行情
    
> `GRPC` BatchRealTime([.biss.common.trade.Market](#.biss.common.trade.Market)) return [RealTimeUpdates](#RealTimeUpdates)






> `HTTP` `GET` /v1/quote/batch/realtime/{market}
 <!-- end with -->
 <!-- end if -->
 <!-- end if -->
 <!-- end with -->

## KLineHistory

请求 K 线历史数据
    
> `GRPC` KLineHistory([KLineHistoryReq](#KLineHistoryReq)) return [KLineHistoryResp](#KLineHistoryResp)






> `HTTP` `GET` /v1/quote/kline
 <!-- end with -->
 <!-- end if -->
 <!-- end if -->
 <!-- end with -->

## TickHistory

请求逐笔成交 (Tick) 历史数据
    
> `GRPC` TickHistory([TickHistoryReq](#TickHistoryReq)) return [TickHistoryResp](#TickHistoryResp)






> `HTTP` `GET` /v1/quote/{ticker.symbol}/{ticker.market}/tick-history
 <!-- end with -->
 <!-- end if -->
 <!-- end if -->
 <!-- end with -->

## Position

请求盘口深度数据
    
> `GRPC` Position([PositionReq](#PositionReq)) return [PositionUpdate](#PositionUpdate)






> `HTTP` `GET` /v1/quote/{ticker.symbol}/{ticker.market}/position
 <!-- end with -->
 <!-- end if -->
 <!-- end if -->
 <!-- end with -->

## SubRealTime

订阅实时行情
    
> `GRPC` SubRealTime([RealTimeReq](#RealTimeReq)) return [RealTimeUpdate](#RealTimeUpdate) `stream`


 <!-- end with -->

## SubTick

订阅逐笔 (Tick) 行情
    
> `GRPC` SubTick([SubTickReq](#SubTickReq)) return [TickUpdate](#TickUpdate) `stream`


 <!-- end with -->

## SubKLine

订阅 K 线行情
    
> `GRPC` SubKLine([KLineReq](#KLineReq)) return [KLineUpdate](#KLineUpdate) `stream`


 <!-- end with -->

## SubPosition

订阅盘口行情
    
> `GRPC` SubPosition([PositionReq](#PositionReq)) return [PositionUpdate](#PositionUpdate) `stream`


 <!-- end with -->

 <!-- end methods -->
 <!-- end services -->


# 数据对象



## FundRealTime

基金行情


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| nav | [string](#string) |  | 基金净值 |
| iopv | [string](#string) |  | 基金净值预估 |
| etf | [FundRealTime.ETFFundRealTime](#FundRealTime.ETFFundRealTime) |  | ETF 基金参数 |




## FundRealTime.ETFFundRealTime




| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| tracker | [biss.common.trade.Ticker](#biss.common.trade.Ticker) |  | 锚定对象 |
| price | [string](#string) |  | 当前价 |
| ratio | [string](#string) |  | 涨跌幅 |




## KLineData

单条 K 线数据


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| time | [uint64](#uint64) |  | K 线周期开始时间，纳秒精度 |
| data | [PeroidData](#PeroidData) |  | K 线数据 |




## KLineHistoryReq

K 线历史数据请求


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| ticker | [biss.common.trade.Ticker](#biss.common.trade.Ticker) |  | 标的 |
| peroid | [KLinePeroid](#KLinePeroid) |  | 周期 |
| offset | [uint64](#uint64) |  | 读取起始位置，0 表示最新位置 |
| count | [uint32](#uint32) |  | 读取记录数量 |
| data_direction | [biss.common.SortDirection](#biss.common.SortDirection) |  | 数据读取方向, 默认倒序 |
| sort_direction | [biss.common.SortDirection](#biss.common.SortDirection) |  | 结果排序方向，默认增序 |




## KLineHistoryResp

K 线历史数据请求应答


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| ticker | [biss.common.trade.Ticker](#biss.common.trade.Ticker) |  | 标的 |
| peroid | [KLinePeroid](#KLinePeroid) |  | 周期 |
| offset | [uint64](#uint64) |  | 读取起始位置，0 表示最新位置 |
| count | [uint32](#uint32) |  | 读取记录数量 |
| data_direction | [biss.common.SortDirection](#biss.common.SortDirection) |  | 数据读取方向, 默认倒序 |
| sort_direction | [biss.common.SortDirection](#biss.common.SortDirection) |  | 结果排序方向，默认增序 |
| lines | [KLineData](#KLineData) | repeated | 历史 K 线数据列表 |




## KLineReq

K 线数据订阅请求


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| ticker | [biss.common.trade.Ticker](#biss.common.trade.Ticker) |  | 标的 |
| peroid | [KLinePeroid](#KLinePeroid) |  | K 线数据 |




## KLineUpdate

K 线数据更新


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| ticker | [biss.common.trade.Ticker](#biss.common.trade.Ticker) |  | 标的 |
| peroid | [KLinePeroid](#KLinePeroid) |  | K 线周期 |
| line | [KLineData](#KLineData) |  | K 线数据 |




## PeroidData

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




## PositionData

盘口数据


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| level | [uint32](#uint32) |  | 盘口深度级别 |
| price | [string](#string) |  | 价格 |
| volume | [string](#string) |  | 数量 |
| amount | [string](#string) |  | 总额 |
| order_qty | [string](#string) | repeated | 当前报价的委托队列 |




## PositionReq

盘口深度行情数据请求


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| ticker | [biss.common.trade.Ticker](#biss.common.trade.Ticker) |  | 成交 |
| precision | [string](#string) |  | 盘口合并深度 |




## PositionUpdate

盘口数据更新请求应答


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| ticker | [biss.common.trade.Ticker](#biss.common.trade.Ticker) |  | 标的 |
| precision | [string](#string) |  | 盘口合并深度 |
| items | [PositionUpdateItem](#PositionUpdateItem) | repeated | 数据列表 |




## PositionUpdateItem

单条盘口数据更新


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| mode | [UpdateMode](#UpdateMode) |  | 更新模式 |
| bids | [PositionData](#PositionData) | repeated | 买单更新列表 |
| asks | [PositionData](#PositionData) | repeated | 卖单更新列表 |




## RealTimeReq

实时行情请求


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| tickers | [biss.common.trade.Ticker](#biss.common.trade.Ticker) | repeated | 请求的ticker列表，包含请求单个ticker |




## RealTimeUpdate

实时行情更新数据


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| ticker | [biss.common.trade.Ticker](#biss.common.trade.Ticker) |  | 标的 |
| price | [string](#string) |  | biss.common.trade.TickerInfo info = 2;

现价 |
| h24 | [PeroidData](#PeroidData) |  | 24 小时周期数据 |
| tick_time | [uint64](#uint64) |  | 最新的tick的时间 |
| quote_time | [uint64](#uint64) |  | tick时间对应的行情服务器的时间 |
| cirulating_supply | [string](#string) |  | 当前流通量 |
| max_supply | [string](#string) |  | 总发行量 |
| usstock | [UsStockRealTime](#UsStockRealTime) |  | 美股周期数据 |
| trade_peroid | [PeroidData](#PeroidData) |  | 周期数据 |
| category | [biss.common.trade.Category](#biss.common.trade.Category) |  | 类型 |
| sub_category | [biss.common.trade.SubCategory](#biss.common.trade.SubCategory) |  | 类型 |
| fund | [FundRealTime](#FundRealTime) |  | 基金行情 |




## RealTimeUpdates

实时行情更新数据列表，即实时行情请求应答


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| updates | [RealTimeUpdate](#RealTimeUpdate) | repeated | 数据列表 |




## SubTickReq

成交推送订阅请求


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| ticker | [biss.common.trade.Ticker](#biss.common.trade.Ticker) |  | 标的 |
| last | [uint32](#uint32) |  | 订阅成功后，立即返回的历史最新 Tick 数量 |




## TickData

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




## TickHistoryReq

历史逐笔成交数据请求


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| ticker | [biss.common.trade.Ticker](#biss.common.trade.Ticker) |  | 标的 |
| start | [uint64](#uint64) |  | 起始成交标号 |
| count | [uint32](#uint32) |  | 数量 |




## TickHistoryResp

历史逐笔成交数据请求应答


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| ticker | [biss.common.trade.Ticker](#biss.common.trade.Ticker) |  | 标的 |
| start | [uint64](#uint64) |  | 其实成交编号 |
| count | [uint32](#uint32) |  | 数量 |
| ticks | [TickData](#TickData) | repeated | 成交数据列表 |




## TickUpdate

逐笔成交数据更新


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| ticker | [biss.common.trade.Ticker](#biss.common.trade.Ticker) |  | 标的 |
| tick | [TickData](#TickData) |  | 数据 |




## UsStockRealTime

美股实时行情周期性数据


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| base | [PeroidData](#PeroidData) |  |  |
| high52 | [string](#string) |  |  |
| low52 | [string](#string) |  |  |
| mktcap | [string](#string) |  | 市值 |
| qpr2rev | [string](#string) |  | 市盈率 |
| apenorm | [string](#string) |  | 市盈率动 |
| price2bk | [string](#string) |  | 市净率 |
| ttmpr2rev | [string](#string) |  | 市销率 |
| state | [uint32](#uint32) |  | 0: 闭盘 1:开盘 |
| open_min | [uint32](#uint32) |  | 距离开盘时间（分钟） |


 <!-- end messages -->

# 枚举类型


<a name="biss.api.v1.quote.KLinePeroid"></a>

## KLinePeroid
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

## UpdateMode
更新模式

| Name | Number | Description |
| ---- | ------ | ----------- |
| UM_NONE | 0 |  |
| UM_OVERRIDE | 1 | 全局覆盖 |
| UM_MODIFY | 2 | 修改 |
| UM_ADD | 3 | 添加 |
| UM_DELETE | 4 | 删除 |


 <!-- end enums -->



