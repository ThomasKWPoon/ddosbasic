# DescribeLayer4Rules {#reference1674 .reference}

调用DescribeLayer4Rules查询指定实例的四层转发规则。

## 请求参数 { .section}

|名称|类型|是否必需|描述|
|--|--|----|--|
|InstanceId|String|是|要查询的实例ID。|
|ForwardProtocol|String|否|转发协议，取值：TCP。|
|FrontendPort|Integer|否|前端端口。|
|Offset|Integer|是|开始索引位置，即从第几个结果开始返回。**说明：** 如果不传入该参数，则从第0个结果开始返回。

|
|PageSize|Integer|是|分页大小，即每页显示多少个结果。最大值50。|

## 返回参数 {#section_s32_11v_jgb .section}

|名称|类型|描述|
|--|--|--|
|Total|Integer|结果总数。|
|Listeners|Listener\[\]|Listeners数组。具体结构描述见[Listener](#)。|
|RequestId|String|本次请求的ID。|

|名称|类型|描述|
|--|--|--|
|InstanceId|String|实例ID。|
|Protocol|String|协议类型。|
|FrontendPort|Integer|前端使用的端口，范围：0-65535。|
|BackendPort|Integer|后端使用的端口，范围：0-65535。|
|RealServers|Json数组|源站IP地址。|
|IsAutoCreate|Boolean|是否自动创建。如果是，则不允许删除和修改。|

## 示例 { .section}

**请求示例**

```
{
  "InstanceId": "0bcf28g5-d57c-11e7-9bs0-d89d6717dxbc",
  "ForwardProtocol": "tcp",
  "FrontendPort": 80,
  "Offset": 1,
  "PageSize": 10
}

```

**返回示例**

```
{
  "Total": 1,
  "Listeners": [
    {
      "InstanceId": "0bcf28g5-d57c-11e7-9bs0-d89d6717dxbc",
      "Protocol": "tcp",
      "FrontendPort": 80,
	  "BackendPort":80,
      "RealServers": [
        "1.1.1.1",
        "2.2.2.2"
      ],
      "IsAutoCreate": true
    }
  ],
  "RequestId": "0bcf28g5-d57c-11e7-9bs0-d89d6717dxbc"
}

```

