# ECS stress test guide {#concept_40041_zh .concept}

Alibaba Cloud Security Anti-DDoS Basic provides defense against DDoS attacks. By default, when the public traffic exceeds 180 MB per second, 30,000 messages per second, or 480 HTTP requests per second on an ECS server, Anti-DDoS Basic automatially starts traffic scrubbing to protect the ECS server.

Therefore, before you start the stress testing on an ECS server, you have to adjust the cleaning trigger value to an appropriate value in the [Alibaba Cloud Anti-DDoS Basic console](https://partners-intl.console.aliyun.com/#/ddosnext). For more information, view [Set the cleaning trigger value](reseller.en-US/Anti-DDoS Basic Service/User Guide/Set the cleaning trigger value.md#).

**Note:** We recommend that you do not set the increasing pace per minute to exceed 100 times during the stress test.

