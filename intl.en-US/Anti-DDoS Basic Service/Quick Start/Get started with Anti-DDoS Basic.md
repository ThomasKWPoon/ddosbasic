# Get started with Anti-DDoS Basic {#task1560 .task}

Alibaba Cloud Anti-DDoS Basic is enabled and initialized by default with the creation of ECS, Server Load Balance, or EIP instances. This service provides a 5 Gbps mitigation capacity free of charge.

In Alibaba Cloud Security Anti-DDoS Basic console, you can take the following operations:

-   Set **Cleaning Trigger Value**. When the IP suffers DDoS attack and the attack bandwidth exceeds the cleaning threshold, Alibaba starts to scrub the flow automatically to guarantee your business availability.
-   Check **Protection Threshold**. The protection threshold consists of Basic protection threshold and Elastic protection threshold.
    -   If the attack bandwidth is below the basic protection threshold, the attack traffic can be scrubbed for free. The [Default Basic Protection Threshold](reseller.en-US/Anti-DDoS Basic Service/User Guide/Anti-DDoS Basic black hole threshold.md#) varies according to the regions of your IP addresses.
    -   When the attack bandwidth is between the basic protection threshold and the elastic protection threshold, the available protection traffic that Alibaba Cloud provides for free is consumed. The elastic protection threshold is determined by your IP address, traffic consumption, and security credibility. After all of the free-of-charge protection traffic is consumed, the protection threshold decreases to the basic protection threshold. [Learn more](reseller.en-US/Anti-DDoS Basic Service/FAQ/Anti-DDoS Basic FAQ.md#).

1.  Log on to the [Anti-DDoS Basic console](https://partners-intl.console.aliyun.com/#/ddosnext). 
2.  Select the region. 
3.  On the **Anti-DDoS Basic** \> **Instances** page, select the **ECS**, **SLB**, or **EIP\( including NAT\)** instance type tab. 
4.  In the instances list, select the instance to be operated.![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/79450/154814205434162_en-US.png)

 
    -   Click the instance IP to view traffic and packet trends over the last 7 days, and DDoS attack events.

        ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/79450/154814205434075_en-US.png)

    -   In the **Instance Details** dialog box, click **Cleaning Settings**. Now, you can choose to manually set the cleaning threshold or use the system default cleaning threshold.

        ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/79450/154814205434074_en-US.png)

5.  View the DDoS attack protection information. Turn on the **DDoS Attack Protection Information** switch on the upper-right corner, to view the following information:![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/79450/154814205434160_en-US.png)

 
    -   View the currently available protection traffic.

        **Note:** Click **Protection Traffic** to view the elastic protection traffic consumption details over the last 30 days.

        ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/79450/154814205434077_en-US.png)

    -   View the current security credibility score.

        **Note:** Click **Security Credibility** to see the security score details.

        ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/79450/154814205534078_en-US.png)

        With a higher credibility score, you can get more extra DDoS mitigation capacity. We recommend that you learn the credibility score policy and maintain a better credibility score.

    -   View the current blackhole duration time.

        **Note:** Click **Blackholing** to view detailed information about the Alibaba Cloud blackhole strategy.


