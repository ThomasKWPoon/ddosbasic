# Cancel traffic scrubbing {#task370 .task}

Alibaba Cloud servers enjoy a free DDoS mitigation capacity by default. When they are targeted by traffic attacks, the traffic scrubbing service is activated automatically. The traffic scrubbing service consists of three units: detecting center, cleaning center, and centralized management center.

The detecting center monitors data traffic flowing into the cloud server, and identifies abnormal traffic in a timely manner, such as DDoS attack. When an abnormity is detected, the management center guides the scrubbing center to clean suspicious traffic based on the traffic diversion policy. Malicious traffic is removed, while legitimate traffic is returned to the original instance. This ensures only legitimate traffic can be forwarded to the target system.

You can manually cancel traffic scrubbing for instance IP in the abnormal status.

**Note:** One account can manually disable traffic scrubbing for three times in one day.

1.  Log on to the [Anti-DDoS Basic console](https://partners-intl.console.aliyun.com/#/ddosnext). 
2.  Select the region. 
3.  Select the instance type tab, locate the instance IP that is in the scrubbing status, and then click the instance IP to open the **Instance Details** dialog box. 

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/79453/154814185737787_en-US.png)

4.  In the DDoS event list, select the event that is in the **Scrubbing** status, and click **Cancel Cleaning**. 

    **Note:** Click **Download** to download the captured traffic data file as evidence for you to report this event to the network supervision department.


