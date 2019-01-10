# DescribeDDoSEvents {#reference1469 .reference}

调用DescribeDDoSEvents查询指定IP的DDoS攻击事件。

## 请求参数 { .section}

|名称|类型|是否必需|描述|
|--|--|----|--|
|Eip|String|是|要查询的EIP地址。|
|StartTime|Long|是|流量查询的开始时间戳，单位：秒。|
|EndTime|Long|是|流量查询的结束时间戳，单位：秒。|
|Offset|Integer|是|返回结果开始位置，即从几个结果开始返回。**说明：** 若不传入该参数，则从第0个结果开始返回。

|
|PageSize|Integer|是|分页大小，即每页显示的结果个数。最大值50。|

## 返回参数 { .section}

|名称|类型|描述|
|--|--|--|
|Total|Integer|结果总数。|
|Events|DDoSEvent|DDoS攻击事件。具体结构描述见[DDoSEvent](#)。|
|RequestId|String|本次请求的ID。|

|名称|类型|描述|
|--|--|--|
|StartTime|Long|事件开始时间。|
|EndTime|Long|事件结束时间。|
|Interval|Integer|事件持续时间，单位：秒。|
|Status|String|事件状态，取值：-   blackhole\_start：黑洞中
-   blackhole\_end：黑洞结束
-   defense\_start：清洗中
-   defense\_end：清洗结束

|

## 示例 { .section}

**请求示例**

```
{
  "Eip": "1.1.1.1",
  "StartTime": 3289457324,
  "EndTime": 3289457398,
  "Offset": 0,
  "PageSize": 10
}

```

**返回示例**

```
{
  "Total": 1,
  "Events": [
    {
      "StartTime": 3289457324,
      "EndTime": 3289457398,
      "Interval": 12,
      "Status": "blackhole_end"
    }
  ],
  "RequestId": "0bcf28g5-d57c-11e7-9bs0-d89d6717dxbc"
}

```

