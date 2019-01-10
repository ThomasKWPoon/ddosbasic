# DescribeDDoSTraffic {#reference1370 .reference}

调用DescribeDDoSTraffic查询指定IP的DDoS攻击流量信息。

## 请求参数 { .section}

|名称|类型|是否必需|描述|
|--|--|----|--|
|Eip|String|是|要查询的EIP地址。|
|StarTime|Long|是|开始时间戳，单位：秒。|
|EndTime|Long|是|结束时间戳，单位：秒。|
|Interval|Integer|是|采样间隔，单位：秒。必须是60秒的倍数，默认60s。返回结果可缩放。|

## 返回参数 { .section}

|名称|类型|描述|
|--|--|--|
|DefenseInBytes|Integer|清洗流量，单位：byte。|
|SourceInBytes|Integer|回源流量，单位：byte。|
|DDoSTrafficPoints|DDoSTrafficPoint|各时间点攻击流量信息。具体结构描述见[DDoSTrafficPoint](#)。|
|RequestId|String|本次请求的ID。|

|名称|类型|描述|
|--|--|--|
|Time|Long|时间点（时间戳），单位：秒。|
|DefenseMaxInBps|Integer|该时间点的攻击流量，单位：bps。|
|SourceMaxInBps|Integer|该时间点的总流量，单位：bps。|

## 示例 { .section}

**请求示例**

```
{
  "Eip": "1.1.1.1",
  "StarTime": 3289457324,
  "EndTime": 3289457398,
  "Interval": 60
}

```

**返回示例**

```
{
  "DefenseInBytes": 23482234,
  "SourceInBytes": 19284762,
  "DDoSTrafficPoints": [
    {
      "Time": 234082304,
	  "DefenseMaxInBps": 129867,
	  "SourceMaxInBps": 129867,
    }
  ],
  "RequestId": "0bcf28g5-d57c-11e7-9bs0-d89d6717dxbc"
}

```

