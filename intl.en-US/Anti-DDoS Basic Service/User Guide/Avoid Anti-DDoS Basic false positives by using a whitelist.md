# Avoid Anti-DDoS Basic false positives by using a whitelist {#task670 .task}

In some situations, you may find that some normal traffic is blocked by Anti-DDoS Basic \(such as normal website service access\).

For example, in an NAT network environment \(hosts in the LAN share an Internet IP address for Internet access\), some hosts in the LAN infected by a virus or suffering intrusion may attack an ECS server. In this situation, once Alibaba Cloud Security acknowledges the attacks, it blocks the shared Internet IP address of the NAT, resulting to an access failure.

However, you can set a whitelist in the Alibaba Cloud Security Control platform to avoid such false positives.

1.  Log on to the [Alibaba Cloud Security Control console](https://partners-intl.console.aliyun.com/#/sc). 

    **Note:** You can also hover your mouse on the account icon in the upper-right corner of Alibaba Cloud console and click **Security Control** to open it.

2.  Go to **Whitelist** \> **Access Whitelist**, click **Add**. 
3.  Select the Object Type, and enter the Source IP \(not the IP belongs to your current Alibaba Cloud account\). Then, select object IPs of your current account from the list on the left side \(for example, select a public IP of your ECS instance\), click the right arrow button to add the selected IPs to the list on the right side, and click **OK**. Thus, the specified source IP is added to the access whitelist of the selected object IPs, and all accesses from the source IP to the object IPs are not restricted by Alibaba Cloud Security Control platform. 

    **Note:** To allow accesses from all IPs to the object IP, enter 0.0.0.0 in the **Source IP** field.

    After setting the whitelist, all accesses to the target host asset from the source IP in the access whitelist are not restricted by any Alibaba Cloud security controls, even if the access may be risky. Therefore, set the access whitelist carefully.

    **Note:** After the source IP is added to the access whitelist, it takes effect within 10 minutes.


