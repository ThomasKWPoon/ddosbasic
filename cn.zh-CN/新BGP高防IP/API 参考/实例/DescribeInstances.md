# DescribeInstances {#reference1742 .reference}

调用DescribeInstances分页查询新BGP高防实例信息列表。

## 请求参数 {#section_lzw_5s5_jgb .section}

|名称|类型|是否必需|描述|
|--|--|----|--|
|InstanceIds|String|否|通过实例Id查询实例信息，传入要查询的实例Id数组（JSON字符串）。支持精确匹配。例如，\["ddoscoo-cn-XXXX1", "ddoscoo-cn-XXXX2"\]。**说明：** 若传入该参数，则无需传入Ip和Remark。

|
|Ip|String|否|通过实例Ip查询实例信息，传入要查询的实例Ip地址。支持精确匹配查询。**说明：** 若传入该参数，则无需传入InstanceIds和Remark。

|
|Remark|String|否|通过实例备注查询实例信息，传入要查询的实例的备注信息。支持模糊查询。**说明：** 若传入该参数，则无需传入InstanceIds和Ip。

|
|PageNo|Integer|是|分页页号，即从几页开始显示。最小值1。|
|PageSize|Integer|是|分页大小，即每页显示多少条结果。最大值50。|

## 返回参数 { .section}

|名称|类型|描述|
|--|--|--|
|Total|Integer|实例总数。|
|Instances|Instance|实例信息列表。具体结构描述见[instance](#)。|
|RequestId|String|该请求的ID。|

|名称|类型|描述|
|--|--|--|
|InstanceId|String|实例ID。|
|Remark|String|实例备注信息。最大500字节。|
|Status|Integer|实例售卖状态。-   1：正常
-   2：过期
-   3：释放

|
|ExpireTime|Long|过期时间时间戳，单位毫秒。|
|GmtCreate|Long|创建时间时间戳，单位毫秒。|

## 示例 { .section}

**请求示例**

```
{
  "InstanceIds": "[\"0bcf28g5-d57c-11e7-9bs0-d89d6717dxbc\",\"0bcf28g5-d57c-11e7-9bs0-d89d6717dxbc\"]",
  "PageNo": 1,
  "PageSize": 1
}

```

**返回示例**

```
{
  "Total": 1,
  "Instances": [
    {
      "InstanceId": "0bcf28g5-d57c-11e7-9bs0-d89d6717dxbc",
      "Remark": "xxx",
      "Status": 1,
      "ExpireTime": 20384032,
      "GmtCreate": 2308402384
    }
  ],
  "RequestId": "0bcf28g5-d57c-11e7-9bs0-d89d6717dxbc"
}

```

