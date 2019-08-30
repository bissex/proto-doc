



# biss.api.v1.account.Account



## Register

===================================================
注册
    
> `GRPC` Register([RegisterReq](#RegisterReq)) return [.biss.common.Empty](#.biss.common.Empty)


 <!-- end with -->

## Challenge

登陆 Challenge
    
> `GRPC` Challenge([.biss.common.Empty](#.biss.common.Empty)) return [ChallengeResp](#ChallengeResp)


 <!-- end with -->

## Login

登陆
    
> `GRPC` Login([LoginReq](#LoginReq)) return [LoginResp](#LoginResp)


 <!-- end with -->

## Logout

登出
    
> `GRPC` Logout([.biss.common.Empty](#.biss.common.Empty)) return [.biss.common.Empty](#.biss.common.Empty)


 <!-- end with -->

## ModifyPassword

====================================================
修改密码
    
> `GRPC` ModifyPassword([ModifyPasswordReq](#ModifyPasswordReq)) return [ModifyPasswordResp](#ModifyPasswordResp)


 <!-- end with -->

## ResetPassword

重置密码
    
> `GRPC` ResetPassword([ResetPasswordReq](#ResetPasswordReq)) return [ResetPasswordResp](#ResetPasswordResp)


 <!-- end with -->

## BindMobile

=====================================================
绑定手机
    
> `GRPC` BindMobile([BindMobileReq](#BindMobileReq)) return [.biss.common.Empty](#.biss.common.Empty)


 <!-- end with -->

## BindGA

绑定 Google 2-Step Auth
    
> `GRPC` BindGA([BindGAReq](#BindGAReq)) return [.biss.common.Empty](#.biss.common.Empty)


 <!-- end with -->

## KYCUpload

KYC 文件上传请求
    
> `GRPC` KYCUpload([KYCUploadReq](#KYCUploadReq)) return [KYCUploadResp](#KYCUploadResp)


 <!-- end with -->

## KYCAudit

KYC 审核请求
    
> `GRPC` KYCAudit([KYCAuditReq](#KYCAuditReq)) return [.biss.common.Empty](#.biss.common.Empty)


 <!-- end with -->

## KYCStatus

KYC 审核状态请求
    
> `GRPC` KYCStatus([.biss.common.Empty](#.biss.common.Empty)) return [KYCStatusResp](#KYCStatusResp)


 <!-- end with -->

## FeeBissDeduction

手续费BISS抵扣
    
> `GRPC` FeeBissDeduction([FeeBissDeductionReq](#FeeBissDeductionReq)) return [.biss.common.Empty](#.biss.common.Empty)






> `HTTP` `POST` /v1/account/fee-biss-deduction
 <!-- end with -->
 <!-- end if -->
 <!-- end if -->
 <!-- end with -->

## UserInfo

用户个人信息查询
    
> `GRPC` UserInfo([.biss.common.Empty](#.biss.common.Empty)) return [UserInfoResp](#UserInfoResp)






> `HTTP` `GET` /v1/account/user-info
 <!-- end with -->
 <!-- end if -->
 <!-- end if -->
 <!-- end with -->

## IpLog

最近登陆IP查询
    
> `GRPC` IpLog([ClientIpLogReq](#ClientIpLogReq)) return [ClientIpLogResp](#ClientIpLogResp)


 <!-- end with -->

## SendSMSVerifyCode

=====================================================
发送短信验证码到任意号码
    
> `GRPC` SendSMSVerifyCode([SendSMSVerifyCodeReq](#SendSMSVerifyCodeReq)) return [SendVerifyCodeResp](#SendVerifyCodeResp)


 <!-- end with -->

## SendUserSMSVerifyCode

发送短信验证码到用户绑定号码
    
> `GRPC` SendUserSMSVerifyCode([SendUserSMSVerifyCodeReq](#SendUserSMSVerifyCodeReq)) return [SendVerifyCodeResp](#SendVerifyCodeResp)


 <!-- end with -->

## SendEmailVerifyCode

发送邮件验证码到任意邮箱
    
> `GRPC` SendEmailVerifyCode([SendEmailVerifyCodeReq](#SendEmailVerifyCodeReq)) return [SendVerifyCodeResp](#SendVerifyCodeResp)






> `HTTP` `POST` /v1/account/send-email-verify-code
 <!-- end with -->
 <!-- end if -->
 <!-- end if -->
 <!-- end with -->

## SendUserEmailVerifyCode

发送邮件验证码到用户绑定邮箱
    
> `GRPC` SendUserEmailVerifyCode([SendUserEmailVerifyCodeReq](#SendUserEmailVerifyCodeReq)) return [SendVerifyCodeResp](#SendVerifyCodeResp)


 <!-- end with -->

## SendLoginSMSVerifyCode

发送登陆二次验证短信
    
> `GRPC` SendLoginSMSVerifyCode([SendLoginSMSVerifyCodeReq](#SendLoginSMSVerifyCodeReq)) return [SendVerifyCodeResp](#SendVerifyCodeResp)


 <!-- end with -->

## SendPasswordResetEmailVerifyCode

发送密码重置验证邮件
    
> `GRPC` SendPasswordResetEmailVerifyCode([SendPasswordResetEmailVerifyCodeReq](#SendPasswordResetEmailVerifyCodeReq)) return [SendVerifyCodeResp](#SendVerifyCodeResp)


 <!-- end with -->

## SendPasswordResetSMSVerifyCode

发送密码重置二次验证短信
    
> `GRPC` SendPasswordResetSMSVerifyCode([SendPasswordResetSMSVerifyCodeReq](#SendPasswordResetSMSVerifyCodeReq)) return [SendVerifyCodeResp](#SendVerifyCodeResp)


 <!-- end with -->

## GetGASecret

获取 GA Secret
    
> `GRPC` GetGASecret([.biss.common.Empty](#.biss.common.Empty)) return [GetGASecretResp](#GetGASecretResp)


 <!-- end with -->

 <!-- end methods -->
 <!-- end services -->


# 数据对象



## BindGAReq

绑定 GA 请求


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| sig | [bytes](#bytes) |  | 密码签名 |
| verify | [VerifyReq](#VerifyReq) |  | 验证码 |




## BindMobileReq

绑定手机号请求


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| nation_code | [string](#string) |  | 国家码 |
| mobile | [string](#string) |  | 号码 |
| sig | [bytes](#bytes) |  | 密码签名 |
| verify | [VerifyReq](#VerifyReq) |  | 验证码 |
| challenge | [Challenge](#Challenge) |  | Challenge Code, 验证密码使用 |




## Challenge

获取 Challenge Code，客户端使用后原样带回


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| ts | [uint32](#uint32) |  |  |
| nonce | [uint32](#uint32) |  |  |
| sig | [bytes](#bytes) |  |  |




## ChallengeResp

登陆挑战


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| challenge | [Challenge](#Challenge) |  |  |




## ClientIpLog




| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| time | [uint64](#uint64) |  |  |
| client_ip | [string](#string) |  |  |
| country | [string](#string) |  |  |
| city | [string](#string) |  |  |




## ClientIpLogReq




| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| page | [uint32](#uint32) |  |  |
| page_size | [uint32](#uint32) |  |  |




## ClientIpLogResp




| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| total | [uint32](#uint32) |  |  |
| page | [uint32](#uint32) |  |  |
| has_more | [bool](#bool) |  |  |
| ip_logs | [ClientIpLog](#ClientIpLog) | repeated |  |




## FeeBissDeductionReq

手续费BISS抵扣请求


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| switch | [bool](#bool) |  | 开关 |




## GetGASecretResp

获取 Google Two Factor 认证秘钥


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| secret | [string](#string) |  | GA 秘钥 |
| qr | [bytes](#bytes) |  | QR PNG 图片 |
| context | [VerifyContext](#VerifyContext) |  | 上下文 |




## KYCAuditReq

KYC 审核


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| country_code | [string](#string) |  | 国籍 |
| sure_name | [string](#string) |  | 名字 |
| given_name | [string](#string) |  | 姓氏 |
| id_number | [string](#string) |  | 证件号码 |
| urls | [string](#string) | repeated | 审核文件 URL |
| url_id_front | [string](#string) |  | 证件照正面Url |
| url_id_reverse | [string](#string) |  | 证件照反面Url |
| url_id_handheld | [string](#string) |  | 手持证件照Url |
| url_faceid_best | [string](#string) |  | 活体检测最佳照片Url |
| url_faceid_panorama | [string](#string) |  | 活体检测全景Url |
| faceid_delta | [string](#string) |  | 活体检测delta(用于faceid的verify) |




## KYCStatusResp

KYC 审核状态


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| status | [KYCStatus](#KYCStatus) |  |  |
| code | [int32](#int32) |  |  |
| mesg | [string](#string) |  |  |
| update_time | [uint32](#uint32) |  |  |




## KYCUploadReq

KYC 上传


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| files | [string](#string) | repeated | 上传的文件名列表，只使用数量和文件扩展名 |




## KYCUploadResp




| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| urls | [string](#string) | repeated | 上传 URL |




## LoginReq

登陆请求


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| account | [string](#string) |  | 账户名，目前仅支持 Email |
| challenge | [Challenge](#Challenge) |  | Challenge Code |
| sig | [bytes](#bytes) |  | 签名信息 |
| verifies | [Verifies](#Verifies) |  | 验证码 |




## LoginResp

登陆应答


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| uid | [uint64](#uint64) |  | 用户 ID |
| nick_name | [string](#string) |  | 用户名 |
| session | [bytes](#bytes) |  | Session |
| failures | [uint32](#uint32) |  | 连续登陆失败次数 |
| tfa | [VerifyType](#VerifyType) | repeated | 需要两部验证类型 |




## ModifyPasswordReq

修改密码请求


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| passkey | [bytes](#bytes) |  | 新密码公钥 |
| passwd_level | [PasswdLevel](#PasswdLevel) |  | 新密码强度 |
| sig_old | [bytes](#bytes) |  | 旧密码私钥对 pubKey 的签名 |
| sig_new | [bytes](#bytes) |  | 新密码私钥对 pubKey 的签名 |
| verifies | [Verifies](#Verifies) |  | 验证码 |
| challenge | [Challenge](#Challenge) |  | Challenge Code, 验证旧密码使用 |




## ModifyPasswordResp




| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| tfa | [VerifyType](#VerifyType) | repeated | 需要两部验证类型 |




## PointsInfo

积分信息


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| points | [uint64](#uint64) |  | 积分 |
| average_position | [string](#string) |  | 平均持仓 |




## RegisterReq

注册请求


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| email | [string](#string) |  |  |
| passkey | [bytes](#bytes) |  | 根据密码计算出的公钥 |
| sig | [bytes](#bytes) |  | 私钥对 Email 的签名 |
| passwd_level | [PasswdLevel](#PasswdLevel) |  | 安全等级 |
| verify | [VerifyReq](#VerifyReq) |  | 验证码 |
| invite_code | [string](#string) |  | 邀请码 |




## ResetPasswordReq

密码重置请求


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| account | [string](#string) |  |  |
| passkey | [bytes](#bytes) |  | 根据新密码计算出的公钥 |
| sig | [bytes](#bytes) |  | 新密码私钥对 token 的签名 |
| passwd_level | [PasswdLevel](#PasswdLevel) |  | 密码强度 |
| verifies | [Verifies](#Verifies) |  | Email 验证码 |




## ResetPasswordResp




| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| tfa | [VerifyType](#VerifyType) | repeated | 需要两部验证类型 |




## SendEmailVerifyCodeReq

发送邮件验证码到任意邮箱


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| email | [string](#string) |  | Email |
| scene | [VerifyScene](#VerifyScene) |  | 使用场景 |




## SendLoginSMSVerifyCodeReq

发送短信验证码到用户绑定的号码


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| account | [string](#string) |  | 账号 |
| challenge | [Challenge](#Challenge) |  | Challenge Code |
| sig | [bytes](#bytes) |  | 签名 |




## SendPasswordResetEmailVerifyCodeReq

发送邮箱验证码到用户绑定的号码


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| account | [string](#string) |  | 账号 |




## SendPasswordResetSMSVerifyCodeReq

发送短信验证码到用户绑定的号码


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| account | [string](#string) |  | 账号 |
| verify | [VerifyReq](#VerifyReq) |  | 邮件验证码 |




## SendSMSVerifyCodeReq

发送短信验证码到任意号码


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| nation_code | [string](#string) |  | 国家码 |
| mobile | [string](#string) |  | 号码 |
| scene | [VerifyScene](#VerifyScene) |  | 使用场景 |




## SendUserEmailVerifyCodeReq

发送邮件验证码到用户绑定的邮箱


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| scene | [VerifyScene](#VerifyScene) |  | 使用场景 |




## SendUserSMSVerifyCodeReq

发送短信验证码到用户绑定的号码


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| scene | [VerifyScene](#VerifyScene) |  | 使用场景 |




## SendVerifyCodeResp

验证码发送应答


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| context | [VerifyContext](#VerifyContext) |  | 上下文 |




## UserConfigInfo

用户配置信息


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| fee_biss_deduction | [bool](#bool) |  | 手续费BISS抵扣 |




## UserInfoResp




| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| account | [string](#string) |  |  |
| withdraw_limit | [string](#string) |  | 提款额度 |
| passwd_level | [PasswdLevel](#PasswdLevel) |  | 密码强度 |
| secu_level | [SecuLevel](#SecuLevel) |  | 安全等级 |
| kyc_status | [KYCStatus](#KYCStatus) |  | 身份是否认证 |
| mobile | [string](#string) |  |  |
| tfa | [VerifyType](#VerifyType) | repeated | 支持的两步验证类型 |
| invite_code | [string](#string) |  | 邀请码 |
| user_config_info | [UserConfigInfo](#UserConfigInfo) |  | 用户配置信息 |
| vip_info | [VipInfo](#VipInfo) |  | 会员信息 |
| points_info | [PointsInfo](#PointsInfo) |  | 积分信息 |




## Verifies




| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| email | [VerifyReq](#VerifyReq) |  |  |
| mobile | [VerifyReq](#VerifyReq) |  |  |
| ga | [VerifyReq](#VerifyReq) |  |  |




## VerifyContext

验证码上下文


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| type | [VerifyType](#VerifyType) |  | 验证类型 |
| scene | [VerifyScene](#VerifyScene) |  | 使用场景 |
| ts | [uint32](#uint32) |  | 时间戳 |
| nonce | [uint32](#uint32) |  | 随机数 |
| ext | [bytes](#bytes) |  | 扩展信息 |




## VerifyReq

验证码提交请求


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| code | [string](#string) |  | 验证码 |
| context | [VerifyContext](#VerifyContext) |  | 上下文 |




## VipInfo

会员信息


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| level | [biss.common.VipLevel](#biss.common.VipLevel) |  | 会员级别 |
| start_date | [uint64](#uint64) |  | 以下字段仅在用户为会员时有效

开始日期(UTC timestamp in millisecond)(仅年月日有效) |
| finish_date | [uint64](#uint64) |  | 结束日期(UTC timestamp in millisecond)(仅年月日有效) |


 <!-- end messages -->

# 枚举类型


<a name="biss.api.v1.account.KYCStatus"></a>

## KYCStatus


| Name | Number | Description |
| ---- | ------ | ----------- |
| KYC_NONE | 0 |  |
| KYC_PROCESSING | 1 |  |
| KYC_SUCC | 2 |  |
| KYC_FAILED | 3 |  |



<a name="biss.api.v1.account.PasswdLevel"></a>

## PasswdLevel


| Name | Number | Description |
| ---- | ------ | ----------- |
| PL_NONE | 0 |  |
| PL_LOW | 1 |  |
| PL_MIDDLE | 2 |  |
| PL_HIGH | 3 |  |



<a name="biss.api.v1.account.SecuLevel"></a>

## SecuLevel


| Name | Number | Description |
| ---- | ------ | ----------- |
| SL_NONE | 0 |  |
| SL_LOW | 1 |  |
| SL_MIDDLE | 2 |  |
| SL_HIGH | 3 |  |



<a name="biss.api.v1.account.VerifyScene"></a>

## VerifyScene
验证场景

| Name | Number | Description |
| ---- | ------ | ----------- |
| VS_NONE | 0 | 默认值 |
| VS_REGISTER | 1 | 注册 |
| VS_LOGIN | 2 | 登陆 |
| VS_RESET_PASSWORD | 3 | 重置密码 |
| VS_MODIFY_PASSWORD | 4 | 修改密码 |
| VS_BIND_GA | 5 | 绑定 GA |
| VS_MODIFY_GA | 6 | 修改 GA |
| VS_BIND_MOBILE | 7 | 绑定手机 |
| VS_MODIFY_MOBILE | 8 | 修改手机 |
| VS_WITHDRAW | 9 | 提现 |
| VS_USER_FROZON | 10 | 冻结用户(没有用验证，但是要发邮件） |



<a name="biss.api.v1.account.VerifyType"></a>

## VerifyType
验证类型

| Name | Number | Description |
| ---- | ------ | ----------- |
| VT_NONE | 0 | 默认值 |
| VT_SMS | 1 | 短信 |
| VT_EMAIL | 2 | 邮件 |
| VT_GA | 3 | Google |


 <!-- end enums -->



