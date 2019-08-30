



# biss.api.v1.push.PushChannel



## OpenAsync


    
> `GRPC` OpenAsync([OpenAsyncReq](#OpenAsyncReq)) return [PushMessage](#PushMessage) `stream`


 <!-- end with -->

## SubRealTime

============= 订阅行情
订阅实时行情
    
> `GRPC` SubRealTime([RealTimeReq](#RealTimeReq)) return [.biss.common.Empty](#.biss.common.Empty)


 <!-- end with -->

## UnsubRealTime


    
> `GRPC` UnsubRealTime([RealTimeReq](#RealTimeReq)) return [.biss.common.Empty](#.biss.common.Empty)


 <!-- end with -->

## SubTick

逐笔行情
    
> `GRPC` SubTick([SubTickReq](#SubTickReq)) return [.biss.common.Empty](#.biss.common.Empty)


 <!-- end with -->

## UnsubTick


    
> `GRPC` UnsubTick([SubTickReq](#SubTickReq)) return [.biss.common.Empty](#.biss.common.Empty)


 <!-- end with -->

## SubKLine

订阅 K 线行情
    
> `GRPC` SubKLine([KLineReq](#KLineReq)) return [.biss.common.Empty](#.biss.common.Empty)


 <!-- end with -->

## UnsubKLine


    
> `GRPC` UnsubKLine([KLineReq](#KLineReq)) return [.biss.common.Empty](#.biss.common.Empty)


 <!-- end with -->

## SubPosition

订阅盘口
    
> `GRPC` SubPosition([PositionReq](#PositionReq)) return [.biss.common.Empty](#.biss.common.Empty)


 <!-- end with -->

## UnsubPosition


    
> `GRPC` UnsubPosition([PositionReq](#PositionReq)) return [.biss.common.Empty](#.biss.common.Empty)


 <!-- end with -->

 <!-- end methods -->
 <!-- end services -->


# 数据对象



## Hertbeat






## KLineReq




| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| sub_uuid | [string](#string) |  |  |
| ticker | [biss.common.trade.Ticker](#biss.common.trade.Ticker) |  |  |
| peroid | [biss.api.v1.quote.KLinePeroid](#biss.api.v1.quote.KLinePeroid) |  |  |




## OpenAsyncReq




| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| sub_uuid | [string](#string) |  |  |




## PositionReq




| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| sub_uuid | [string](#string) |  |  |
| ticker | [biss.common.trade.Ticker](#biss.common.trade.Ticker) |  |  |
| precision | [string](#string) |  | 盘口合并深度 |




## PushMessage




| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| realtime | [biss.api.v1.quote.RealTimeUpdate](#biss.api.v1.quote.RealTimeUpdate) |  |  |
| tick | [biss.api.v1.quote.TickUpdate](#biss.api.v1.quote.TickUpdate) |  |  |
| kline | [biss.api.v1.quote.KLineUpdate](#biss.api.v1.quote.KLineUpdate) |  |  |
| position | [biss.api.v1.quote.PositionUpdate](#biss.api.v1.quote.PositionUpdate) |  |  |
| hb | [Hertbeat](#Hertbeat) |  |  |




## RealTimeReq




| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| sub_uuid | [string](#string) |  |  |
| tickers | [biss.common.trade.Ticker](#biss.common.trade.Ticker) | repeated | 请求的ticker列表，包含请求单个ticker |




## SubTickReq




| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| sub_uuid | [string](#string) |  |  |
| ticker | [biss.common.trade.Ticker](#biss.common.trade.Ticker) |  |  |
| last | [uint32](#uint32) |  | 最新历史 Tick 数量 |


 <!-- end messages -->

# 枚举类型

 <!-- end enums -->



