# ListAsyncTask {#reference2669 .reference}

调用ListAsyncTask查询异步任务列表。

## 请求参数 { .section}

|名称|类型|是否必需|描述|
|--|--|----|--|
|TaskType|Integer|否|要查询的任务类型，取值：-   1：4层转发规则批量导出任务
-   2：7层防护规则批量导出任务
-   3：会话&健康检查配置导出任务
-   4：DDoS防护策略导出任务

**说明：** 若不传入该参数，则返回所有类型的任务。

|
|TaskStatus|Integer|否|要查询的任务状态，取值：-   0：任务初始化
-   1：任务进行中
-   2：任务成功
-   3：任务失败

**说明：** 若不传入该参数，则返回所有状态的任务。

|
|PageNo|Integer|是|当前页数，从1开始。|
|PageSize|Integer|是|分页大小，最大值20。|

## 返回参数 { .section}

|名称|类型|描述|
|--|--|--|
|RequestId|String|本次请求的ID。|
|Total|Integer|域名总数。|
|AsyncTasks|\[\]AsyncTask|任务列表。具体结构描述见[AsyncTask](#)。|

|名称|类型|描述|
|--|--|--|
|TaskId|Long|任务ID，使用该ID可进行任务的删除操作。|
|TaskType|Integer|任务类型，取值：-   1：4层转发规则批量导出任务
-   2：7层防护规则批量导出任务
-   3：会话&健康检查配置导出任务
-   4：DDoS防护策略导出任务

|
|TaskStatus|Integer|任务状态，取值：-   0：任务初始化
-   1：任务进行中
-   2：任务成功
-   3：任务失败

|
|StartTime|Long|任务开始时间戳，单位：毫秒。|
|EndTime|Long|任务结束时间戳，单位：毫秒。|
|TaskParams|TaskParam|任务执行参数，为一个JSONObject类型的字符串，具体结构描述见[TaskParam](#)。|
|TaskResult|TaskResult|任务执行结果，JSONObject类型的字符串，具体结构描述见[TaskResult](#)。|

|名称|类型|描述|
|--|--|--|
|instanceId|String|新BGP高防实例ID。|
|domain|String|用户域名。|

|名称|类型|描述|
|--|--|--|
|instanceId|String|新BGP高防实例ID。|
|url|String|文件下载OSS地址。|

## 示例 { .section}

**请求示例**

```
{
  "TaskType": 1,
  "TaskStatus": 0,
  "PageNo":1,
  "PageSize":10
}

```

**返回示例**

```
{
  "Total": 2,
  "RequestId": "0bcf28g5-d57c-11e7-9bs0-d89d6717dxbc",
  "AsyncTasks": [
  	{
		"TaskId": 1,
	    "TaskType": 1,
	    "TaskStatus": 2,
	    "StartTime": 156927362,
	 	"EndTime": 156927362
	    "TaskParams": "{}", // 四层任务：{"instanceId": "ddoscoo-1234-qrq2134"}，七层任务：{"domain": "www.aliyun.com"}
  	    "TaskResult": "{}" // 四层任务：{"instanceId": "ddoscoo-1234-qrq2134", "url": "https://oss.xxx.xxx"}，七层任务：{"domain": "www.aliyun.com", "url": "https://oss.xxx.xxx"}，会话&健康检查任务：{"instanceId": "ddoscoo-1234-qrq2134", "url": "https://oss.xxx.xxx"}，DDoS防护策略任务：{"instanceId": "ddoscoo-1234-qrq2134", "url": "https://oss.xxx.xxx"}
	}
  ]
}

```

