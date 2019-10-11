# Protocol Documentation
<a name="top"></a>

## Table of Contents

- [proto/common/common.proto](#proto/common/common.proto)
    - [Decimal](#biss.common.Decimal)
    - [Empty](#biss.common.Empty)
    - [ExchangeRate](#biss.common.ExchangeRate)
    - [Fee](#biss.common.Fee)
    - [PaginationReq](#biss.common.PaginationReq)
    - [PaginationResp](#biss.common.PaginationResp)
  
    - [AccountType](#biss.common.AccountType)
    - [Country](#biss.common.Country)
    - [Currency](#biss.common.Currency)
    - [FeeMode](#biss.common.FeeMode)
    - [Lang](#biss.common.Lang)
    - [Platform](#biss.common.Platform)
    - [SortDirection](#biss.common.SortDirection)
    - [TimeZone](#biss.common.TimeZone)
    - [VipLevel](#biss.common.VipLevel)
  
  
  

- [Scalar Value Types](#scalar-value-types)



<a name="proto/common/common.proto"></a>
<p align="right"><a href="#top">Top</a></p>

## proto/common/common.proto



<a name="biss.common.Decimal"></a>

### Decimal



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| negitive | [bool](#bool) |  |  |
| scale | [int32](#int32) |  |  |
| unscaled | [bytes](#bytes) |  |  |






<a name="biss.common.Empty"></a>

### Empty







<a name="biss.common.ExchangeRate"></a>

### ExchangeRate
汇率


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| rate | [string](#string) |  |  |
| from | [string](#string) |  |  |
| to | [string](#string) |  |  |






<a name="biss.common.Fee"></a>

### Fee



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| mode | [FeeMode](#biss.common.FeeMode) |  |  |
| value | [string](#string) |  |  |






<a name="biss.common.PaginationReq"></a>

### PaginationReq
分页请求


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| page | [uint32](#uint32) |  | 页号（从1开始） |
| page_size | [uint32](#uint32) |  | 每页大小 |






<a name="biss.common.PaginationResp"></a>

### PaginationResp
分页应答


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| page | [uint32](#uint32) |  | 页号（从1开始） |
| page_size | [uint32](#uint32) |  | 每页大小 |
| page_count | [uint32](#uint32) |  | 总页数 |
| item_count | [uint32](#uint32) |  | 总条数 |





 


<a name="biss.common.AccountType"></a>

### AccountType
账户类型

| Name | Number | Description |
| ---- | ------ | ----------- |
| AT_PARENT | 0 | 母账户 |
| AT_US_STOCK | 1 | 美股账户 |
| AT_CONTRACT | 2 | 合约账户 |



<a name="biss.common.Country"></a>

### Country


| Name | Number | Description |
| ---- | ------ | ----------- |
| CC_NONE | 0 |  |
| CC_CHINA | 1 |  |
| CC_USA | 2 |  |
| CC_RUSSIA | 3 |  |
| CC_UK | 4 |  |



<a name="biss.common.Currency"></a>

### Currency


| Name | Number | Description |
| ---- | ------ | ----------- |
| CU_NONE | 0 |  |
| CU_CNY | 1 |  |
| CU_USD | 2 |  |
| CU_HKD | 3 |  |



<a name="biss.common.FeeMode"></a>

### FeeMode


| Name | Number | Description |
| ---- | ------ | ----------- |
| FM_NONE | 0 |  |
| FM_PROPORTIONAL | 1 |  |
| FM_FIXED | 2 |  |



<a name="biss.common.Lang"></a>

### Lang


| Name | Number | Description |
| ---- | ------ | ----------- |
| LANG_DEFAULT | 0 |  |
| LANG_CHINESE | 1 |  |
| LANG_ENGLISH | 2 |  |



<a name="biss.common.Platform"></a>

### Platform


| Name | Number | Description |
| ---- | ------ | ----------- |
| PF_UNKNOWN | 0 |  |
| PF_WEB | 1 |  |
| PF_WIN | 2 |  |
| PF_MAC | 3 |  |
| PF_IOS | 4 |  |
| PF_ANDROID | 5 |  |
| PF_API | 6 |  |



<a name="biss.common.SortDirection"></a>

### SortDirection


| Name | Number | Description |
| ---- | ------ | ----------- |
| SD_DEFAULT | 0 |  |
| SD_AESC | 1 |  |
| SD_DESC | 2 |  |



<a name="biss.common.TimeZone"></a>

### TimeZone


| Name | Number | Description |
| ---- | ------ | ----------- |
| TZ_UNKNOWN | 0 |  |



<a name="biss.common.VipLevel"></a>

### VipLevel
会员级别

| Name | Number | Description |
| ---- | ------ | ----------- |
| VL_NONE | 0 | 一般用户 |
| VL_VIP_1 | 1 | VIP |
| VL_VIP_2 | 2 |  |
| VL_VIP_3 | 3 |  |
| VL_VIP_4 | 4 |  |
| VL_VIP_5 | 5 |  |
| VL_VIP_6 | 6 |  |
| VL_VIP_7 | 7 |  |


 

 

 



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

