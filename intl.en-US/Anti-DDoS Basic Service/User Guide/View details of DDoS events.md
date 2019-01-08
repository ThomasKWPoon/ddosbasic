# View details of DDoS events {#task395 .task}

When the public IP of an ECS or SLB instance is under a massive DDoS attack, and its traffic exceeds the corresponding black hole threshold, the IP is then black-holed, which leads to server unavailability.

**Note:** The black hole threshold values of instances may vary across regions. For more information, see [Alibaba Cloud black hole policies](../../../../../reseller.en-US/DDoS Protection Guide/Basic Concepts/Alibaba Cloud black hole policies.md#).

In this situation, you can view details of the DDoS event and know the reason as to why the IP was black-holed in the Alibaba Cloud Anti-DDoS Basic console.

1.  Log on to the [Anti-DDoS Basic console](https://partners-intl.console.aliyun.com/#/ddosnext). 
2.  Select the region. 
3.  On the **Anti-DDoS Basic** \> **Instances**page, select the instance type tab: **ECS**, **SLB**, or **EIP\( including NAT\)**. 
4.  In the instance list, locate to the target instance, whose **Status** is **Black hole activated**, and click **Details**. 

    **Note:** You can search for target instances by **Instance ID**, **Instance Name**, and **Instance IP**.

5.  View details of the DDoS event, including current mitigation capacity, start time, and peak traffic. 

