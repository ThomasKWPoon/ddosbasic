# Security group rule misconfiguration results into access exceptions {#concept_53137_zh .concept}

You can configure Non-Web Service of Anti-DDoS Pro for an origin site of Alibaba Cloud ECS or VPC. However, if the rule “Only allow Anti-DDoS Pro IP addresses, and block all other IP addresses” exists in the ECS/VPC security group, it can block the real IP address of the client.

## Analysis { .section}

The latest security group version can obtain the visitors’ real IP addresses. Therefore, the “only allow/deny all” access rule can disturb the normal access traffic.

## Resolution { .section}

Modify the ECS security group rules based on visitors’ real IP addresses.

## Example { .section}

Assume that a complete access process is as follows: Client \(real IP address: 1.1.1.1\) \> Anti-DDoS Pro \(Back-to-source IP address: 2.2.2.2\) \> ECS

If you have set the rule in ECS security group to only allow IP address 2.2.2.2, then you must delete this rule. In addition, you have to decide whether to allow certain real client IP addresses based on your actual situation.

