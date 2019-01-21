# ListCcCustomedRule {#doc_api_949228 .reference}

调用ListCcCustomedRule接口查询用户的自定义CC规则。

## 调试 {#apiExplorer .section}

单击[这里](https://api.aliyun.com/#product=DDoSPro&api=ListCcCustomedRule)在OpenAPI Explorer中进行可视化调试，并生成SDK代码示例。

## 请求参数 {#parameters .section}

|名称|类型|是否必选|示例值|描述|
|--|--|----|---|--|
|CurrentPage|Integer|否|1|分页页号，最小值为**1**。

 |
|Domain|String|否|ww.aliyun.com|要查询的域名。

 |
|PageSize|Integer|否|10|分页大小，最大值为**10**。

 |

## 返回参数 {#resultMapping .section}

|名称|类型|示例值|描述|
|--|--|---|--|
|RequestId|String|CF33B4C3-196E-4015-AADD-5CAD00057B80|本次请求的ID。

 |
|RuleList| | |自定义CC规则列表。

 |
|└BlockingTime|Integer|60|阻断时间，单位为秒，取值范围：60~86,400。

 |
|└BlockingType|String|captcha|阻断类型，取值：

 -   **captcha**：人机识别
-   **close**：封禁

 |
|└Interval|Integer|5|检测时长，单位为秒，取值范围：5~10,800。

 |
|└MatchingRule|String|prefix|匹配规则，取值：

 -   **prefix**：前缀模式
-   **match**：完全匹配

 |
|└Name|String|customedCcRule1|自定CC规则名称。

 **说明：** 您可以通过该名称找到对应规则，并进行修改、删除操作。

 |
|└Uri|String|/a/b/c|防护路径。

 |
|└VisitCount|Integer|200|允许的单一IP访问次数，取值范围：2~2,000。

 |
|TotalCount|Integer|10|规则总数。

 |

## 示例 {#demo .section}

请求示例

``` {#request_demo}

https://ddospro.cn-hangzhou.aliyuncs.com/?Action=ListCcCustomedRule
&Domain=www.aliyun.com
&CurrentPage=1
&PageSize=10
&公共请求参数

```

正常返回示例

`XML` 格式

``` {#xml_return_success_demo}
<root>
  <RequestId>C33EB3D5-AF96-43CA-9C7E-37A81BC06A1E</RequestId>
  <RuleList>
    <Rule>
      <element>
        <BlockingTime>7380</BlockingTime>
        <BlockingType>close</BlockingType>
        <Interval>123</Interval>
        <MatchingRule>match</MatchingRule>
        <Name>testttt</Name>
        <Uri>/a/a/a</Uri>
        <VisitCount>123</VisitCount>
      </element>
    </Rule>
  </RuleList>
  <TotalCount>3</TotalCount>
</root>

```

`JSON` 格式

``` {#json_return_success_demo}
{
	"RuleList":{
		"Rule":[
			{
				"Name":"testttt",
				"BlockingType":"close",
				"VisitCount":123,
				"Interval":123,
				"BlockingTime":7380,
				"Uri":"/a/a/a",
				"MatchingRule":"match"
			}
		]
	},
	"TotalCount":3,
	"RequestId":"C33EB3D5-AF96-43CA-9C7E-37A81BC06A1E"
}
```

## 错误码 { .section}

[查看本产品错误码](https://error-center.aliyun.com/status/product/DDoSPro)

