# ConfigLayer7CCTemplate {#reference593 .reference}

调用ConfigLayer7CCTemplate为指定域名设置7层CC防护模式。

## 请求参数 { .section}

|名称|类型|是否必需|描述|
|--|--|----|--|
|Domain|String|是|要操作的域名。|
|Template|String|是|要应用的CC防护模式，取值：-   default：正常
-   gf\_under\_attack：攻击紧急
-   gf\_sos\_verify：严格
-   gf\_sos\_enhance：超级严格

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
  "Template":"XXXX"
}

```

**返回示例**

```
{
  "RequestId": "0bcf28g5-d57c-11e7-9bs0-d89d6717dxbc"
}

```

