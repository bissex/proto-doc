


 <!-- end services -->


# 数据对象



## Decimal




| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| negitive | [bool](#bool) |  |  |
| scale | [int32](#int32) |  |  |
| unscaled | [bytes](#bytes) |  |  |




## Empty






## ExchangeRate

汇率


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| rate | [string](#string) |  |  |
| from | [string](#string) |  |  |
| to | [string](#string) |  |  |




## Fee




| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| mode | [FeeMode](#FeeMode) |  |  |
| value | [string](#string) |  |  |




## PaginationReq

分页请求


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| page | [uint32](#uint32) |  | 页号（从1开始） |
| page_size | [uint32](#uint32) |  | 每页大小 |




## PaginationResp

分页应答


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| page | [uint32](#uint32) |  | 页号（从1开始） |
| page_size | [uint32](#uint32) |  | 每页大小 |
| page_count | [uint32](#uint32) |  | 总页数 |
| item_count | [uint32](#uint32) |  | 总条数 |


 <!-- end messages -->

# 枚举类型


<a name="biss.common.Country"></a>

## Country


| Name | Number | Description |
| ---- | ------ | ----------- |
| CC_NONE | 0 |  |
| CC_CHINA | 1 |  |
| CC_USA | 2 |  |
| CC_RUSSIA | 3 |  |
| CC_UK | 4 |  |



<a name="biss.common.Currency"></a>

## Currency


| Name | Number | Description |
| ---- | ------ | ----------- |
| CU_NONE | 0 |  |
| CU_CNY | 1 |  |
| CU_USD | 2 |  |
| CU_HKD | 3 |  |



<a name="biss.common.FeeMode"></a>

## FeeMode


| Name | Number | Description |
| ---- | ------ | ----------- |
| FM_NONE | 0 |  |
| FM_PROPORTIONAL | 1 |  |
| FM_FIXED | 2 |  |



<a name="biss.common.Lang"></a>

## Lang


| Name | Number | Description |
| ---- | ------ | ----------- |
| LANG_DEFAULT | 0 |  |
| LANG_CHINESE | 1 |  |
| LANG_ENGLISH | 2 |  |



<a name="biss.common.Platform"></a>

## Platform


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

## SortDirection


| Name | Number | Description |
| ---- | ------ | ----------- |
| SD_DEFAULT | 0 |  |
| SD_AESC | 1 |  |
| SD_DESC | 2 |  |



<a name="biss.common.TimeZone"></a>

## TimeZone


| Name | Number | Description |
| ---- | ------ | ----------- |
| TZ_UNKNOWN | 0 |  |



<a name="biss.common.VipLevel"></a>

## VipLevel
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


 <!-- end enums -->



