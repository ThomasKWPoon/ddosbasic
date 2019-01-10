# Configure a multi-line Anti-DDoS Pro instance to pass traffic back to multiple origin sites {#task851 .task}

In cases where compliance or high availability is required, you can deploy a multi-line Anti-DDoS Pro instance to pass traffic back to different origin sites, based on the type of line. For example, you can enable the China Telecom line of your Anti-DDoS Pro instance for a China Telecom origin, and the China Unicom line for a China Unicom origin. This topic describes the configuring method in the Anti-DDoS console.

If your domain name is not connected to an Anti-DDoS Pro instance, follow [HTTP website access](reseller.en-US/Anti-DDoS Pro Service/Quick Start/Web service/Step 1. Set up HTTP protection.md#) or [HTTPS website access](reseller.en-US/Anti-DDoS Pro Service/Quick Start/Web service/(Optional) Step 1: Set up HTTPS protection.md#) to connect your domain name to Anti-DDoS Pro.

**Note:** We recommend that you familiarize yourself with the configuration procedure, before performing the actual configuration and only do so during off-peak hours.

1.  Log on to the [Anti-DDoS Pro console](https://partners-intl.console.aliyun.com/#/ddospro) and go to the **Access** \> **Web Service** page. 
2.  Locate the target domain name, and then click **Origin Edit** under **Domain Info**. 
3.  Disable certain lines for the current origin. 
    1.  On the **Anti-DDoS IP/Domain Resolution Switch** column, toggle off one or more lines. For example, if you want to only use the BGP lines for domain name resolution for the current origin, you can disable the China Telecom and China Unicom lines. 
    2.  Click **Edit IP** in the Operation list. 
    3.  On the Edit IP page, click **OFF** to disable certain lines, for which you have toggled domain name resolution off. In this case, disable China Telecom and China Unicom lines. 
    4.  Click **OK** to go back to the Origin Edit page. When completing the configuration, you can find that the China Telecom and China Unicom lines are removed in the Anti-DDoS IP/Domain Resolution Switch column. 
4.  Add a new origin and enable other lines for it. 
    1.   On the Origin Edit page, click **Add**. For example, you can add a China Telecom origin, and enable the China Telecom line for it. 
    2.   Select the Origin site IP mode and enter an IP address. Click ON under the China Telecom line. Click **OK**. 
    3.  With the preceding configuration, your Anti-DDoS Pro instance’s China Telecom line directs requests back to the newly added China Telecom origin. 
5.  Follow Step 4 to configure other lines of your Anti-DDoS Pro instance for the corresponding origins. Make sure that different lines are enabled for their corresponding origins. 

