# DescribeInstanceSpecs {#reference1220 .reference}

调用DescribeInstanceSpecs查询指定实例的规格。

## 请求参数 { .section}

|名称|类型|是否必需|描述|
|--|--|----|--|
|InstanceIds|String|是|要查询的实例ID数组（JSON字符串）。|

## 返回参数 { .section}

|名称|类型|描述|
|--|--|--|
|InstanceSpecs|InstanceSpec|实例规格列表。具体结构描述见[InstanceSpec](#)。|
|RequestId|String|本次请求的ID。|

|名称|类型|描述|
|--|--|--|
|InstanceId|String|实例ID。|
|BaseBandwidth|Integer|基础带宽值。|
|ElasticBandwidth|Integer|弹性带宽值。|
|PortLimit|Integer|最大4层转发次数。|
|DomainLimit|Integer|最大域名个数。|
|BandwidthMbps|Integer|业务带宽值。|

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
  "InstanceSpecs": [
    {
      "InstanceId": "0bcf28g5-d57c-11e7-9bs0-d89d6717dxbc",
      "BaseBandwidth": 20,
      "ElasticBandwidth": 10,
      "PortLimit":10,
      "DomainLimit": 20,
      "BandwidthMbps": 100
    }
  ],
  "RequestId": "0bcf28g5-d57c-11e7-9bs0-d89d6717dxbc"
}

```

