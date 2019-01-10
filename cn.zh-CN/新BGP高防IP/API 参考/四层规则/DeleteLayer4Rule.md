# DeleteLayer4Rule {#reference829 .reference}

调用DeleteLayer4Rule删除4层转发规则。

## 请求参数 { .section}

|名称|类型|是否必需|描述|
|--|--|----|--|
|Listeners|String|是|传入要操作的Listeners的JSON数组串，每个Listener的具体结构描述见[Listener](#)。**说明：** 目前不支持批量删除，每次只允许删除一个对象。

|

|名称|类型|是否必需|描述|
|--|--|----|--|
|InstanceId|String|是|实例ID。|
|Protocol|String|是|协议类型。|
|FrontendPort|Integer|是|前端使用的端口，取值范围：0-65535。|

## 返回参数 { .section}

|名称|类型|描述|
|--|--|--|
|RequestId|String|本次请求的ID。|

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
  "RequestId": "0bcf28g5-d57c-11e7-9bs0-d89d6717dxbc"
}

```

