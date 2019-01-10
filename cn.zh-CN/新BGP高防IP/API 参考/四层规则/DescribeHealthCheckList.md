# DescribeHealthCheckList {#reference2091 .reference}

调用DescribeHealthCheckList查询4层/7层健康检查列表。

## 请求参数 { .section}

|名称|类型|是否必需|描述|
|--|--|----|--|
|Listeners|String|是|要查询的Listeners数组JSON串，每个Listener的具体结构描述见[Listener](#)。|

|名称|类型|是否必需|描述|
|--|--|----|--|
|InstanceId|String|是|实例ID。|
|Protocol|String|是|协议类型。|
|FrontendPort|Integer|是|前端使用的端口，范围：0-65535。|
|BackendPort|Integer|否|后端使用的端口，范围：0-65535。|
|RealServers|Json数组|否|源站IP地址。|
|IsAutoCreate|Boolean|否|是否自动创建。如果是，则不允许删除和修改。|

## 返回参数 { .section}

|名称|类型|描述|
|--|--|--|
|Total|Integer|结果总数。|
|HealthCheck|HealthCheck|健康检查信息。具体结构描述见[HealthCheck](#)。|
|RequestId|String|请求ID。|

|名称|类型|描述|
|--|--|--|
|Type|String|协议类型，取值：-   TCP（四层）
-   HTTP（七层）

|
|Domain|String|健康检查/七层健康检查/域名。|
|Uri|String|健康检查/七层健康检查/检查路径。|
|Timeout|Integer|健康检查/四层健康检查/响应超时时间。|
|Port|Integer|健康检查/四层健康检查/检查端口。|
|Interval|Integer|健康检查/四层健康检查/检查间隔。|
|Up|Integer|健康检查/四层健康检查/健康阈值。|
|Down|Integer|健康检查/四层健康检查/不健康阈值。|

## 示例 { .section}

**请求示例**

```
{
  "Listeners": "[{\"InstanceId\":\"0bcf28g5-d57c-11e7-9bs0-d89d6717dxbc\",\"Protocol\":\"tcp\",\"FrontendPort\":80}]"
}

```

**返回示例**

```
{
  "Total": 1,
  "HealthCheck": [
    {
      "InstanceId": "0bcf28g5-d57c-11e7-9bs0-d89d6717dxbc",
      "Protocol": "tcp",
      "FrontendPort": 80,
      "HealthCheck": {
        "Type": "tcp",
        "Timeout": 10,
        "Port": 80,
        "Interval": 10,
        "Up": 10,
        "Down": 20
      }
    }
  ],
  "RequestId": "0bcf28g5-d57c-11e7-9bs0-d89d6717dxbc"
}

```

