# Request Authentication

## APPID&APPKEY

**APPID:** 

```
ATxp3JdTFgTk21ODVLDk9ohJZkldokhwg4gfO2/yi8P4huDGo+xCBmooWBuhOdCbsH3JWRPHk/VZzTF1R7Ir4TXDoWjuLSBPB1+7/PnBzqRioNfFkO9kiVjk6UPT9Tn6wQ==
```

**APPKEY:** 

```
yMw/v2o4UhYui0fMgNRHgoOcLB0RJBV8j+/SM9tOHcS+dh/Pm+OGNeOASTFxGjOoOlOxgtsIX3ALredZ+adL6YMKER7B3Qe6sQP8MBkpC+PGTxqHKT7YcEmeYS45tjSZ
```



## URL

Contains `Path` & `Query` Parameters

```http
/api/v1/system/symbol-config
```



## Timestamp

**Milliseconds** since Unix Epoch(Jan 1, 1970 00:00:00 UTC)

```shell
1543253646000
```



## Signature

### Message

`URL` append `Timestamp`

```shell
/api/v1/system/symbol-config&timestamp=1543253646000
```

### HMAC SHA256

use `APPKEY` as key, and convert result to **base64** format

```shell
echo -n "/api/v1/system/symbol-config&timestamp=1543253646000" | \
openssl dgst -sha256 -hmac "yMw/v2o4UhYui0fMgNRHgoOcLB0RJBV8j+/SM9tOHcS+dh/Pm+OGNeOASTFxGjOoOlOxgtsIX3ALredZ+adL6YMKER7B3Qe6sQP8MBkpC+PGTxqHKT7YcEmeYS45tjSZ" -binary | \
openssl base64

x2xpuBleiNAuUeoOjTx50C2UdgC8/jkGg34z5Au3FO8=
```



## HTTP header

| Field                | Value     |
| -------------------- | --------- |
| **x-biss-appid**     | APPID     |
| **x-biss-timestamp** | Timestamp |
| **x-biss-signature** | Signature |
