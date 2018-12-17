# Disable traffic scrubbing {#task370 .task}

Alibaba Cloud servers enjoys a free DDoS mitigation capacity by default. When they are targeted by traffic attacks, the traffic scrubbing service is activated automatically. The traffic scrubbing service consists of three units: detecting center, cleaning center, and centralized management center.

The detecting center monitors data traffic flowing into the cloud server, and identifies abnormal traffic in a timely manner, such as DDoS attack. When an abnormity is detected, the management center guides the scrubbing center to clean suspicious traffic based on the traffic diversion policy. Malicious traffic is removed, while legitimate traffic is returned to the original instance. This ensures only legitimate traffic can be forwarded to the target system.

You can manually cancel traffic scrubbing for instance IP in the abnormal status.

**Note:** One account can manually disable traffic scrubbing for three times in one day.

1.  Log on to the [Anti-DDoS Basic console](https://partners-intl.console.aliyun.com/#/ddosnext). 
2.  Select a region. 
3.  Select ECS, Server Load Balancer, or EIP \(including NAT\), and locate to the instance IP that is in the cleaning status, and click **View Details**. 
4.  Click **Cancel Cleaning**. 

