# ConfigLayer7Cert {#reference928 .reference}

调用ConfigLayer7Cert为指定域名配置7层证书。

## 请求参数 { .section}

|名称|类型|是否必需|描述|
|--|--|----|--|
|Domain|String|是|要操作的域名。|
|CertId|Integer|否|证书ID。**说明：** 若传入此参数，则无需传入CertName、Cert、Key。

|
|CertName|String|否|证书名称。**说明：** 若传入此参数，则必须同时传入Cert和Key。若传入CertName、Cert、Key组合，则无需传入CertId。

|
|Cert|String|否|证书公钥。**说明：** 若传入此参数，则必须同时传入CertName和Key。若传入CertName、Cert、Key组合，则无需传入CertId。

|
|Key|String|否|证书私钥。**说明：** 若传入此参数，则必须同时传入CertName和Cert。若传入CertName、Cert、Key组合，则无需传入CertId。

|

## 返回参数 { .section}

|名称|类型|描述|
|--|--|--|
|RequestId|String|本次请求的ID。|

## 示例 { .section}

**请求示例**

```
{
  "Domain" : "www.alibaba.com",
  "CertId" : 1,
  "CertName" : "xxxx",
  "Cert" : "abc",
  "Key" : "bcd"
}

```

**返回示例**

```
{
  "RequestId": "0bcf28g5-d57c-11e7-9bs0-d89d6717dxbc"
}

```

