# ConfigDomainAccessMode {#reference522 .reference}

调用ConfigDomainAccessMode设置域名接入模式。

## 请求参数 { .section}

|名称|类型|是否必需|描述|
|--|--|----|--|
|Domain|String|是|要操作的域名。|
|AccessMode|Integer|是|接入模式，取值：-   0：A记录
-   1：高防
-   2：回源

|

## 返回参数 { .section}

|名称|类型|描述|
|--|--|--|
|RequestId|String|本次请求的ID。|

## 示例 { .section}

**请求示例**

```
{
  "Domain": "www.alibaba.com",
  "AccessMode": 1
}

```

**返回示例**

```
{
  "RequestId": "0bcf28g5-d57c-11e7-9bs0-d89d6717dxbc",
}

```

