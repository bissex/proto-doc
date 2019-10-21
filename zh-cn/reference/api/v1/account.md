# Protocol Documentation
<a name="top"></a>

## Table of Contents

- [proto/api/v1/account.proto](#proto/api/v1/account.proto)
    - [BindGAReq](#biss.api.v1.account.BindGAReq)
    - [BindMobileReq](#biss.api.v1.account.BindMobileReq)
    - [Challenge](#biss.api.v1.account.Challenge)
    - [ChallengeResp](#biss.api.v1.account.ChallengeResp)
    - [ClientIpLog](#biss.api.v1.account.ClientIpLog)
    - [ClientIpLogReq](#biss.api.v1.account.ClientIpLogReq)
    - [ClientIpLogResp](#biss.api.v1.account.ClientIpLogResp)
    - [FeeBissDeductionReq](#biss.api.v1.account.FeeBissDeductionReq)
    - [GetGASecretResp](#biss.api.v1.account.GetGASecretResp)
    - [KYCAuditReq](#biss.api.v1.account.KYCAuditReq)
    - [KYCStatusResp](#biss.api.v1.account.KYCStatusResp)
    - [KYCUploadReq](#biss.api.v1.account.KYCUploadReq)
    - [KYCUploadResp](#biss.api.v1.account.KYCUploadResp)
    - [LoginReq](#biss.api.v1.account.LoginReq)
    - [LoginResp](#biss.api.v1.account.LoginResp)
    - [ModifyPasswordReq](#biss.api.v1.account.ModifyPasswordReq)
    - [ModifyPasswordResp](#biss.api.v1.account.ModifyPasswordResp)
    - [OpenSubAccountReq](#biss.api.v1.account.OpenSubAccountReq)
    - [PointsInfo](#biss.api.v1.account.PointsInfo)
    - [RegisterReq](#biss.api.v1.account.RegisterReq)
    - [ResetPasswordReq](#biss.api.v1.account.ResetPasswordReq)
    - [ResetPasswordResp](#biss.api.v1.account.ResetPasswordResp)
    - [SendEmailVerifyCodeReq](#biss.api.v1.account.SendEmailVerifyCodeReq)
    - [SendLoginSMSVerifyCodeReq](#biss.api.v1.account.SendLoginSMSVerifyCodeReq)
    - [SendPasswordResetEmailVerifyCodeReq](#biss.api.v1.account.SendPasswordResetEmailVerifyCodeReq)
    - [SendPasswordResetSMSVerifyCodeReq](#biss.api.v1.account.SendPasswordResetSMSVerifyCodeReq)
    - [SendSMSVerifyCodeReq](#biss.api.v1.account.SendSMSVerifyCodeReq)
    - [SendUserEmailVerifyCodeReq](#biss.api.v1.account.SendUserEmailVerifyCodeReq)
    - [SendUserSMSVerifyCodeReq](#biss.api.v1.account.SendUserSMSVerifyCodeReq)
    - [SendVerifyCodeResp](#biss.api.v1.account.SendVerifyCodeResp)
    - [UserConfigInfo](#biss.api.v1.account.UserConfigInfo)
    - [UserInfoResp](#biss.api.v1.account.UserInfoResp)
    - [Verifies](#biss.api.v1.account.Verifies)
    - [VerifyContext](#biss.api.v1.account.VerifyContext)
    - [VerifyReq](#biss.api.v1.account.VerifyReq)
    - [VipInfo](#biss.api.v1.account.VipInfo)
  
    - [KYCStatus](#biss.api.v1.account.KYCStatus)
    - [PasswdLevel](#biss.api.v1.account.PasswdLevel)
    - [SecuLevel](#biss.api.v1.account.SecuLevel)
    - [VerifyScene](#biss.api.v1.account.VerifyScene)
    - [VerifyType](#biss.api.v1.account.VerifyType)
  
  
    - [Account](#biss.api.v1.account.Account)
  

- [Scalar Value Types](#scalar-value-types)



<a name="proto/api/v1/account.proto"></a>
<p align="right"><a href="#top">Top</a></p>

## proto/api/v1/account.proto



<a name="biss.api.v1.account.BindGAReq"></a>

### BindGAReq
绑定 GA 请求


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| sig | [bytes](#bytes) |  | 密码签名 |
| verify | [VerifyReq](#biss.api.v1.account.VerifyReq) |  | 验证码 |






<a name="biss.api.v1.account.BindMobileReq"></a>

### BindMobileReq
绑定手机号请求


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| nation_code | [string](#string) |  | 国家码 |
| mobile | [string](#string) |  | 号码 |
| sig | [bytes](#bytes) |  | 密码签名 |
| verify | [VerifyReq](#biss.api.v1.account.VerifyReq) |  | 验证码 |
| challenge | [Challenge](#biss.api.v1.account.Challenge) |  | Challenge Code, 验证密码使用 |






<a name="biss.api.v1.account.Challenge"></a>

### Challenge
获取 Challenge Code，客户端使用后原样带回


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| ts | [uint32](#uint32) |  |  |
| nonce | [uint32](#uint32) |  |  |
| sig | [bytes](#bytes) |  |  |






<a name="biss.api.v1.account.ChallengeResp"></a>

### ChallengeResp
登陆挑战


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| challenge | [Challenge](#biss.api.v1.account.Challenge) |  |  |






<a name="biss.api.v1.account.ClientIpLog"></a>

### ClientIpLog



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| time | [uint64](#uint64) |  |  |
| client_ip | [string](#string) |  |  |
| country | [string](#string) |  |  |
| city | [string](#string) |  |  |






<a name="biss.api.v1.account.ClientIpLogReq"></a>

### ClientIpLogReq



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| page | [uint32](#uint32) |  |  |
| page_size | [uint32](#uint32) |  |  |






<a name="biss.api.v1.account.ClientIpLogResp"></a>

### ClientIpLogResp



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| total | [uint32](#uint32) |  |  |
| page | [uint32](#uint32) |  |  |
| has_more | [bool](#bool) |  |  |
| ip_logs | [ClientIpLog](#biss.api.v1.account.ClientIpLog) | repeated |  |






<a name="biss.api.v1.account.FeeBissDeductionReq"></a>

### FeeBissDeductionReq
手续费BISS抵扣请求


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| switch | [bool](#bool) |  | 开关 |






<a name="biss.api.v1.account.GetGASecretResp"></a>

### GetGASecretResp
获取 Google Two Factor 认证秘钥


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| secret | [string](#string) |  | GA 秘钥 |
| qr | [bytes](#bytes) |  | QR PNG 图片 |
| context | [VerifyContext](#biss.api.v1.account.VerifyContext) |  | 上下文 |






<a name="biss.api.v1.account.KYCAuditReq"></a>

### KYCAuditReq
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






<a name="biss.api.v1.account.KYCStatusResp"></a>

### KYCStatusResp
KYC 审核状态


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| status | [KYCStatus](#biss.api.v1.account.KYCStatus) |  |  |
| code | [int32](#int32) |  |  |
| mesg | [string](#string) |  |  |
| update_time | [uint32](#uint32) |  |  |






<a name="biss.api.v1.account.KYCUploadReq"></a>

### KYCUploadReq
KYC 上传


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| files | [string](#string) | repeated | 上传的文件名列表，只使用数量和文件扩展名 |






<a name="biss.api.v1.account.KYCUploadResp"></a>

### KYCUploadResp



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| urls | [string](#string) | repeated | 上传 URL |






<a name="biss.api.v1.account.LoginReq"></a>

### LoginReq
登陆请求


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| account | [string](#string) |  | 账户名，目前仅支持 Email |
| challenge | [Challenge](#biss.api.v1.account.Challenge) |  | Challenge Code |
| sig | [bytes](#bytes) |  | 签名信息 |
| verifies | [Verifies](#biss.api.v1.account.Verifies) |  | 验证码 |






<a name="biss.api.v1.account.LoginResp"></a>

### LoginResp
登陆应答


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| uid | [uint64](#uint64) |  | 用户 ID |
| nick_name | [string](#string) |  | 用户名 |
| session | [bytes](#bytes) |  | Session |
| failures | [uint32](#uint32) |  | 连续登陆失败次数 |
| tfa | [VerifyType](#biss.api.v1.account.VerifyType) | repeated | 需要两部验证类型 |






<a name="biss.api.v1.account.ModifyPasswordReq"></a>

### ModifyPasswordReq
修改密码请求


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| passkey | [bytes](#bytes) |  | 新密码公钥 |
| passwd_level | [PasswdLevel](#biss.api.v1.account.PasswdLevel) |  | 新密码强度 |
| sig_old | [bytes](#bytes) |  | 旧密码私钥对 pubKey 的签名 |
| sig_new | [bytes](#bytes) |  | 新密码私钥对 pubKey 的签名 |
| verifies | [Verifies](#biss.api.v1.account.Verifies) |  | 验证码 |
| challenge | [Challenge](#biss.api.v1.account.Challenge) |  | Challenge Code, 验证旧密码使用 |






<a name="biss.api.v1.account.ModifyPasswordResp"></a>

### ModifyPasswordResp



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| tfa | [VerifyType](#biss.api.v1.account.VerifyType) | repeated | 需要两部验证类型 |






<a name="biss.api.v1.account.OpenSubAccountReq"></a>

### OpenSubAccountReq
开通子账户请求


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| type | [biss.common.AccountType](#biss.common.AccountType) |  | 开通子账户类型 |






<a name="biss.api.v1.account.PointsInfo"></a>

### PointsInfo
积分信息


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| points | [uint64](#uint64) |  | 积分 |
| average_position | [string](#string) |  | 平均持仓 |






<a name="biss.api.v1.account.RegisterReq"></a>

### RegisterReq
注册请求


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| email | [string](#string) |  |  |
| passkey | [bytes](#bytes) |  | 根据密码计算出的公钥 |
| sig | [bytes](#bytes) |  | 私钥对 Email 的签名 |
| passwd_level | [PasswdLevel](#biss.api.v1.account.PasswdLevel) |  | 安全等级 |
| verify | [VerifyReq](#biss.api.v1.account.VerifyReq) |  | 验证码 |
| invite_code | [string](#string) |  | 邀请码 |






<a name="biss.api.v1.account.ResetPasswordReq"></a>

### ResetPasswordReq
密码重置请求


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| account | [string](#string) |  |  |
| passkey | [bytes](#bytes) |  | 根据新密码计算出的公钥 |
| sig | [bytes](#bytes) |  | 新密码私钥对 token 的签名 |
| passwd_level | [PasswdLevel](#biss.api.v1.account.PasswdLevel) |  | 密码强度 |
| verifies | [Verifies](#biss.api.v1.account.Verifies) |  | Email 验证码 |






<a name="biss.api.v1.account.ResetPasswordResp"></a>

### ResetPasswordResp



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| tfa | [VerifyType](#biss.api.v1.account.VerifyType) | repeated | 需要两部验证类型 |






<a name="biss.api.v1.account.SendEmailVerifyCodeReq"></a>

### SendEmailVerifyCodeReq
发送邮件验证码到任意邮箱


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| email | [string](#string) |  | Email |
| scene | [VerifyScene](#biss.api.v1.account.VerifyScene) |  | 使用场景 |






<a name="biss.api.v1.account.SendLoginSMSVerifyCodeReq"></a>

### SendLoginSMSVerifyCodeReq
发送短信验证码到用户绑定的号码


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| account | [string](#string) |  | 账号 |
| challenge | [Challenge](#biss.api.v1.account.Challenge) |  | Challenge Code |
| sig | [bytes](#bytes) |  | 签名 |






<a name="biss.api.v1.account.SendPasswordResetEmailVerifyCodeReq"></a>

### SendPasswordResetEmailVerifyCodeReq
发送邮箱验证码到用户绑定的号码


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| account | [string](#string) |  | 账号 |






<a name="biss.api.v1.account.SendPasswordResetSMSVerifyCodeReq"></a>

### SendPasswordResetSMSVerifyCodeReq
发送短信验证码到用户绑定的号码


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| account | [string](#string) |  | 账号 |
| verify | [VerifyReq](#biss.api.v1.account.VerifyReq) |  | 邮件验证码 |






<a name="biss.api.v1.account.SendSMSVerifyCodeReq"></a>

### SendSMSVerifyCodeReq
发送短信验证码到任意号码


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| nation_code | [string](#string) |  | 国家码 |
| mobile | [string](#string) |  | 号码 |
| scene | [VerifyScene](#biss.api.v1.account.VerifyScene) |  | 使用场景 |






<a name="biss.api.v1.account.SendUserEmailVerifyCodeReq"></a>

### SendUserEmailVerifyCodeReq
发送邮件验证码到用户绑定的邮箱


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| scene | [VerifyScene](#biss.api.v1.account.VerifyScene) |  | 使用场景 |






<a name="biss.api.v1.account.SendUserSMSVerifyCodeReq"></a>

### SendUserSMSVerifyCodeReq
发送短信验证码到用户绑定的号码


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| scene | [VerifyScene](#biss.api.v1.account.VerifyScene) |  | 使用场景 |






<a name="biss.api.v1.account.SendVerifyCodeResp"></a>

### SendVerifyCodeResp
验证码发送应答


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| context | [VerifyContext](#biss.api.v1.account.VerifyContext) |  | 上下文 |






<a name="biss.api.v1.account.UserConfigInfo"></a>

### UserConfigInfo
用户配置信息


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| fee_biss_deduction | [bool](#bool) |  | 手续费BISS抵扣 |






<a name="biss.api.v1.account.UserInfoResp"></a>

### UserInfoResp



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| account | [string](#string) |  |  |
| withdraw_limit | [string](#string) |  | 提款额度 |
| passwd_level | [PasswdLevel](#biss.api.v1.account.PasswdLevel) |  | 密码强度 |
| secu_level | [SecuLevel](#biss.api.v1.account.SecuLevel) |  | 安全等级 |
| kyc_status | [KYCStatus](#biss.api.v1.account.KYCStatus) |  | 身份是否认证 |
| mobile | [string](#string) |  |  |
| tfa | [VerifyType](#biss.api.v1.account.VerifyType) | repeated | 支持的两步验证类型 |
| invite_code | [string](#string) |  | 邀请码 |
| user_config_info | [UserConfigInfo](#biss.api.v1.account.UserConfigInfo) |  | 用户配置信息 |
| vip_info | [VipInfo](#biss.api.v1.account.VipInfo) |  | 会员信息 |
| points_info | [PointsInfo](#biss.api.v1.account.PointsInfo) |  | 积分信息 |
| contract_account | [bool](#bool) |  | 是否已开通合约账户 |






<a name="biss.api.v1.account.Verifies"></a>

### Verifies



| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| email | [VerifyReq](#biss.api.v1.account.VerifyReq) |  |  |
| mobile | [VerifyReq](#biss.api.v1.account.VerifyReq) |  |  |
| ga | [VerifyReq](#biss.api.v1.account.VerifyReq) |  |  |






<a name="biss.api.v1.account.VerifyContext"></a>

### VerifyContext
验证码上下文


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| type | [VerifyType](#biss.api.v1.account.VerifyType) |  | 验证类型 |
| scene | [VerifyScene](#biss.api.v1.account.VerifyScene) |  | 使用场景 |
| ts | [uint32](#uint32) |  | 时间戳 |
| nonce | [uint32](#uint32) |  | 随机数 |
| ext | [bytes](#bytes) |  | 扩展信息 |






<a name="biss.api.v1.account.VerifyReq"></a>

### VerifyReq
验证码提交请求


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| code | [string](#string) |  | 验证码 |
| context | [VerifyContext](#biss.api.v1.account.VerifyContext) |  | 上下文 |






<a name="biss.api.v1.account.VipInfo"></a>

### VipInfo
会员信息


| Field | Type | Label | Description |
| ----- | ---- | ----- | ----------- |
| level | [biss.common.VipLevel](#biss.common.VipLevel) |  | 会员级别 |
| start_date | [uint64](#uint64) |  | 以下字段仅在用户为会员时有效

开始日期(UTC timestamp in millisecond)(仅年月日有效) |
| finish_date | [uint64](#uint64) |  | 结束日期(UTC timestamp in millisecond)(仅年月日有效) |





 


<a name="biss.api.v1.account.KYCStatus"></a>

### KYCStatus


| Name | Number | Description |
| ---- | ------ | ----------- |
| KYC_NONE | 0 |  |
| KYC_PROCESSING | 1 |  |
| KYC_SUCC | 2 |  |
| KYC_FAILED | 3 |  |



<a name="biss.api.v1.account.PasswdLevel"></a>

### PasswdLevel


| Name | Number | Description |
| ---- | ------ | ----------- |
| PL_NONE | 0 |  |
| PL_LOW | 1 |  |
| PL_MIDDLE | 2 |  |
| PL_HIGH | 3 |  |



<a name="biss.api.v1.account.SecuLevel"></a>

### SecuLevel


| Name | Number | Description |
| ---- | ------ | ----------- |
| SL_NONE | 0 |  |
| SL_LOW | 1 |  |
| SL_MIDDLE | 2 |  |
| SL_HIGH | 3 |  |



<a name="biss.api.v1.account.VerifyScene"></a>

### VerifyScene
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

### VerifyType
验证类型

| Name | Number | Description |
| ---- | ------ | ----------- |
| VT_NONE | 0 | 默认值 |
| VT_SMS | 1 | 短信 |
| VT_EMAIL | 2 | 邮件 |
| VT_GA | 3 | Google |


 

 


<a name="biss.api.v1.account.Account"></a>

### Account


| Method Name | Request Type | Response Type | Description |
| ----------- | ------------ | ------------- | ------------|
| Register | [RegisterReq](#biss.api.v1.account.RegisterReq) | [.biss.common.Empty](#biss.common.Empty) | =================================================== 注册 |
| Challenge | [.biss.common.Empty](#biss.common.Empty) | [ChallengeResp](#biss.api.v1.account.ChallengeResp) | 登陆 Challenge |
| Login | [LoginReq](#biss.api.v1.account.LoginReq) | [LoginResp](#biss.api.v1.account.LoginResp) | 登陆 |
| Logout | [.biss.common.Empty](#biss.common.Empty) | [.biss.common.Empty](#biss.common.Empty) | 登出 |
| ModifyPassword | [ModifyPasswordReq](#biss.api.v1.account.ModifyPasswordReq) | [ModifyPasswordResp](#biss.api.v1.account.ModifyPasswordResp) | ==================================================== 修改密码 |
| ResetPassword | [ResetPasswordReq](#biss.api.v1.account.ResetPasswordReq) | [ResetPasswordResp](#biss.api.v1.account.ResetPasswordResp) | 重置密码 |
| BindMobile | [BindMobileReq](#biss.api.v1.account.BindMobileReq) | [.biss.common.Empty](#biss.common.Empty) | ===================================================== 绑定手机 |
| BindGA | [BindGAReq](#biss.api.v1.account.BindGAReq) | [.biss.common.Empty](#biss.common.Empty) | 绑定 Google 2-Step Auth |
| KYCUpload | [KYCUploadReq](#biss.api.v1.account.KYCUploadReq) | [KYCUploadResp](#biss.api.v1.account.KYCUploadResp) | KYC 文件上传请求 |
| KYCAudit | [KYCAuditReq](#biss.api.v1.account.KYCAuditReq) | [.biss.common.Empty](#biss.common.Empty) | KYC 审核请求 |
| KYCStatus | [.biss.common.Empty](#biss.common.Empty) | [KYCStatusResp](#biss.api.v1.account.KYCStatusResp) | KYC 审核状态请求 |
| FeeBissDeduction | [FeeBissDeductionReq](#biss.api.v1.account.FeeBissDeductionReq) | [.biss.common.Empty](#biss.common.Empty) | 手续费BISS抵扣 |
| UserInfo | [.biss.common.Empty](#biss.common.Empty) | [UserInfoResp](#biss.api.v1.account.UserInfoResp) | 用户个人信息查询 |
| IpLog | [ClientIpLogReq](#biss.api.v1.account.ClientIpLogReq) | [ClientIpLogResp](#biss.api.v1.account.ClientIpLogResp) | 最近登陆IP查询 |
| SendSMSVerifyCode | [SendSMSVerifyCodeReq](#biss.api.v1.account.SendSMSVerifyCodeReq) | [SendVerifyCodeResp](#biss.api.v1.account.SendVerifyCodeResp) | ===================================================== 发送短信验证码到任意号码 |
| SendUserSMSVerifyCode | [SendUserSMSVerifyCodeReq](#biss.api.v1.account.SendUserSMSVerifyCodeReq) | [SendVerifyCodeResp](#biss.api.v1.account.SendVerifyCodeResp) | 发送短信验证码到用户绑定号码 |
| SendEmailVerifyCode | [SendEmailVerifyCodeReq](#biss.api.v1.account.SendEmailVerifyCodeReq) | [SendVerifyCodeResp](#biss.api.v1.account.SendVerifyCodeResp) | 发送邮件验证码到任意邮箱 |
| SendUserEmailVerifyCode | [SendUserEmailVerifyCodeReq](#biss.api.v1.account.SendUserEmailVerifyCodeReq) | [SendVerifyCodeResp](#biss.api.v1.account.SendVerifyCodeResp) | 发送邮件验证码到用户绑定邮箱 |
| SendLoginSMSVerifyCode | [SendLoginSMSVerifyCodeReq](#biss.api.v1.account.SendLoginSMSVerifyCodeReq) | [SendVerifyCodeResp](#biss.api.v1.account.SendVerifyCodeResp) | 发送登陆二次验证短信 |
| SendPasswordResetEmailVerifyCode | [SendPasswordResetEmailVerifyCodeReq](#biss.api.v1.account.SendPasswordResetEmailVerifyCodeReq) | [SendVerifyCodeResp](#biss.api.v1.account.SendVerifyCodeResp) | 发送密码重置验证邮件 |
| SendPasswordResetSMSVerifyCode | [SendPasswordResetSMSVerifyCodeReq](#biss.api.v1.account.SendPasswordResetSMSVerifyCodeReq) | [SendVerifyCodeResp](#biss.api.v1.account.SendVerifyCodeResp) | 发送密码重置二次验证短信 |
| GetGASecret | [.biss.common.Empty](#biss.common.Empty) | [GetGASecretResp](#biss.api.v1.account.GetGASecretResp) | 获取 GA Secret |
| OpenSubAccount | [OpenSubAccountReq](#biss.api.v1.account.OpenSubAccountReq) | [.biss.common.Empty](#biss.common.Empty) | 开通子账户 |

 



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

