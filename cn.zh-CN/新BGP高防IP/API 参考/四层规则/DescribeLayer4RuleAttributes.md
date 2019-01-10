# DescribeLayer4RuleAttributes {#reference3712 .reference}

调用DescribeLayer4RuleAttributes查询四层转发属性，包括会话保持和DDoS防护策略。

## 请求参数 { .section}

|名称|类型|是否必需|描述|
|--|--|----|--|
|Listeners|String|是|传入要查询的Listener数组JSON串，每个Listener的具体结构描述见[Listener](#)。|

|名称|类型|是否必需|描述|
|--|--|----|--|
|InstanceId|String|是|实例ID。|
|Protocol|String|是|协议类型。|
|FrontendPort|Integer|是|前端使用的端口，范围：0-65535。|
|BackendPort|Integer|否|后端使用的端口，范围：0-65535。|
|RealServers|Json数组|否|源站IP地址。|
|IsAutoCreate|Boolean|否|是否自动创建。如果是，则不允许删除和修改。|

## 返回参数 { .section}

|名称|类型|描述|
|--|--|--|
|Total|Integer|结果总数。|
|Listeners|String|Listener数组JSON串。具体结构描述见[Listener](#)。|
|RequestId|String|请求ID。|

|名称|类型|描述|
|--|--|--|
|InstanceId|String|实例ID。|
|Protocol|String|协议类型。|
|FrontendPort|Integer|前端使用的端口，范围：0-65535。|
|Config|TcpConfig|TCP配置。具体结构描述见[TcpConfig](#)。|

|名称|类型|描述|
|--|--|--|
|PersistenceTimeout|Integer|会话保持的超时时间，单位为秒。默认为0，表示关闭。|
|Synproxy|String|DDoS防护策略的虚假源，取值：off、on。|
|NodataConn|String|DDoS防护策略的空连接，取值：off、on。|
|Sla|Sla|目的限制配置。具体结构描述见[Sla](#)。|
|Slimit|Slimit|源限制配置。具体结构描述见[Slimit](#)。|
|PayloadLen|PayloadLen|包过滤配置。具体结构描述见[PayloadLen](#)。|

|名称|类型|描述|
|--|--|--|
|Cps|Integer|DDoS防护策略/目的新建连接限速，取值范围：100~100,000。|
|Maxconn|Integer|DDoS防护策略/目的并发连接限速，取值范围：1,000~1,000,000。|
|CpsEnable|Integer|是否启用Cps，取值：-   0：禁用cps
-   1：启用cps（默认）

|
|MaxconnEnable|Integer|是否启用Maxconnection，取值：-   0：禁用maxconn
-   1：启用maxconn（默认）

|

|名称|类型|描述|
|--|--|--|
|Cps|Integer|DDoS防护策略/源新建连接限速，取值范围：100~100,000。|
|Maxconn|Integer|DDoS防护策略/源并发连接限速，取值范围：1,000~1,000,000。|
|CpsEnable|Integer|是否启用Cps，取值：-   0：禁用cps
-   1：启用cps（默认）

|
|MaxconnEnable|Integer|是否启用Maxconnection，取值：-   0：禁用maxconn
-   1：启用maxconn（默认）

|

|名称|类型|描述|
|--|--|--|
|Min|Integer|DDoS防护策略/包长度过滤，包长度的最小值。|
|Max|Integer|DDoS防护策略/包长度过滤，包长度的最大值。|

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
  "Total": 1,
  "Listeners": [
    {
      "InstanceId": "0bcf28g5-d57c-11e7-9bs0-d89d6717dxbc",
      "Protocol": "tcp",
      "FrontendPort": 80,
      "Config": {
        "PersistenceTimeout": 80,
        "Synproxy": "off",
		"NodataConn": "on",
        "Sla": {
          "Cps": 10,
          "Maxconn": 10,
		  "CpsEnable": 1,
		  "MaxconnEnable": 1
        },
        "Slimit": {
          "Cps": 10,
          "Maxconn": 10,
		  "CpsEnable": 1,
		  "MaxconnEnable": 1
        },
        "PayloadLen": {
          "Min": 1,
          "Max": 2
        }
      }
    }
  ],
  "RequestId": "0bcf28g5-d57c-11e7-9bs0-d89d6717dxbc"
}

```

