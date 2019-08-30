# Quote

## RealTime

### HTTP Request

```http
GET /v1/quote/{symbol}/{market}/realtime
```

**Path Parameters**

| Parameter              | Description |
| ---------------------- | ----------- |
| `symbol`<br />*string* | 标的        |
| `market`<br />*string* | 市场        |

### Response

| Code                                         | Description  |
| -------------------------------------------- | ------------ |
| 200<br />[*RealTimeUpdate*](#RealTimeUpdate) | 实时行情应答 |

### Example

**curl request**

```shell
curl -X GET $BISS_SERVER'/v1/quote/BTC/USDT/realtime'
```

**curl response**

```json
{
    "ticker": {
        "symbol": "BTC",
        "market": "USDT"
    },
    "price": "4600",
    "h24": {
        "open": "4500",
        "close": "4600",
        "volume": "4",
        "change": "100",
        "ratio": "2.2200",
        "high": "4600",
        "low": "4400",
        "amount": "18100",
        "avg": "4525.00"
    },
    "tickTime": "1543477872837",
    "quoteTime": "1543477873070",
    "cirulatingSupply": "17398775.00",
    "maxSupply": "21000000.00"
}
```



## TickHistory

### HTTP Request

```http
GET /v1/quote/{symbol}/{market}/tick-history
```

**Path Parameters**

| Parameter              | Description |
| ---------------------- | ----------- |
| `symbol`<br />*string* | 标的        |
| `market`<br />*string* | 市场        |

**Query Parameters**

| Parameter             | Description                                                  |
| --------------------- | ------------------------------------------------------------ |
| `start`<br />*string* | 从此时间向前获取（取值为1970.1.1UTC距今的毫秒数，0表示当前时间） |
| `count`<br />*string* | 条数                                                         |

### Response

| Code                                           | Description      |
| ---------------------------------------------- | ---------------- |
| 200<br />[*TickHistoryResp*](#TickHistoryResp) | 逐笔历史数据应答 |

### Example

**curl request**

```shell
curl -X GET $BISS_SERVER'/v1/quote/BTC/USDT/tick-history?start=0&count=50'
```

**curl response**

```json
{
    "ticker": {
        "symbol": "BTC",
        "market": "USDT"
    },
    "start": "0",
    "count": 4,
    "ticks": [
        {
            "id": "4",
            "time": "1543477872837",
            "price": "4600",
            "volume": "1",
            "amount": "4600",
            "side": "TS_BID",
            "bidOrderNo": "0",
            "bidOrderQty": "0",
            "askOrderNo": "0",
            "askOrderQty": "0"
        },
        {
            "id": "3",
            "time": "1543477863683",
            "price": "4600",
            "volume": "1",
            "amount": "4600",
            "side": "TS_BID",
            "bidOrderNo": "0",
            "bidOrderQty": "0",
            "askOrderNo": "0",
            "askOrderQty": "0"
        },
        {
            "id": "2",
            "time": "1543477774436",
            "price": "4400",
            "volume": "1",
            "amount": "4400",
            "side": "TS_BID",
            "bidOrderNo": "0",
            "bidOrderQty": "0",
            "askOrderNo": "0",
            "askOrderQty": "0"
        },
        {
            "id": "1",
            "time": "1543477731799",
            "price": "4500",
            "volume": "1",
            "amount": "4500",
            "side": "TS_BID",
            "bidOrderNo": "0",
            "bidOrderQty": "0",
            "askOrderNo": "0",
            "askOrderQty": "0"
        }
    ]
}
```



## Position

### HTTP Request

```http
GET /v1/quote/{symbol}/{market}/position
```

**Path Parameters**

| Parameter              | Description |
| ---------------------- | ----------- |
| `symbol`<br />*string* | 标的        |
| `market`<br />*string* | 市场        |

**Query Parameters**

| Parameter                 | Description  |
| ------------------------- | ------------ |
| `precision`<br />*string* | 盘口合并深度 |

### Response

| Code                                         | Description |
| -------------------------------------------- | ----------- |
| 200<br />[*PositionUpdate*](#PositionUpdate) | 盘口应答    |

### Example

**curl request**

```shell
curl -X GET $BISS_SERVER'/v1/quote/BTC/USDT/position?precision=0.01'
```

**curl response**

```json
{
    "ticker": {
        "symbol": "BTC",
        "market": "USDT"
    },
    "precision": "0.01",
    "items": [
        {
            "mode": "UM_OVERRIDE",
            "bids": [
                {
                    "level": 1,
                    "price": "4999.00",
                    "volume": "0.01",
                    "amount": "49.99",
                    "orderQty": []
                },
                {
                    "level": 2,
                    "price": "4998.00",
                    "volume": "0.02",
                    "amount": "99.96",
                    "orderQty": []
                },
                {
                    "level": 3,
                    "price": "4997.00",
                    "volume": "0.03",
                    "amount": "149.91",
                    "orderQty": []
                },
                {
                    "level": 4,
                    "price": "4996.00",
                    "volume": "0.04",
                    "amount": "199.84",
                    "orderQty": []
                },
                {
                    "level": 5,
                    "price": "4995.00",
                    "volume": "0.05",
                    "amount": "249.75",
                    "orderQty": []
                }
            ],
            "asks": [
                {
                    "level": 1,
                    "price": "5001.00",
                    "volume": "0.01",
                    "amount": "50.01",
                    "orderQty": []
                },
                {
                    "level": 2,
                    "price": "5002.00",
                    "volume": "0.02",
                    "amount": "100.04",
                    "orderQty": []
                },
                {
                    "level": 3,
                    "price": "5003.00",
                    "volume": "0.03",
                    "amount": "150.09",
                    "orderQty": []
                },
                {
                    "level": 4,
                    "price": "5004.00",
                    "volume": "0.04",
                    "amount": "200.16",
                    "orderQty": []
                },
                {
                    "level": 5,
                    "price": "5005.00",
                    "volume": "0.05",
                    "amount": "250.25",
                    "orderQty": []
                }
            ]
        }
    ]
}
```
