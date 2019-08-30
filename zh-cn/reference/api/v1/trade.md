



# biss.api.v1.trade.Trade



## TickerInfo

获取标的信息
    
> `GRPC` TickerInfo([.biss.common.trade.Ticker](#.biss.common.trade.Ticker)) return [TickerInfoResp](#TickerInfoResp)


 <!-- end with -->

## Affordability

可买可卖查询
    
> `GRPC` Affordability([AffordabilityReq](#AffordabilityReq)) return [AffordabilityResp](#AffordabilityResp)


 <!-- end with -->

## Entrust

委托下单
    
> `GRPC` Entrust([EntrustReq](#EntrustReq)) return [EntrustResp](#EntrustResp)






> `HTTP` `POST` /v1/trade/{ticker.symbol}/{ticker.market}
 <!-- end with -->
 <!-- end if -->
 <!-- end if -->
 <!-- end with -->

## BatchEntrust

批量委托下单
    
> `GRPC` BatchEntrust([BatchEntrustReq](#BatchEntrustReq)) return [BatchEntrustResp](#BatchEntrustResp)






> `HTTP` `POST` /v1/trade/batch_entrust
 <!-- end with -->
 <!-- end if -->
 <!-- end if -->
 <!-- end with -->

## Cancel

取消订单
    
> `GRPC` Cancel([CancelReq](#CancelReq)) return [.biss.common.Empty](#.biss.common.Empty)






> `HTTP` `DELETE` /v1/trade/{ticker.symbol}/{ticker.market}/{oid}
 <!-- end with -->
 <!-- end if -->
 <!-- end if -->
 <!-- end with -->

## BatchCancel

批量取消订单
    
> `GRPC` BatchCancel([BatchCancelReq](#BatchCancelReq)) return [.biss.common.Empty](#.biss.common.Empty)


 <!-- end with -->

## CancelAll

全部取消订单
    
> `GRPC` CancelAll([CancelAllReq](#CancelAllReq)) return [.biss.common.Empty](#.biss.common.Empty)






> `HTTP` `DELETE` /v1/trade/{ticker.symbol}/{ticker.market}
 <!-- end with -->
 <!-- end if -->
 <!-- end if -->
 <!-- end with -->

## EntrustInfo

委托信息(获取单个order信息)
    
> `GRPC` EntrustInfo([EntrustInfoReq](#EntrustInfoReq)) return [EntrustInfoResp](#EntrustInfoResp)






> `HTTP` `GET` /v1/trade/{ticker.symbol}/{ticker.market}/{oid}
 <!-- end with -->
 <!-- end if -->
 <!-- end if -->
 <!-- end with -->

## BatchEntrustInfo

委托信息(获取多个order信息)
    
> `GRPC` BatchEntrustInfo([BatchEntrustInfoReq](#BatchEntrustInfoReq)) return [BatchEntrustInfoResp](#BatchEntrustInfoResp)






> `HTTP` `GET` /v1/trade/{ticker.symbol}/{ticker.market}/list
 <!-- end with -->
 <!-- end if -->
 <!-- end if -->
 <!-- end with -->

## EntrustList

委托列表
    
> `GRPC` EntrustList([OrderListReq](#OrderListReq)) return [OrderListResp](#OrderListResp)






> `HTTP` `GET` /v1/trade/{ticker.symbol}/{ticker.market}
 <!-- end with -->
 <!-- end if -->
 <!-- end if -->
 <!-- end with -->

## OrderHistoryList

历史订单记录
    
> `GRPC` OrderHistoryList([OrderListReq](#OrderListReq)) return [OrderListResp](#OrderListResp)


 <!-- end with -->

## PositionList

持仓列表
    
> `GRPC` PositionList([PositionListReq](#PositionListReq)) return [PositionListResp](#PositionListResp)


 <!-- end with -->

## PositionBrief

持仓状态
    
> `GRPC` PositionBrief([.biss.common.Empty](#.biss.common.Empty)) return [PositionBriefResp](#PositionBriefResp) `stream`


 <!-- end with -->

 <!-- end methods -->
 <!-- end services -->


# 数据对象



## AffordabilityReq




| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| ticker | [biss.common.trade.Ticker](#biss.common.trade.Ticker) |  |  |
| side | [biss.common.trade.TradeSide](#biss.common.trade.TradeSide) |  |  |
| type | [biss.common.trade.OrderType](#biss.common.trade.OrderType) |  | 订单类型 |
| price | [string](#string) |  | 尝试的交易价格 |
| qty | [string](#string) |  | 尝试交易数量 |




## AffordabilityResp




| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| ticker | [biss.common.trade.Ticker](#biss.common.trade.Ticker) |  |  |
| asset | [string](#string) |  | 用户资产 |
| afford_qty | [string](#string) |  |  |
| total | [string](#string) |  |  |
| fee | [string](#string) |  | 手续费 |
| fee_ratio | [string](#string) |  |  |
| usdt2usd | [string](#string) |  |  |




## BatchCancelReq




| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| order_indexs | [OrderIndex](#OrderIndex) | repeated |  |




## BatchEntrustInfoReq




| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| ticker | [biss.common.trade.Ticker](#biss.common.trade.Ticker) |  |  |
| oids | [uint64](#uint64) | repeated |  |




## BatchEntrustInfoResp




| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| order_infos | [Order](#Order) | repeated | order 信息 |




## BatchEntrustReq




| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| reqs | [EntrustReq](#EntrustReq) | repeated | 批量委托请求数组 |




## BatchEntrustResp




| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| resps | [EntrustResp](#EntrustResp) | repeated | 批量委托应答数组，长度、顺序与 BatchEntrustReq.reqs 一致 |




## CancelAllReq




| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| ticker | [biss.common.trade.Ticker](#biss.common.trade.Ticker) |  | 可有可无，有值就是撤销当前用户的该ticker的所有可撤委托 |




## CancelReq




| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| ticker | [biss.common.trade.Ticker](#biss.common.trade.Ticker) |  |  |
| oid | [uint64](#uint64) |  |  |




## EntrustInfoReq




| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| oid | [uint64](#uint64) |  | order id |
| ticker | [biss.common.trade.Ticker](#biss.common.trade.Ticker) |  |  |




## EntrustInfoResp




| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| order_info | [Order](#Order) |  | order 信息 |




## EntrustReq




| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| ticker | [biss.common.trade.Ticker](#biss.common.trade.Ticker) |  |  |
| type | [biss.common.trade.OrderType](#biss.common.trade.OrderType) |  |  |
| side | [biss.common.trade.TradeSide](#biss.common.trade.TradeSide) |  |  |
| price | [string](#string) |  |  |
| qty | [string](#string) |  |  |




## EntrustResp




| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| oid | [uint64](#uint64) |  | 订单编号 |
| code | [uint64](#uint64) |  | 错误码，批量委托使用 |
| failed | [bool](#bool) |  | 委托失败 |




## Order




| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| id | [uint64](#uint64) |  |  |
| type | [biss.common.trade.OrderType](#biss.common.trade.OrderType) |  | 订单类型 |
| side | [biss.common.trade.TradeSide](#biss.common.trade.TradeSide) |  | 交易方向 |
| price | [string](#string) |  | 价格 |
| qty | [string](#string) |  | 委托数量 |
| amount | [string](#string) |  | 交易额 |
| status | [biss.common.trade.OrderStatus](#biss.common.trade.OrderStatus) |  | 订单状态 |
| filled | [string](#string) |  | 已成交 |
| left | [string](#string) |  | 未成交 |
| time | [uint64](#uint64) |  | 委托时间 |
| ticker | [biss.common.trade.Ticker](#biss.common.trade.Ticker) |  | 交易对 |
| filled_avg | [string](#string) |  | 成交均价 |
| fee | [string](#string) |  | 手续费 |
| filledAmount | [string](#string) |  | 成交金额 |
| fillStatus | [biss.common.trade.OrderFillStatus](#biss.common.trade.OrderFillStatus) |  | 成交状态 |
| fill_ratio | [string](#string) |  |  |
| fees | [TradeFee](#TradeFee) | repeated | 手续费明细 |




## OrderIndex




| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| ticker | [biss.common.trade.Ticker](#biss.common.trade.Ticker) |  |  |
| oid | [uint64](#uint64) |  |  |




## OrderListReq




| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| page | [uint32](#uint32) |  |  |
| page_size | [uint32](#uint32) |  |  |
| sort_direction | [biss.common.SortDirection](#biss.common.SortDirection) |  |  |
| sort_type | [OrderListSortType](#OrderListSortType) |  |  |
| order_list_type | [biss.common.trade.OrderListType](#biss.common.trade.OrderListType) |  |  |
| ticker | [biss.common.trade.Ticker](#biss.common.trade.Ticker) |  |  |




## OrderListResp




| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| total | [uint32](#uint32) |  |  |
| page | [uint32](#uint32) |  |  |
| has_more | [bool](#bool) |  |  |
| sort_direction | [biss.common.SortDirection](#biss.common.SortDirection) |  |  |
| sort_type | [OrderListSortType](#OrderListSortType) |  |  |
| orders | [Order](#Order) | repeated |  |




## PositionBriefResp




| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| profit | [string](#string) |  | 盈亏 |
| ratio | [uint32](#uint32) |  | 盈亏比例 |
| hoding_amount | [string](#string) |  | 持仓市值 |
| current_amount | [string](#string) |  | 市值 |
| price_decimal | [uint32](#uint32) |  | 价格单位 |




## PositionListReq




| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| total | [uint32](#uint32) |  |  |
| page | [uint32](#uint32) |  |  |
| sort_direction | [biss.common.SortDirection](#biss.common.SortDirection) |  |  |
| sort_type | [PositionListSortType](#PositionListSortType) |  |  |




## PositionListResp




| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| total | [uint32](#uint32) |  |  |
| page | [uint32](#uint32) |  |  |
| has_more | [bool](#bool) |  |  |
| sort_direction | [biss.common.SortDirection](#biss.common.SortDirection) |  |  |
| sort_type | [PositionListSortType](#PositionListSortType) |  |  |
| positions | [PositionListResp.Position](#PositionListResp.Position) | repeated |  |




## PositionListResp.Position




| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| ticker | [biss.common.trade.Ticker](#biss.common.trade.Ticker) |  |  |
| hoding_price | [string](#string) |  | 持仓成本 |
| current_price | [string](#string) |  | 现价 |
| qty | [string](#string) |  | 数量 |
| hoding_amount | [string](#string) |  | 持仓市值 |
| current_amount | [string](#string) |  | 市值 |
| profit | [string](#string) |  | 盈亏 |
| ratio | [int32](#int32) |  | 盈亏比例 |




## Tick




| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| id | [uint64](#uint64) |  |  |
| type | [biss.common.trade.OrderType](#biss.common.trade.OrderType) |  | 订单类型 |
| side | [biss.common.trade.TradeSide](#biss.common.trade.TradeSide) |  | 交易方向 |
| price | [string](#string) |  | 价格 |
| qty | [string](#string) |  | 数量 |
| amount | [string](#string) |  | 市值 |
| fee | [string](#string) |  | 交易手续费 |
| time | [uint64](#uint64) |  | 成交时间 |
| ticker | [biss.common.trade.Ticker](#biss.common.trade.Ticker) |  | 交易对 |




## TickerInfo




| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| share_uint | [string](#string) |  | 交易单位，默认为 1 |
| min_bid_qty | [string](#string) |  | 最小买入数量 |
| max_bid_qty | [string](#string) |  | 最大买入数量 |
| min_ask_qty | [string](#string) |  | 最小卖出数量 |
| max_ask_qty | [string](#string) |  | 最大卖出数量 |
| trading_status | [biss.common.trade.TradingStatus](#biss.common.trade.TradingStatus) |  |  |
| vcm_info | [VCMInfo](#VCMInfo) |  | 波动中断信息 |




## TickerInfoResp




| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| ticker | [biss.common.trade.Ticker](#biss.common.trade.Ticker) |  |  |
| info | [TickerInfo](#TickerInfo) |  |  |




## TradeFee




| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| symbol | [string](#string) |  | 扣费币种 |
| qty | [string](#string) |  | 实扣数量 |
| original_qty | [string](#string) |  | 应扣数量 |
| discount_rate | [uint32](#uint32) |  | 平均折扣率，qty/original_qty*100 |




## VCMInfo




| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| upper_price_limit | [string](#string) |  | 触发上限 |
| lower_price_limit | [string](#string) |  | 触发下限 |
| cooling_off_period | [uint64](#uint64) |  | 冷却时间 |
| status | [VCMStatus](#VCMStatus) |  | 当前状态 |




## VCMStatus

Volatility Control Mechanism Infomation


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| trigger_time | [uint64](#uint64) |  | 触发时间 |
| post_time | [uint64](#uint64) |  | 过期时间 |


 <!-- end messages -->

# 枚举类型


<a name="biss.api.v1.trade.OrderListSortType"></a>

## OrderListSortType


| Name | Number | Description |
| ---- | ------ | ----------- |
| TIME | 0 | 委托时间 |
| STATUS | 1 | 订单状态 |
| ORDER_TYPE | 2 | 订单类型 |
| TRADE_SIDE | 3 | 交易方向 |
| ENTRUST_PRICE | 4 | 当前委托按照价格 |
| ENTRUST_QTY | 5 | 委托数量 |
| ENTRUST_AMOUNT | 6 | 委托总额 |
| FILLED_QTY | 7 | 成交数量 |
| FILLED_AMOUNT | 8 | 成交总额 |
| FILL_STATUS | 9 | 成交状态 |



<a name="biss.api.v1.trade.PositionListSortType"></a>

## PositionListSortType


| Name | Number | Description |
| ---- | ------ | ----------- |
| DEFAULT | 0 |  |
| HODING_PRICE | 1 |  |
| CURRENT_PRICE | 2 |  |
| QTY | 3 |  |
| HODING_AMOUNT | 4 |  |
| CURRENT_AMOUNT | 5 |  |
| PROFIT | 6 |  |
| RATIO | 7 |  |


 <!-- end enums -->



