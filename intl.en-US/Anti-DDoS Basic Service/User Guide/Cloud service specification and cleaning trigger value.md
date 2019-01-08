# Cloud service specification and cleaning trigger value {#concept_94178_zh .concept}

Alibaba Cloud provides basic DDoS protection capabilities to help mitigate DDoS attacks on cloud products open to the public network. When the network traffic of the public IP address of the cloud product exceeds the specified cleaning threshold, the traffic to this IP is automatically scrubbed to protect your normal service from DDoS attacks.

For more information about traffic scrubbing, see [Traffic scrubbing, black hole, and threshold value](../../../../../reseller.en-US/DDoS Protection Guide/Basic Concepts/Traffic scrubbing and black hole.md#).

The maximum cleaning threshold supported for each Alibaba cloud service depends on the specifications of the instance. When you create or change an ECS or SLB instance, the system automatically adjusts the maximum cleaning threshold based on the current instance specification.

**Note:** The actual black hole threshold for each instance IP is calculated based on factors such as maximum cleaning threshold and security credibility score.

-   For the specific calculation method of the maximum cleaning threshold of ECS instances, see [Basic DDoS Protection for ECS](../../../../../reseller.en-US/Product Introduction/Network and security/Anti-DDoS Basic.md#).
-   For the specific calculation method of the maximum cleaning threshold of SLB instances, see [Basic DDoS Protection for SLB](../../../../../reseller.en-US/User Guide/Anti-DDoS Basic.md#).

