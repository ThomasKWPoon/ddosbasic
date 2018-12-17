# Set the cleaning trigger value {#task584 .task}

Alibaba Cloud Security Anti-DDoS Basic mitigates SYN flood, UDP flood, ACK flood, ICMP flood, and DNS flood DDoS attacks. To set the cleaning trigger value in Anti-DDoS Basic, follow these steps:

1.  Log on to the [Anti-DDoS Basic console](https://partners-intl.console.aliyun.com/#/ddosnext). 
2.  Select a region. 
3.  On the **Anti-DDoS Basic** \> **Instances**page, select the instance type tab: **ECS**, **SLB**, or **EIP\( including NAT\)**. 
4.  Locate to the instance to be operated. 

    **Note:** You can search for target instances by **Instance ID**, **Instance Name**, and **Instance IP**.

5.  Click **Cleaning Settings** to configure the cleaning threshold value setting for the IP. 
6.  In the Cleaning Settings dialog box, select the cleaning threshold mode: .**Default** or **Manual setting**. ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/79452/154503687934126_en-US.png)

 
    -   **Default**: Anti-DDoS Basic service dynamically adjusts the cleaning threshold value based on the traffic load status.
    -   **Manual setting**: You can select the traffic and packet threshold values manually. When traffic exceeds this threshold value, Anti-DDoS Basic traffic cleaning is triggered. \( We recommend that you adjust the cleaning threshold value appropriately when your website has some promotion activities.\)

        **Note:** The cleaning threshold value can be a bit bigger than the actual access traffic value. If the threshold value is too big, it is not effective on DDoS attacks defense; if the threshold value is too small, the normal access can be affected due to the unexpected traffic cleaning.

        When traffic to an IP reaches the cleaning threshold value, you can view the cleaning information in the Alibaba Cloud Security Anti-DDoS Basic console. If normal access requests are affected, you can cancel the traffic cleaning and adjust the cleaning threshold value appropriately.


