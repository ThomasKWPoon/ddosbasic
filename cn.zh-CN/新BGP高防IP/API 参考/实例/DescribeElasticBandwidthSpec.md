# DescribeElasticBandwidthSpec {#reference550 .reference}

调用DescribeElasticBandwidthSpec查询指定实例的弹性带宽规格。

## 请求参数 { .section}

|名称|类型|是否必需|描述|
|--|--|----|--|
|InstanceId|String|是|要查询的实例ID。单次请求只支持查询1个实例。|

## 返回参数 { .section}

|名称|类型|描述|
|--|--|--|
|RequestId|String|本次请求的ID。|
|ElasticBandwidthSpec|Integer数组|弹性带宽规格。|

## 示例 { .section}

**请求示例**

```
{
  "InstanceId": "0bcf28g5-d57c-11e7-9bs0-d89d6717dxbc"
}

```

**返回示例**

```
{
  "ElasticBandwidthSpec": [5,10,20,30],
  "RequestId": "0bcf28g5-d57c-11e7-9bs0-d89d6717dxbc"
}

```

