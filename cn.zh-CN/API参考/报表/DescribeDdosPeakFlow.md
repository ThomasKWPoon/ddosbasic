# DescribeDdosPeakFlow {#reference713 .reference}

调用DescribeDdosPeakFlow接口查询高防Ip的攻击峰值。

## 请求参数 { .section}

|名称|类型|是否必需|描述|
|--|--|----|--|
|StartTime|Long|是|查询开始时间戳，单位为毫秒。|
|EndTime|Long|是|查询结束时间戳，单位为毫秒。|
|Ip|String|是|要查询的高防实例Ip。|

## 返回参数 { .section}

|名称|类型|描述|
|--|--|--|
|RequestId|String|本次请求的ID。|
|PeakFlow|String|攻击峰值，单位为G。|

## 示例 { .section}

**请求示例**

```language-shell
https://ddospro.cn-hangzhou.aliyuncs.com/?Action=DescribeDdosPeakFlow
&StartTime=1536891600
&EndTime=1536893404
&Ip=1.1.1.1
&公共请求参数

```

**返回示例**

-   JSON格式

    ```language-json
    {
    	"RequestId": "C33EB3D5-AF96-43CA-9C7E-37A81BC06A1E",
        "PeakFlow": "8.36"
    }
    
    ```


