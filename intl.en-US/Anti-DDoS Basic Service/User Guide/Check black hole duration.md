# Check black hole duration {#task512 .task}

When your server suffers massive DDoS attacks and the black hole mechanism is triggered, the public IP of the server is banned for a certain time period based on the security credibility of the server.

The default black hole duration is 2.5 hours and the IP cannot be unbanned during this period. The actual black hole duration depends on the attack situation and may range from 30 minutes to 24 hours. The duration of the black hole is mainly influenced by the following factors:

-   Whether the attack persists. The black hole duration keeps extending, if the attack continues. The black hole duration is re-calculated from the time of extension.
-   Whether the attack is frequent. If a user is attacked for the first time, the black hole duration will be automatically shortened. On the contrary, the black hole duration for a user under frequent attacks will be automatically extended as the user is more likely to be attacked again.

You can log on to the Anti-DDoS Basic console to view the specific black hole threshold and duration.

**Note:** 

-   For users suffering overly frequent black holes, Alibaba Cloud reserves the right to extend the black hole duration and reduce the black hole threshold.
-   Black hole is a service provided by Internet service providers \(ISPs\) and ISPs have a clear black hole disabled time limit. Thus, in general, the black hole duration is no less than 30 minutes, and the specific black hole duration of your account is automatically adjusted according to the security credibility of your account.

1.  Log on to the [Anti-DDoS Basic console](https://partners-intl.console.aliyun.com/#/ddosnext). 
2.  On the **Anti-DDoS Basic** \> **Instances** page, make sure that the **Why is the IP address abnormal?** switch in the upper-right corner is turned on. 
3.  Hover your mouse over the **Blackholing** icon to check the current black hole duration.![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/79454/154503690534165_en-US.png)

 

