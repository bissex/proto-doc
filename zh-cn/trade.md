# Trade

## Entrust

### HTTP Request

```http
POST /v1/trade/{symbol}/{market}
```

**Path Parameters**

| Parameter              | Description |
| ---------------------- | ----------- |
| `symbol`<br />*string* | 标的        |
| `market`<br />*string* | 市场        |

**Body Parameters**

| Parameter                               | Description |
| --------------------------------------- | ----------- |
| `body`<br />[*EntrustReq*](#EntrustReq) | 委托请求    |

### Response

| Code                                   | Description |
| -------------------------------------- | ----------- |
| 200<br />[*EntrustResp*](#EntrustResp) | 委托应答    |

### Example

**curl request**

```shell
curl -X POST -d '
{
	"type": "OT_LIMIT",
	"side": "TS_BID",
	"price": "6543.21",
	"qty": "0.1234"
}' $BISS_SERVER'/v1/trade/BTC/USDT'
```

**curl response**

```json
{
    "oid": "1"
}
```



## EntrustInfo

### HTTP Request

```http
GET /v1/trade/{symbol}/{market}/{oid}
```

**Path Parameters**

| Parameter              | Description |
| ---------------------- | ----------- |
| `symbol`<br />*string* | 标的        |
| `market`<br />*string* | 市场        |
| `oid`<br />*string*    | 订单id      |

### Response

| Code                                           | Description  |
| ---------------------------------------------- | ------------ |
| 200<br />[*EntrustInfoResp*](#EntrustInfoResp) | 委托信息应答 |

### Example

**curl request**

```shell
curl -X GET $BISS_SERVER'/v1/trade/BTC/USDT/1'
```

**curl response**

```json
{
    "orderInfo": {
        "id": "1",
        "type": "OT_LIMIT",
        "side": "TS_BID",
        "price": "6543.21",
        "qty": "0.1234",
        "amount": "807.432114",
        "status": "OS_OPEN",
        "filled": "0",
        "left": "0.1234",
        "time": "1543980952781",
        "ticker": {
            "symbol": "BTC",
            "market": "USDT"
        },
        "filledAvg": "",
        "fee": "0.000",
        "filledAmount": "0",
        "fillStatus": "OFS_UNFILLED"
    }
}
```



## BatchEntrustInfo

### HTTP Request

```http
GET /v1/trade/{symbol}/{market}/list
```

**Path Parameters**

| Parameter              | Description |
| ---------------------- | ----------- |
| `symbol`<br />*string* | 标的        |
| `market`<br />*string* | 市场        |

**Query Parameters**

| Parameter                  | Description |
| -------------------------- | ----------- |
| `oids`<br />*string* array | 订单id列表  |

### Response

| Code                                                     | Description      |
| -------------------------------------------------------- | ---------------- |
| 200<br />[*BatchEntrustInfoResp*](#BatchEntrustInfoResp) | 批量委托信息应答 |

### Example

**curl request**

```shell
curl -X GET $BISS_SERVER'/v1/trade/BTC/USDT/list?oids=1&oids=2&oids=3'
```

**curl response**

```json
{
    "orderInfos": [
        {
            "id": "1",
            "type": "OT_LIMIT",
            "side": "TS_BID",
            "price": "6543.21",
            "qty": "0.1234",
            "amount": "807.432114",
            "status": "OS_OPEN",
            "filled": "0",
            "left": "0.1234",
            "time": "1543980952781",
            "ticker": {
                "symbol": "BTC",
                "market": "USDT"
            },
            "filledAvg": "",
            "fee": "0.000",
            "filledAmount": "0",
            "fillStatus": "OFS_UNFILLED"
        },
        {
            "id": "2",
            "type": "OT_LIMIT",
            "side": "TS_BID",
            "price": "6543.21",
            "qty": "0.1234",
            "amount": "807.432114",
            "status": "OS_OPEN",
            "filled": "0",
            "left": "0.1234",
            "time": "1543980954916",
            "ticker": {
                "symbol": "BTC",
                "market": "USDT"
            },
            "filledAvg": "",
            "fee": "0.000",
            "filledAmount": "0",
            "fillStatus": "OFS_UNFILLED"
        },
        {
            "id": "3",
            "type": "OT_LIMIT",
            "side": "TS_BID",
            "price": "6543.21",
            "qty": "0.1234",
            "amount": "807.432114",
            "status": "OS_OPEN",
            "filled": "0",
            "left": "0.1234",
            "time": "1543980955767",
            "ticker": {
                "symbol": "BTC",
                "market": "USDT"
            },
            "filledAvg": "",
            "fee": "0.000",
            "filledAmount": "0",
            "fillStatus": "OFS_UNFILLED"
        }
    ]
}
```



## EntrustList

### HTTP Request

```http
GET /v1/trade/{symbol}/{market}
```

**Path Parameters**

| Parameter              | Description |
| ---------------------- | ----------- |
| `symbol`<br />*string* | 标的        |
| `market`<br />*string* | 市场        |

**Query Parameters**

| Parameter                                                  | Description     |
| ---------------------------------------------------------- | --------------- |
| `order_list_type`<br />[*OrderListType*](#OrderListType)   | 订单列表类型    |
| `sort_type`<br />[*OrderListSortType*](#OrderListSortType) | 排序类型        |
| `sort_direction`<br />[*SortDirection*](#SortDirection)    | 排序方向        |
| `page`<br />*string*                                       | 页号（从1开始） |
| `page_size`<br />*string*                                  | 每页大小        |

### Response

| Code                                       | Description  |
| ------------------------------------------ | ------------ |
| 200<br />[*OrderListResp*](#OrderListResp) | 订单列表应答 |

### Example

**curl request**

```shell
curl -X GET $BISS_SERVER'/v1/trade/BTC/USDT?order_list_type=OLT_CURRENT&sort_type=TIME&sort_direction=SD_DESC&page=1&page_size=100'
```

**curl response**

```json
{
    "total": 3,
    "page": 1,
    "hasMore": false,
    "sortDirection": "SD_DESC",
    "sortType": "TIME",
    "orders": [
        {
            "id": "3",
            "type": "OT_LIMIT",
            "side": "TS_BID",
            "price": "6543.21",
            "qty": "0.1234",
            "amount": "807.432114",
            "status": "OS_OPEN",
            "filled": "0",
            "left": "0.1234",
            "time": "1543980955767",
            "ticker": {
                "symbol": "BTC",
                "market": "USDT"
            },
            "filledAvg": "",
            "fee": "0.000",
            "filledAmount": "0",
            "fillStatus": "OFS_UNFILLED"
        },
        {
            "id": "2",
            "type": "OT_LIMIT",
            "side": "TS_BID",
            "price": "6543.21",
            "qty": "0.1234",
            "amount": "807.432114",
            "status": "OS_OPEN",
            "filled": "0",
            "left": "0.1234",
            "time": "1543980954916",
            "ticker": {
                "symbol": "BTC",
                "market": "USDT"
            },
            "filledAvg": "",
            "fee": "0.000",
            "filledAmount": "0",
            "fillStatus": "OFS_UNFILLED"
        },
        {
            "id": "1",
            "type": "OT_LIMIT",
            "side": "TS_BID",
            "price": "6543.21",
            "qty": "0.1234",
            "amount": "807.432114",
            "status": "OS_OPEN",
            "filled": "0",
            "left": "0.1234",
            "time": "1543980952781",
            "ticker": {
                "symbol": "BTC",
                "market": "USDT"
            },
            "filledAvg": "",
            "fee": "0.000",
            "filledAmount": "0",
            "fillStatus": "OFS_UNFILLED"
        }
    ]
}
```



## Cancel

### HTTP Request

```http
DELETE /v1/trade/{symbol}/{market}/{oid}
```

**Path Parameters**

| Parameter              | Description |
| ---------------------- | ----------- |
| `symbol`<br />*string* | 标的        |
| `market`<br />*string* | 市场        |
| `oid`<br />*string*    | 订单id      |

### Response

| Code | Description |
| ---- | ----------- |
| 200  | 撤单应答    |

### Example

**curl request**

```shell
curl -X DELETE $BISS_SERVER'/v1/trade/BTC/USDT/1'
```

**curl response**

```json
{}
```



## CancelAll

### HTTP Request

```http
DELETE /v1/trade/{symbol}/{market}
```

**Path Parameters**

| Parameter              | Description |
| ---------------------- | ----------- |
| `symbol`<br />*string* | 标的        |
| `market`<br />*string* | 市场        |

### Response

| Code | Description  |
| ---- | ------------ |
| 200  | 全部撤单应答 |

### Example

**curl request**

```shell
curl -X DELETE $BISS_SERVER'/v1/trade/BTC/USDT'
```

**curl response**

```json
{}
```
