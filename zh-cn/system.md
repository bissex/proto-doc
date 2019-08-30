## SymbolConfig

### HTTP Request

```http
GET /v1/system/symbol-config
```

### Response

| Code                                 | Description |
| ------------------------------------ | ----------- |
| 200<br />[*SymbolList*](#SymbolList) | 标的列表    |

### Example

**curl request**

```shell
curl -X GET $BISS_SERVER'/v1/system/symbol-config'
```

**curl response**

```json
{
    "symbols": [
        {
            "symbol": "BTC",
            "priority": 500,
            "minWithdrawQty": "0.002",
            "minDepositQty": "0.001",
            "withdrawQuota": "5",
            "confirmBlocks": 6,
            "withdrawBlocks": 6,
            "withdrawFee": {
                "mode": "FM_FIXED",
                "value": "0.001"
            }
        },
        {
            "symbol": "BCH",
            "priority": 500,
            "minWithdrawQty": "0.01",
            "minDepositQty": "0.001",
            "withdrawQuota": "5",
            "confirmBlocks": 6,
            "withdrawBlocks": 6,
            "withdrawFee": {
                "mode": "FM_FIXED",
                "value": "0.001"
            }
        },
        {
            "symbol": "ETH",
            "priority": 500,
            "minWithdrawQty": "0.2",
            "minDepositQty": "0.01",
            "withdrawQuota": "5",
            "confirmBlocks": 30,
            "withdrawBlocks": 30,
            "withdrawFee": {
                "mode": "FM_FIXED",
                "value": "0.01"
            }
        },
        {
            "symbol": "ETC",
            "priority": 500,
            "minWithdrawQty": "0.5",
            "minDepositQty": "0.01",
            "withdrawQuota": "5",
            "confirmBlocks": 120,
            "withdrawBlocks": 120,
            "withdrawFee": {
                "mode": "FM_FIXED",
                "value": "0.01"
            }
        },
        {
            "symbol": "LTC",
            "priority": 500,
            "minWithdrawQty": "0.1",
            "minDepositQty": "0.001",
            "withdrawQuota": "5",
            "confirmBlocks": 6,
            "withdrawBlocks": 6,
            "withdrawFee": {
                "mode": "FM_FIXED",
                "value": "0.001"
            }
        },
        {
            "symbol": "EOS",
            "priority": 500,
            "minWithdrawQty": "100",
            "minDepositQty": "0.1",
            "withdrawQuota": "5",
            "confirmBlocks": 1,
            "withdrawBlocks": 1,
            "withdrawFee": {
                "mode": "FM_FIXED",
                "value": "0.1"
            }
        },
        {
            "symbol": "IOST",
            "priority": 500,
            "minWithdrawQty": "500",
            "minDepositQty": "100",
            "withdrawQuota": "5",
            "confirmBlocks": 30,
            "withdrawBlocks": 30,
            "withdrawFee": {
                "mode": "FM_FIXED",
                "value": "100"
            }
        },
        {
            "symbol": "USDT",
            "priority": 500,
            "minWithdrawQty": "100",
            "minDepositQty": "100",
            "withdrawQuota": "5",
            "confirmBlocks": 6,
            "withdrawBlocks": 6,
            "withdrawFee": {
                "mode": "FM_FIXED",
                "value": "5"
            }
        },
        {
            "symbol": "TUSD",
            "priority": 500,
            "minWithdrawQty": "100",
            "minDepositQty": "100",
            "withdrawQuota": "5",
            "confirmBlocks": 30,
            "withdrawBlocks": 30,
            "withdrawFee": {
                "mode": "FM_FIXED",
                "value": "5"
            }
        },
        {
            "symbol": "DICE",
            "priority": 500,
            "minWithdrawQty": "500",
            "minDepositQty": "500",
            "withdrawQuota": "5",
            "confirmBlocks": 1,
            "withdrawBlocks": 1,
            "withdrawFee": {
                "mode": "FM_FIXED",
                "value": "100"
            }
        },
        {
            "symbol": "TPT",
            "priority": 500,
            "minWithdrawQty": "500",
            "minDepositQty": "500",
            "withdrawQuota": "5",
            "confirmBlocks": 1,
            "withdrawBlocks": 1,
            "withdrawFee": {
                "mode": "FM_FIXED",
                "value": "100"
            }
        }
    ]
}
```



## MarketConfig

### HTTP Request

```http
GET /v1/system/market-config
```

### Response

| Code                                 | Description |
| ------------------------------------ | ----------- |
| 200<br />[*MarketList*](#MarketList) | 市场列表    |

### Example

**curl request**

```shell
curl -X GET $BISS_SERVER'/v1/system/market-config'
```

**curl response**

```json
{
    "markets": [
        {
            "market": "BTC",
            "priority": 500,
            "minMarketBuyAmount": "0.001"
        },
        {
            "market": "ETH",
            "priority": 500,
            "minMarketBuyAmount": "0.01"
        },
        {
            "market": "USDT",
            "priority": 500,
            "minMarketBuyAmount": "10"
        },
        {
            "market": "EOS",
            "priority": 500,
            "minMarketBuyAmount": "2"
        }
    ]
}
```



## TickerConfig

### HTTP Request

```http
GET /v1/system/ticker-config
```

### Response

| Code                                 | Description |
| ------------------------------------ | ----------- |
| 200<br />[*TickerList*](#TickerList) | 交易对列表  |

### Example

**curl request**

```shell
curl -X GET $BISS_SERVER'/v1/system/ticker-config'
```

**curl response**

```json
{
    "tickers": [
        {
            "symbol": "DICE",
            "market": "EOS",
            "priority": 1000,
            "showInHome": false,
            "minTradePrice": "0.000001",
            "minTradeQty": "1",
            "takerFee": {
                "mode": "FM_PROPORTIONAL",
                "value": "0.001"
            },
            "makerFee": {
                "mode": "FM_PROPORTIONAL",
                "value": "0.001"
            },
            "depthGroups": [
                "0.0001",
                "0.00001",
                "0.000001"
            ]
        },
        {
            "symbol": "BCH",
            "market": "ETH",
            "priority": 999,
            "showInHome": false,
            "minTradePrice": "0.00001",
            "minTradeQty": "0.01",
            "takerFee": {
                "mode": "FM_PROPORTIONAL",
                "value": "0.001"
            },
            "makerFee": {
                "mode": "FM_PROPORTIONAL",
                "value": "0.001"
            },
            "depthGroups": [
                "0.001",
                "0.0001",
                "0.00001"
            ]
        },
        {
            "symbol": "TPT",
            "market": "EOS",
            "priority": 999,
            "showInHome": false,
            "minTradePrice": "0.000001",
            "minTradeQty": "1",
            "takerFee": {
                "mode": "FM_PROPORTIONAL",
                "value": "0.001"
            },
            "makerFee": {
                "mode": "FM_PROPORTIONAL",
                "value": "0.001"
            },
            "depthGroups": [
                "0.0001",
                "0.00001",
                "0.000001"
            ]
        },
        {
            "symbol": "BCH",
            "market": "BTC",
            "priority": 999,
            "showInHome": false,
            "minTradePrice": "0.000001",
            "minTradeQty": "0.01",
            "takerFee": {
                "mode": "FM_PROPORTIONAL",
                "value": "0.001"
            },
            "makerFee": {
                "mode": "FM_PROPORTIONAL",
                "value": "0.001"
            },
            "depthGroups": [
                "0.0001",
                "0.00001",
                "0.000001"
            ]
        },
        {
            "symbol": "BTC",
            "market": "USDT",
            "priority": 999,
            "showInHome": false,
            "minTradePrice": "0.01",
            "minTradeQty": "0.0001",
            "takerFee": {
                "mode": "FM_PROPORTIONAL",
                "value": "0.001"
            },
            "makerFee": {
                "mode": "FM_PROPORTIONAL",
                "value": "0.001"
            },
            "depthGroups": [
                "1",
                "0.1",
                "0.01"
            ]
        },
        {
            "symbol": "ETH",
            "market": "BTC",
            "priority": 998,
            "showInHome": false,
            "minTradePrice": "0.000001",
            "minTradeQty": "0.01",
            "takerFee": {
                "mode": "FM_PROPORTIONAL",
                "value": "0.001"
            },
            "makerFee": {
                "mode": "FM_PROPORTIONAL",
                "value": "0.001"
            },
            "depthGroups": [
                "0.0001",
                "0.00001",
                "0.000001"
            ]
        },
        {
            "symbol": "BCH",
            "market": "USDT",
            "priority": 998,
            "showInHome": false,
            "minTradePrice": "0.01",
            "minTradeQty": "0.001",
            "takerFee": {
                "mode": "FM_PROPORTIONAL",
                "value": "0.001"
            },
            "makerFee": {
                "mode": "FM_PROPORTIONAL",
                "value": "0.001"
            },
            "depthGroups": [
                "1",
                "0.1",
                "0.01"
            ]
        },
        {
            "symbol": "ETC",
            "market": "ETH",
            "priority": 997,
            "showInHome": false,
            "minTradePrice": "0.00001",
            "minTradeQty": "0.1",
            "takerFee": {
                "mode": "FM_PROPORTIONAL",
                "value": "0.001"
            },
            "makerFee": {
                "mode": "FM_PROPORTIONAL",
                "value": "0.001"
            },
            "depthGroups": [
                "0.001",
                "0.0001",
                "0.00001"
            ]
        },
        {
            "symbol": "ETC",
            "market": "BTC",
            "priority": 997,
            "showInHome": false,
            "minTradePrice": "0.000001",
            "minTradeQty": "0.1",
            "takerFee": {
                "mode": "FM_PROPORTIONAL",
                "value": "0.001"
            },
            "makerFee": {
                "mode": "FM_PROPORTIONAL",
                "value": "0.001"
            },
            "depthGroups": [
                "0.00001",
                "0.000001",
                "0.0000001"
            ]
        },
        {
            "symbol": "ETH",
            "market": "USDT",
            "priority": 997,
            "showInHome": false,
            "minTradePrice": "0.01",
            "minTradeQty": "0.001",
            "takerFee": {
                "mode": "FM_PROPORTIONAL",
                "value": "0.001"
            },
            "makerFee": {
                "mode": "FM_PROPORTIONAL",
                "value": "0.001"
            },
            "depthGroups": [
                "1",
                "0.1",
                "0.01"
            ]
        },
        {
            "symbol": "ETC",
            "market": "USDT",
            "priority": 996,
            "showInHome": false,
            "minTradePrice": "0.0001",
            "minTradeQty": "0.01",
            "takerFee": {
                "mode": "FM_PROPORTIONAL",
                "value": "0.001"
            },
            "makerFee": {
                "mode": "FM_PROPORTIONAL",
                "value": "0.001"
            },
            "depthGroups": [
                "0.01",
                "0.001",
                "0.0001"
            ]
        },
        {
            "symbol": "LTC",
            "market": "ETH",
            "priority": 996,
            "showInHome": false,
            "minTradePrice": "0.000001",
            "minTradeQty": "0.01",
            "takerFee": {
                "mode": "FM_PROPORTIONAL",
                "value": "0.001"
            },
            "makerFee": {
                "mode": "FM_PROPORTIONAL",
                "value": "0.001"
            },
            "depthGroups": [
                "0.0001",
                "0.00001",
                "0.000001"
            ]
        },
        {
            "symbol": "LTC",
            "market": "BTC",
            "priority": 996,
            "showInHome": false,
            "minTradePrice": "0.000001",
            "minTradeQty": "0.01",
            "takerFee": {
                "mode": "FM_PROPORTIONAL",
                "value": "0.001"
            },
            "makerFee": {
                "mode": "FM_PROPORTIONAL",
                "value": "0.001"
            },
            "depthGroups": [
                "0.0001",
                "0.00001",
                "0.000001"
            ]
        },
        {
            "symbol": "EOS",
            "market": "ETH",
            "priority": 995,
            "showInHome": false,
            "minTradePrice": "0.000001",
            "minTradeQty": "0.1",
            "takerFee": {
                "mode": "FM_PROPORTIONAL",
                "value": "0.001"
            },
            "makerFee": {
                "mode": "FM_PROPORTIONAL",
                "value": "0.001"
            },
            "depthGroups": [
                "0.0001",
                "0.00001",
                "0.000001"
            ]
        },
        {
            "symbol": "EOS",
            "market": "BTC",
            "priority": 995,
            "showInHome": false,
            "minTradePrice": "0.00000001",
            "minTradeQty": "0.1",
            "takerFee": {
                "mode": "FM_PROPORTIONAL",
                "value": "0.001"
            },
            "makerFee": {
                "mode": "FM_PROPORTIONAL",
                "value": "0.001"
            },
            "depthGroups": [
                "0.00001",
                "0.000001",
                "0.0000001"
            ]
        },
        {
            "symbol": "LTC",
            "market": "USDT",
            "priority": 995,
            "showInHome": false,
            "minTradePrice": "0.01",
            "minTradeQty": "0.001",
            "takerFee": {
                "mode": "FM_PROPORTIONAL",
                "value": "0.001"
            },
            "makerFee": {
                "mode": "FM_PROPORTIONAL",
                "value": "0.001"
            },
            "depthGroups": [
                "1",
                "0.1",
                "0.01"
            ]
        },
        {
            "symbol": "EOS",
            "market": "USDT",
            "priority": 994,
            "showInHome": false,
            "minTradePrice": "0.0001",
            "minTradeQty": "0.01",
            "takerFee": {
                "mode": "FM_PROPORTIONAL",
                "value": "0.001"
            },
            "makerFee": {
                "mode": "FM_PROPORTIONAL",
                "value": "0.001"
            },
            "depthGroups": [
                "0.01",
                "0.001",
                "0.0001"
            ]
        },
        {
            "symbol": "IOST",
            "market": "USDT",
            "priority": 993,
            "showInHome": false,
            "minTradePrice": "0.000001",
            "minTradeQty": "0.1",
            "takerFee": {
                "mode": "FM_PROPORTIONAL",
                "value": "0.001"
            },
            "makerFee": {
                "mode": "FM_PROPORTIONAL",
                "value": "0.001"
            },
            "depthGroups": [
                "0.0001",
                "0.00001",
                "0.000001"
            ]
        },
        {
            "symbol": "IOST",
            "market": "ETH",
            "priority": 993,
            "showInHome": false,
            "minTradePrice": "0.00000001",
            "minTradeQty": "1",
            "takerFee": {
                "mode": "FM_PROPORTIONAL",
                "value": "0.001"
            },
            "makerFee": {
                "mode": "FM_PROPORTIONAL",
                "value": "0.001"
            },
            "depthGroups": [
                "0.000001",
                "0.0000001",
                "0.00000001"
            ]
        },
        {
            "symbol": "IOST",
            "market": "BTC",
            "priority": 993,
            "showInHome": false,
            "minTradePrice": "0.0000000001",
            "minTradeQty": "1",
            "takerFee": {
                "mode": "FM_PROPORTIONAL",
                "value": "0.001"
            },
            "makerFee": {
                "mode": "FM_PROPORTIONAL",
                "value": "0.001"
            },
            "depthGroups": [
                "0.000001",
                "0.0000001",
                "0.00000001"
            ]
        },
        {
            "symbol": "TUSD",
            "market": "USDT",
            "priority": 992,
            "showInHome": false,
            "minTradePrice": "0.0001",
            "minTradeQty": "0.1",
            "takerFee": {
                "mode": "FM_PROPORTIONAL",
                "value": "0.001"
            },
            "makerFee": {
                "mode": "FM_PROPORTIONAL",
                "value": "0.001"
            },
            "depthGroups": [
                "0.01",
                "0.001",
                "0.0001"
            ]
        }
    ]
}
```



## SystemConfig

### HTTP Request

```http
GET /v1/system/system-config
```

### Response

| Code                                 | Description |
| ------------------------------------ | ----------- |
| 200<br />[*SystemResp*](#SystemResp) | 系统配置    |

### Example

**curl request**

```shell
curl -X GET $BISS_SERVER'/v1/system/system-config'
```

**curl response**

```json
{
    "symbols": [
        {
            "symbol": "BTC",
            "priority": 500,
            "minWithdrawQty": "0.002",
            "minDepositQty": "0.001",
            "withdrawQuota": "5",
            "confirmBlocks": 6,
            "withdrawBlocks": 6,
            "withdrawFee": {
                "mode": "FM_FIXED",
                "value": "0.001"
            }
        },
        {
            "symbol": "BCH",
            "priority": 500,
            "minWithdrawQty": "0.01",
            "minDepositQty": "0.001",
            "withdrawQuota": "5",
            "confirmBlocks": 6,
            "withdrawBlocks": 6,
            "withdrawFee": {
                "mode": "FM_FIXED",
                "value": "0.001"
            }
        },
        {
            "symbol": "ETH",
            "priority": 500,
            "minWithdrawQty": "0.2",
            "minDepositQty": "0.01",
            "withdrawQuota": "5",
            "confirmBlocks": 30,
            "withdrawBlocks": 30,
            "withdrawFee": {
                "mode": "FM_FIXED",
                "value": "0.01"
            }
        },
        {
            "symbol": "ETC",
            "priority": 500,
            "minWithdrawQty": "0.5",
            "minDepositQty": "0.01",
            "withdrawQuota": "5",
            "confirmBlocks": 120,
            "withdrawBlocks": 120,
            "withdrawFee": {
                "mode": "FM_FIXED",
                "value": "0.01"
            }
        },
        {
            "symbol": "LTC",
            "priority": 500,
            "minWithdrawQty": "0.1",
            "minDepositQty": "0.001",
            "withdrawQuota": "5",
            "confirmBlocks": 6,
            "withdrawBlocks": 6,
            "withdrawFee": {
                "mode": "FM_FIXED",
                "value": "0.001"
            }
        },
        {
            "symbol": "EOS",
            "priority": 500,
            "minWithdrawQty": "100",
            "minDepositQty": "0.1",
            "withdrawQuota": "5",
            "confirmBlocks": 1,
            "withdrawBlocks": 1,
            "withdrawFee": {
                "mode": "FM_FIXED",
                "value": "0.1"
            }
        },
        {
            "symbol": "IOST",
            "priority": 500,
            "minWithdrawQty": "500",
            "minDepositQty": "100",
            "withdrawQuota": "5",
            "confirmBlocks": 30,
            "withdrawBlocks": 30,
            "withdrawFee": {
                "mode": "FM_FIXED",
                "value": "100"
            }
        },
        {
            "symbol": "USDT",
            "priority": 500,
            "minWithdrawQty": "100",
            "minDepositQty": "100",
            "withdrawQuota": "5",
            "confirmBlocks": 6,
            "withdrawBlocks": 6,
            "withdrawFee": {
                "mode": "FM_FIXED",
                "value": "5"
            }
        },
        {
            "symbol": "TUSD",
            "priority": 500,
            "minWithdrawQty": "100",
            "minDepositQty": "100",
            "withdrawQuota": "5",
            "confirmBlocks": 30,
            "withdrawBlocks": 30,
            "withdrawFee": {
                "mode": "FM_FIXED",
                "value": "5"
            }
        },
        {
            "symbol": "DICE",
            "priority": 500,
            "minWithdrawQty": "500",
            "minDepositQty": "500",
            "withdrawQuota": "5",
            "confirmBlocks": 1,
            "withdrawBlocks": 1,
            "withdrawFee": {
                "mode": "FM_FIXED",
                "value": "100"
            }
        },
        {
            "symbol": "TPT",
            "priority": 500,
            "minWithdrawQty": "500",
            "minDepositQty": "500",
            "withdrawQuota": "5",
            "confirmBlocks": 1,
            "withdrawBlocks": 1,
            "withdrawFee": {
                "mode": "FM_FIXED",
                "value": "100"
            }
        }
    ],
    "tickers": [
        {
            "symbol": "DICE",
            "market": "EOS",
            "priority": 1000,
            "showInHome": false,
            "minTradePrice": "0.000001",
            "minTradeQty": "1",
            "takerFee": {
                "mode": "FM_PROPORTIONAL",
                "value": "0.001"
            },
            "makerFee": {
                "mode": "FM_PROPORTIONAL",
                "value": "0.001"
            },
            "depthGroups": [
                "0.0001",
                "0.00001",
                "0.000001"
            ]
        },
        {
            "symbol": "BCH",
            "market": "ETH",
            "priority": 999,
            "showInHome": false,
            "minTradePrice": "0.00001",
            "minTradeQty": "0.01",
            "takerFee": {
                "mode": "FM_PROPORTIONAL",
                "value": "0.001"
            },
            "makerFee": {
                "mode": "FM_PROPORTIONAL",
                "value": "0.001"
            },
            "depthGroups": [
                "0.001",
                "0.0001",
                "0.00001"
            ]
        },
        {
            "symbol": "TPT",
            "market": "EOS",
            "priority": 999,
            "showInHome": false,
            "minTradePrice": "0.000001",
            "minTradeQty": "1",
            "takerFee": {
                "mode": "FM_PROPORTIONAL",
                "value": "0.001"
            },
            "makerFee": {
                "mode": "FM_PROPORTIONAL",
                "value": "0.001"
            },
            "depthGroups": [
                "0.0001",
                "0.00001",
                "0.000001"
            ]
        },
        {
            "symbol": "BCH",
            "market": "BTC",
            "priority": 999,
            "showInHome": false,
            "minTradePrice": "0.000001",
            "minTradeQty": "0.01",
            "takerFee": {
                "mode": "FM_PROPORTIONAL",
                "value": "0.001"
            },
            "makerFee": {
                "mode": "FM_PROPORTIONAL",
                "value": "0.001"
            },
            "depthGroups": [
                "0.0001",
                "0.00001",
                "0.000001"
            ]
        },
        {
            "symbol": "BTC",
            "market": "USDT",
            "priority": 999,
            "showInHome": false,
            "minTradePrice": "0.01",
            "minTradeQty": "0.0001",
            "takerFee": {
                "mode": "FM_PROPORTIONAL",
                "value": "0.001"
            },
            "makerFee": {
                "mode": "FM_PROPORTIONAL",
                "value": "0.001"
            },
            "depthGroups": [
                "1",
                "0.1",
                "0.01"
            ]
        },
        {
            "symbol": "ETH",
            "market": "BTC",
            "priority": 998,
            "showInHome": false,
            "minTradePrice": "0.000001",
            "minTradeQty": "0.01",
            "takerFee": {
                "mode": "FM_PROPORTIONAL",
                "value": "0.001"
            },
            "makerFee": {
                "mode": "FM_PROPORTIONAL",
                "value": "0.001"
            },
            "depthGroups": [
                "0.0001",
                "0.00001",
                "0.000001"
            ]
        },
        {
            "symbol": "BCH",
            "market": "USDT",
            "priority": 998,
            "showInHome": false,
            "minTradePrice": "0.01",
            "minTradeQty": "0.001",
            "takerFee": {
                "mode": "FM_PROPORTIONAL",
                "value": "0.001"
            },
            "makerFee": {
                "mode": "FM_PROPORTIONAL",
                "value": "0.001"
            },
            "depthGroups": [
                "1",
                "0.1",
                "0.01"
            ]
        },
        {
            "symbol": "ETC",
            "market": "ETH",
            "priority": 997,
            "showInHome": false,
            "minTradePrice": "0.00001",
            "minTradeQty": "0.1",
            "takerFee": {
                "mode": "FM_PROPORTIONAL",
                "value": "0.001"
            },
            "makerFee": {
                "mode": "FM_PROPORTIONAL",
                "value": "0.001"
            },
            "depthGroups": [
                "0.001",
                "0.0001",
                "0.00001"
            ]
        },
        {
            "symbol": "ETC",
            "market": "BTC",
            "priority": 997,
            "showInHome": false,
            "minTradePrice": "0.000001",
            "minTradeQty": "0.1",
            "takerFee": {
                "mode": "FM_PROPORTIONAL",
                "value": "0.001"
            },
            "makerFee": {
                "mode": "FM_PROPORTIONAL",
                "value": "0.001"
            },
            "depthGroups": [
                "0.00001",
                "0.000001",
                "0.0000001"
            ]
        },
        {
            "symbol": "ETH",
            "market": "USDT",
            "priority": 997,
            "showInHome": false,
            "minTradePrice": "0.01",
            "minTradeQty": "0.001",
            "takerFee": {
                "mode": "FM_PROPORTIONAL",
                "value": "0.001"
            },
            "makerFee": {
                "mode": "FM_PROPORTIONAL",
                "value": "0.001"
            },
            "depthGroups": [
                "1",
                "0.1",
                "0.01"
            ]
        },
        {
            "symbol": "ETC",
            "market": "USDT",
            "priority": 996,
            "showInHome": false,
            "minTradePrice": "0.0001",
            "minTradeQty": "0.01",
            "takerFee": {
                "mode": "FM_PROPORTIONAL",
                "value": "0.001"
            },
            "makerFee": {
                "mode": "FM_PROPORTIONAL",
                "value": "0.001"
            },
            "depthGroups": [
                "0.01",
                "0.001",
                "0.0001"
            ]
        },
        {
            "symbol": "LTC",
            "market": "ETH",
            "priority": 996,
            "showInHome": false,
            "minTradePrice": "0.000001",
            "minTradeQty": "0.01",
            "takerFee": {
                "mode": "FM_PROPORTIONAL",
                "value": "0.001"
            },
            "makerFee": {
                "mode": "FM_PROPORTIONAL",
                "value": "0.001"
            },
            "depthGroups": [
                "0.0001",
                "0.00001",
                "0.000001"
            ]
        },
        {
            "symbol": "LTC",
            "market": "BTC",
            "priority": 996,
            "showInHome": false,
            "minTradePrice": "0.000001",
            "minTradeQty": "0.01",
            "takerFee": {
                "mode": "FM_PROPORTIONAL",
                "value": "0.001"
            },
            "makerFee": {
                "mode": "FM_PROPORTIONAL",
                "value": "0.001"
            },
            "depthGroups": [
                "0.0001",
                "0.00001",
                "0.000001"
            ]
        },
        {
            "symbol": "EOS",
            "market": "ETH",
            "priority": 995,
            "showInHome": false,
            "minTradePrice": "0.000001",
            "minTradeQty": "0.1",
            "takerFee": {
                "mode": "FM_PROPORTIONAL",
                "value": "0.001"
            },
            "makerFee": {
                "mode": "FM_PROPORTIONAL",
                "value": "0.001"
            },
            "depthGroups": [
                "0.0001",
                "0.00001",
                "0.000001"
            ]
        },
        {
            "symbol": "EOS",
            "market": "BTC",
            "priority": 995,
            "showInHome": false,
            "minTradePrice": "0.00000001",
            "minTradeQty": "0.1",
            "takerFee": {
                "mode": "FM_PROPORTIONAL",
                "value": "0.001"
            },
            "makerFee": {
                "mode": "FM_PROPORTIONAL",
                "value": "0.001"
            },
            "depthGroups": [
                "0.00001",
                "0.000001",
                "0.0000001"
            ]
        },
        {
            "symbol": "LTC",
            "market": "USDT",
            "priority": 995,
            "showInHome": false,
            "minTradePrice": "0.01",
            "minTradeQty": "0.001",
            "takerFee": {
                "mode": "FM_PROPORTIONAL",
                "value": "0.001"
            },
            "makerFee": {
                "mode": "FM_PROPORTIONAL",
                "value": "0.001"
            },
            "depthGroups": [
                "1",
                "0.1",
                "0.01"
            ]
        },
        {
            "symbol": "EOS",
            "market": "USDT",
            "priority": 994,
            "showInHome": false,
            "minTradePrice": "0.0001",
            "minTradeQty": "0.01",
            "takerFee": {
                "mode": "FM_PROPORTIONAL",
                "value": "0.001"
            },
            "makerFee": {
                "mode": "FM_PROPORTIONAL",
                "value": "0.001"
            },
            "depthGroups": [
                "0.01",
                "0.001",
                "0.0001"
            ]
        },
        {
            "symbol": "IOST",
            "market": "USDT",
            "priority": 993,
            "showInHome": false,
            "minTradePrice": "0.000001",
            "minTradeQty": "0.1",
            "takerFee": {
                "mode": "FM_PROPORTIONAL",
                "value": "0.001"
            },
            "makerFee": {
                "mode": "FM_PROPORTIONAL",
                "value": "0.001"
            },
            "depthGroups": [
                "0.0001",
                "0.00001",
                "0.000001"
            ]
        },
        {
            "symbol": "IOST",
            "market": "ETH",
            "priority": 993,
            "showInHome": false,
            "minTradePrice": "0.00000001",
            "minTradeQty": "1",
            "takerFee": {
                "mode": "FM_PROPORTIONAL",
                "value": "0.001"
            },
            "makerFee": {
                "mode": "FM_PROPORTIONAL",
                "value": "0.001"
            },
            "depthGroups": [
                "0.000001",
                "0.0000001",
                "0.00000001"
            ]
        },
        {
            "symbol": "IOST",
            "market": "BTC",
            "priority": 993,
            "showInHome": false,
            "minTradePrice": "0.0000000001",
            "minTradeQty": "1",
            "takerFee": {
                "mode": "FM_PROPORTIONAL",
                "value": "0.001"
            },
            "makerFee": {
                "mode": "FM_PROPORTIONAL",
                "value": "0.001"
            },
            "depthGroups": [
                "0.000001",
                "0.0000001",
                "0.00000001"
            ]
        },
        {
            "symbol": "TUSD",
            "market": "USDT",
            "priority": 992,
            "showInHome": false,
            "minTradePrice": "0.0001",
            "minTradeQty": "0.1",
            "takerFee": {
                "mode": "FM_PROPORTIONAL",
                "value": "0.001"
            },
            "makerFee": {
                "mode": "FM_PROPORTIONAL",
                "value": "0.001"
            },
            "depthGroups": [
                "0.01",
                "0.001",
                "0.0001"
            ]
        }
    ],
    "markets": [
        {
            "market": "BTC",
            "priority": 500,
            "minMarketBuyAmount": "0.001"
        },
        {
            "market": "ETH",
            "priority": 500,
            "minMarketBuyAmount": "0.01"
        },
        {
            "market": "USDT",
            "priority": 500,
            "minMarketBuyAmount": "10"
        },
        {
            "market": "EOS",
            "priority": 500,
            "minMarketBuyAmount": "2"
        }
    ]
}
```
