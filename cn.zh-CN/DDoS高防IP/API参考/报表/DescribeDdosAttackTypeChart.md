# DescribeDdosAttackTypeChart {#doc_api_949116 .reference}

调用DescribeDdosAttackTypeChart接口查询高防IP的攻击类型概览图表。

## 调试 {#apiExplorer .section}

单击[这里](https://api.aliyun.com/#product=DDoSPro&api=DescribeDdosAttackTypeChart)在OpenAPI Explorer中进行可视化调试，并生成SDK代码示例。

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|EndTime|Long|是|1536891600|查询结束时间戳，单位为毫秒。

 |
|Ip|String|是|1.1.1.1|要查询的高防实例IP。

 |
|StartTime|Long|是|1536893404|查询开始时间戳，单位为毫秒。

 |

## 返回参数 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|AttckCount|Integer|6|攻击种类个数。

 |
|AttckType|String|udp-flood|攻击种类，取值：

 -   **tcp-flood**
-   **udp-flood**
-   **icmp-flood**
-   **finrst-flood**

 |
|DropCount|Integer|405322|清洗包大小，单位为Kbps。

 |
|DropType|String|udp|清洗的攻击种类。

 |
|RequestId|String|C33EB3D5-AF96-43CA-9C7E-37A81BC06A1E|本次请求的ID。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}

https://ddospro.cn-hangzhou.aliyuncs.com/?Action=DescribeDdosAttackTypeChart
&StartTime=1536891600
&EndTime=1536893404
&Ip=1.1.1.1
&<公共请求参数>

```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<DescribeDdosAttackTypeChart>
  <RequestId>C33EB3D5-AF96-43CA-9C7E-37A81BC06A1E</RequestId>
  <AttackCount>6</AttackCount>
  <AttackType>syn-flood</AttackType>
  <DropCount>405322</DropCount>
  <DropType>syn</DropType>
</DescribeDdosAttackTypeChart>

```

`JSON` 格式

``` {#json_return_success_demo}
{
	"AttackType":"udp-flood",
	"DropType":"udp",
	"DropCount":405322,
	"AttackCount":6,
	"RequestId":"C33EB3D5-AF96-43CA-9C7E-37A81BC06A1E"
}
```

## 错误码 { .section}

[查看本产品错误码](https://error-center.aliyun.com/status/product/DDoSPro)

