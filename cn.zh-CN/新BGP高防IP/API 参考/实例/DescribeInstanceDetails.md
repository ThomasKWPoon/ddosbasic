# DescribeInstanceDetails {#reference1341 .reference}

调用DescribeInstanceDetails查询指定实例的详情信息。

## 请求参数 { .section}

|名称|类型|是否必需|描述|
|--|--|----|--|
|InstanceIds|String|是|要查询的实例ID数组（JSON字符串）。|

## 返回参数 { .section}

|名称|类型|描述|
|--|--|--|
|InstanceDetails|InstanceDetail|实例详情列表。具体结构描述见[InstanceDetail](#)。|
|RequestId|String|本次请求的ID。|

|名称|类型|描述|
|--|--|--|
|InstanceId|String|实例ID。|
|Line|String|实例线路。例如，coop-line-001。|
|\[\]EipInfoList|EipInfo|与该示例绑定的EIP信息列表。具体结构描述见[EipInfo](#)。|

|名称|类型|描述|
|--|--|--|
|Eip|String|EIP值。|
|Status|String|EIP状态。取值：-   normal：正常
-   cleaning：清洗中
-   blackhole：黑洞中

|

## 示例 { .section}

**请求示例**

```
{
  "InstanceIds": "[\"0bcf28g5-d57c-11e7-9bs0-d89d6717dxbc\",\"0bcf28g5-d57c-11e7-9bs0-d89d6717dxbc\"]"
}

```

**返回示例**

```
{
  "InstanceDetails": [
    {
      "InstanceId": "0bcf28g5-d57c-11e7-9bs0-d89d6717dxbc",
      "Line": "coop-line-001",
      "EipInfoList": [
        {
          "Eip": "1.1.1.1",
          "Status": "normal"
        }
      ]
    }
  ],
  "RequestId": "0bcf28g5-d57c-11e7-9bs0-d89d6717dxbc"
}

```

