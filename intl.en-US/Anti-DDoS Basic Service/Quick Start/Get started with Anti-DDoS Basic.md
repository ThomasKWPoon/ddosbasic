# Get started with Anti-DDoS Basic {#task1560 .task}

Alibaba Cloud Anti-DDoS Basic is enabled and initialized by default with the creation of ECS, Server Load Balance, or EIP instances. This service provides a 5 Gbps mitigation capacity free of charge.

In Alibaba Cloud Security Anti-DDoS Basic console, you can take the following operations:

-   Set **Cleaning Trigger Value**. When the IP suffers DDoS attack and the attack bandwidth exceeds the cleaning threshold, Alibaba starts to scrub the flow automatically to guarantee your business availability.
-   Check **Protection Threshold**. The protection threshold consists of Basic protection threshold and Elastic protection threshold.
    -   If the attack bandwidth is below the basic protection threshold, the attack traffic can be scrubbed for free. The [Default Basic Protection Threshold](reseller.en-US/Anti-DDoS Basic Service/User Guide/Anti-DDoS Basic black hole threshold.md#) varies according to the regions of your IP addresses.
    -   When the attack bandwidth is between the basic protection threshold and the elastic protection threshold, the available protection traffic that Alibaba Cloud provides for free is consumed. The elastic protection threshold is determined by your IP address, traffic consumption, and security credibility. After all of the free-of-charge protection traffic is consumed, the protection threshold decreases to the basic protection threshold. [Learn more](reseller.en-US/Anti-DDoS Basic Service/FAQ/Anti-DDoS Basic FAQ.md#).

1.  Log on to the [Anti-DDoS Basic console](https://partners-intl.console.aliyun.com/#/ddosnext). 
2.  Select a region. 
3.  On the **Anti-DDoS Basic** \> **Instances**page, select the instance type tab: **ECS**, **SLB**, or **EIP\( including NAT\)**. 
4.  Select the instance, check the current Cleaning Trigger Value and Current Protection Threshold.![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/79450/154503682734162_en-US.png)

 
    -   Click **Cleaning Settings** to change the cleaning threshold mode to Default or Manual setting. For the Default mode, the system dynamically adjusts the cleaning threshold value based on traffic load. For the Manual setting mode, you can select the cleaning threshold value according to your business requirements.

        ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/79450/154503682734074_en-US.png)

    -   Click **Report** to view the traffic and packets trend of this instance and the DDoS event details.

        ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/79450/154503682734075_en-US.png)

5.  View IP exception descriptions When the **Why is the IP address abnormal?** switch is turned on, you can view the information about protection traffic, security credibility score, and automatic blackhole deactivation time.![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/79450/154503682734160_en-US.png)

 
    -   Hover your mouse on the **Protection Traffic** icon to check your available protection traffic. Additionally, you can click **Protection Traffic** to see the elastic protection traffic consumption details.

        ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/79450/154503682734077_en-US.png)

    -   Hover your mouse on the **Security Credibility** icon to check your security credit score. Additionally, you can click **Security Credibility** to see the security credit details.

        ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/79450/154503682734078_en-US.png)

        With a higher credibility score, you can get more extra DDoS mitigation capacity. We recommend that you learn the credibility score policy and maintain a better credibility score.

    -   Hover your mouse on the **Blackholing** icon to check your blackhole deactivation time.

