# ConfigHealthCheck {#reference1542 .reference}

调用ConfigHealthCheck配置4层/7层健康检查。

## 请求参数 { .section}

|名称|类型|是否必需|描述|
|--|--|----|--|
|InstanceId|String|是|要操作的实例ID。|
|ForwardProtocol|String|是|转发协议，取值：-   TCP（四层）
-   UDP（四层）
-   HTTP（七层）

|
|FrontendPort|Integer|是|前端端口。|
|HealthCheck|String|是|传入HealthCheck对象JSON串，具体结构描述见[HealthCheck](#)。|

|名称|类型|是否必需|描述|
|--|--|----|--|
|Type|String|是|协议类型。取值：-   TCP（四层）
-   HTTP（七层）

|
|Domain|String|否|健康检查/七层健康检查/域名。|
|Uri|String|否|健康检查/七层健康检查/检查路径。|
|Timeout|Integer|否|健康检查/四层健康检查/响应超时时间。|
|Port|Integer|否|健康检查/四层健康检查/检查端口。|
|Interval|Integer|否|健康检查/四层健康检查/检查间隔。|
|Up|Integer|否|健康检查/四层健康检查/健康阈值。|
|Down|Integer|否|健康检查/四层健康检查/不健康阈值。|

## 返回参数 { .section}

|名称|类型|描述|
|--|--|--|
|RequestId|String|本次请求的ID。|

## 示例 { .section}

**请求示例**

```
{
  "InstanceId": "0bcf28g5-d57c-11e7-9bs0-d89d6717dxbc",
  "ForwardProtocol": "tcp",
  "FrontendPort": 80,
  "HealthCheck": "{\"Type\":\"tcp\",\"Timeout\":10,\"Port\":80,\"Interval\":10,\"Up\":10,\"Down\":40}"
}

```

**返回示例**

```
{
  "RequestId": "0bcf28g5-d57c-11e7-9bs0-d89d6717dxbc"
}

```

