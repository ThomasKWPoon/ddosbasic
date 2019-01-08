# Add website to Anti-DDoS Premium for protection {#task1814 .task}

After purchasing an Anti-DDoS Premium instance, you can add your website domain to the instance for DDoS protection.

1.  Log on to the [Anti-DDoS Premium Service console](https://yundun.console.aliyun.com/?p=ddosdip). 
2.  Go to **Provisioning** \> **Website** page, and click **Add Website.**  
3.  On the Website configuration page, enter information for the website to be protected, and then click **Add Website**. 

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/79670/154692905035231_en-US.png)

    |Parameter|Description|Note|
    |---------|-----------|----|
    |Website domain|Domain of the website to be protected.|Top-level and second-level domains are supported. Additionally, wild-card domains are also supported, and the system automatically matches all second-level domain names of the wild-card domain.|
    |Protocol|Protocols supported by the website.|If your website supports https or websockets encryption authentication, you can check the HTTPS or Websockets protocol and upload the corresponding certificate and private key after adding the web site configuration.|
    |Origin server|Origin server of the website.|After adding the website to the Anti-DDoS Premium instance, the system forwards clean traffic back to the origin server that you specified.    -   **\(Recommended\)** Select **IP**, and input the origin server IP \(For example, you can input a public IP of an ECS or SLB instance\). Then, the Anti-DDoS Premium instance forwards traffic to the origin server IP after the configuration.

**Note:** You can set up to 20 origin server IPs. If multiple origin IPs are set, the system polls these IPs by IP-Hash to realize load balancing.

    -   Select **Domain**, and input the origin server domain \(For example, you can input a CNAME of an OSS bucket\). Then, the Anti-DDoS Premium instance forwards traffic to the origin server domain after the configuration.

**Note:** The origin server domain must not be the same as the website domain to be protected.

|
    |Origin server ports|Ports of the website origin server. The Anti-DDoS Premium instance forwards clean traffic to the ports of the origin server after the configuration.|     -   By default, the HTTP and Websocket protocols use Port 80,
    -   and the HTTPS and Websockets protocols use Port 433.
 |
    |Choose Dedicated IP|Anti-DDoS Premium instance to protect the website.|For one website domain, you can set up to 8 Anti-DDoS Premium Dedicated IPs.|

4.  Go to the DNS service provider of your website, 

    and change the DNS record to the Dedicated IP of the Anti-DDoS Premium instance to enable Anti-DDoS service for your website.

    **Note:** Click **Return to website list**, if you want to test the forwarding rule of the Anti-DDoS Premium instance before switching business traffic to the Dedicated IP of Anti-DDoS Premium. After you verify that the forwarding rule works as expected, change the DNS record to switch business traffic to Anti-DDoS Premium.

    1.  Log on to the [Anti-DDoS Premium Service console](https://yundun.console.aliyun.com/?p=ddosdip), go to the **Instance List** page, locate the Anti-DDoS Premium instance that protects the website, and record the Dedicated IP of the instance. 
    2.  Go to the DNS service provider of your website, and change the A record to point to the Dedicated IP. 

        The settings pages of the different DNS service providers are different. The following pictures are for reference only.

        ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/79670/154692905035255_en-US.png)

    3.  After the DNS configuration is effective, all traffic to the website goes through the Anti-DDoS Premium instance for DDoS protection. 

        **Note:** Generally, the DNS configuration takes about 10 minutes to be effective. We recommend that you change the DNS configurations during the low peak period.

5.  Configure origin server protection. 

    **Note:** The origin server protection can prevent your origin server against light-traffic HTTP flood and web attacks, but cannot defend against heavy traffic DDoS attacks. In addition, it does not prevent DDoS attacks directly targeting the origin server through traffic that bypasses Anti-DDoS Premium, which may even throw the origin IP address into the blackhole routing status.


