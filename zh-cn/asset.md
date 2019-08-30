
# Assets

## Assets

### HTTP Request

```http
GET /v1/assets/assets
```

### Response

| Code                                | Description |
| ----------------------------------- | ----------- |
| 200<br />[*AssetsResp*](#AssetsResp) | 资产列表    |

### Example

**curl request**

```shell
curl -X GET $BISS_SERVER'/v1/assets/assets'
```

**curl response**

```json
{
    "btcValue": "10100.00000000",
    "values": [
        {
            "legalCurrency": "CU_USD",
            "legalValue": "40147601.000000000000"
        },
        {
            "legalCurrency": "CU_CNY",
            "legalValue": "279142254.9929000000000000"
        }
    ],
    "assets": [
        {
            "symbol": "BTC",
            "name": "Bitcoin",
            "amount": "10000",
            "available": "10000",
            "frozen": "0",
            "btcValue": "10000"
        },
        {
            "symbol": "ETH",
            "name": "Ethereum",
            "amount": "10000",
            "available": "10000",
            "frozen": "0",
            "btcValue": "10.000"
        },
        {
            "symbol": "EOS",
            "name": "EOS",
            "amount": "10000",
            "available": "10000",
            "frozen": "0",
            "btcValue": "10.000"
        },
        {
            "symbol": "BCH",
            "name": "Bitcoin Cash",
            "amount": "10000",
            "available": "10000",
            "frozen": "0",
            "btcValue": "10.000"
        },
        {
            "symbol": "LTC",
            "name": "Litecoin",
            "amount": "10000",
            "available": "10000",
            "frozen": "0",
            "btcValue": "10.000"
        },
        {
            "symbol": "ETC",
            "name": "Ethereum Classic",
            "amount": "10000",
            "available": "10000",
            "frozen": "0",
            "btcValue": "10.000"
        },
        {
            "symbol": "IOST",
            "name": "IOST",
            "amount": "10000",
            "available": "10000",
            "frozen": "0",
            "btcValue": "10.000"
        },
        {
            "symbol": "TUSD",
            "name": "TrueUSD",
            "amount": "10000",
            "available": "10000",
            "frozen": "0",
            "btcValue": "10.000"
        },
        {
            "symbol": "USDT",
            "name": "Tether",
            "amount": "10000",
            "available": "10000",
            "frozen": "0",
            "btcValue": "10.00000000"
        },
        {
            "symbol": "DICE",
            "name": "DICE",
            "amount": "10000",
            "available": "10000",
            "frozen": "0",
            "btcValue": "10.000"
        },
        {
            "symbol": "TPT",
            "name": "TPT",
            "amount": "10000",
            "available": "10000",
            "frozen": "0",
            "btcValue": "10.000"
        }
    ]
}
```

