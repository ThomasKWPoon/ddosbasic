# How to migrate the service from the original Anti-DDoS Pro instance to a new one? {#task428 .task}

This topic describes the procedure to migrate your service to a new instance without experiencing any service interruption. This generally happens when your original Anti-DDoS Pro instance expires and you have a new Anti-DDoS Pro instance.

1.  Log on to the [Anti-DDoS Pro console](https://partners-intl.console.aliyun.com/#/ddospro). 
2.  Go to the **Access** \> **Web Service** page. 
3.  Locate the target domain name, and click **Origin Edit** under **Domain Info** of the target domain name. 
4.  Click **Edit IP** in the Operation column. 
5.  In the Edit IP dialog box, select the Instance and Anti-DDoS IP to enable for the target domain name. You can click the corresponding **ON** button to apply the current domain name configuration to that IP. 
6.  Click **OK**. When the domain name configuration is effective, both the original and the new Anti-DDoS Pro instances become available. 
7.  Disable the Anti-DDoS IP of the original Anti-DDoS Pro instance on the Origin Edit page, and then remove that Anti-DDoS IP in the Edit IP dialog box by clicking the corresponding OFF button. 

