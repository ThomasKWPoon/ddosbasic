# Anti-DDoS Pro FAQ {#concept_56296_zh .concept}

-   [Can non-Alibaba Cloud users use Anti-DDoS Pro?](#)
-   [Does Anti-DDoS Pro support upgrade from two-line subscription to three-line subscription?](#)
-   [Does Anti-DDoS Pro support wildcard domain names?](#)
-   [Can I upgrade to higher protection capabilities at any time if the 20 GB Anti-DDoS Basic capability of my Anti-DDoS Pro instance is insufficient?](#)
-   [What will happen if my Anti-DDoS Pro instance expires?](#)
-   [What is Anti-DDoS Pro bandwidth?](#)
-   [Does it mean that each Anti-DDoS Pro IP address has a 500 Mbps service bandwidth if I purchase the Anti-DDoS Pro subscription with a service bandwidth of 500 Mbps?](#)
-   [Is there any problem if the traffic exceeds the bandwidth of Anti-DDoS Pro?](#)
-   [Does it support manual recovery if an Anti-DDoS Pro IP address has been thrown into the black hole?](#)
-   [What is the role of the backup IP address for Anti-DDoS Pro \(Hong Kong\)?](#)
-   [Will all Anti-DDoS Pro IP addresses be thrown into the black hole if the main IP address for Anti-DDoS Pro \(Hong Kong\) has been thrown into the back hole?](#)
-   [What are the back-to-source IP addresses of Anti-DDoS Pro?](#)
-   [Does Anti-DDoS Pro automatically add the Anti-DDoS Pro back-to-source IP addresses to the security group?](#)
-   [Can I enter the intranet IP address as the origin IP address for Anti-DDoS Pro?](#)
-   [Is there any delay when I modify the origin IP address for Anti-DDoS Pro?](#)
-   [How long will it take for configuration modifications to come into effect, if the modifications are made from the Anti-DDoS Pro console?](#)
-   [How can I view the attacker’s IP address from the Anti-DDoS Pro console?](#)
-   [How long will attack source IP address data be kept by Anti-DDoS Pro?](#)
-   [Is it true that I can only retrieve the last month’s data from the Anti-DDoS Pro security report?](#)
-   [How can I know which website is attacked if I have configured multiple websites under the same Anti-DDoS Pro instance?](#)
-   [What is the CNAME scheduling rule for Anti-DDoS Pro?](#)
-   [How does a non-website CNAME use CNAME domain name scheduling?](#)
-   [Does Anti-DDoS Pro support health check?](#)
-   [How to balance the load if Anti-DDoS Pro is configured with multiple origins?](#)
-   [Does Anti-DDoS Pro support packet capturing files?](#)
-   [Does Anti-DDoS Pro support session persistence?](#)
-   [How does Anti-DDoS Pro perform session persistence?](#)
-   [What is the default TCP connection timeout value for Anti-DDoS Pro?](#)
-   [What is the default HTTP/HTTPS connection timeout value for Anti-DDoS Pro?](#)
-   [Does Anti-DDoS Pro support IPv6 protocol?](#)
-   [Does Anti-DDoS Pro support WebSocket protocol?](#)
-   [Does Anti-DDoS Pro support HTTPS two-way authentication?](#)
-   [Why cannot old version browsers and Android clients normally access HTTPS sites?](#)
-   [What are the SSL protocols and encryption suites supported by Anti-DDoS Pro?](#)
-   [What are the total numbers of forwarding ports and domain names supported by Anti-DDoS Pro?](#)
-   [The server’s traffic does not reach the cleaning threshold. Why does some scrubbed traffic appear in the security report?](#)

 

## Can non-Alibaba Cloud users use Anti-DDoS Pro? {#1 .section}

Yes, non-Alibaba Cloud users can use Anti-DDoS Pro.

Anti-DDoS Pro uses a public network to return traffic back to origins, so all servers that are accessible to the public routes on Alibaba Cloud, other clouds, and IDC data centers can use Cloud Anti-DDoS Pro.

## Does Anti-DDoS Pro support upgrade from two-line subscription to three-line subscription? {#3 .section}

No, Anti-DDoS Pro does not support line upgrade. You can purchase the three-line Anti-DDoS Pro, and then migrate the original configuration to it. After confirming that the original two-line Anti-DDoS Pro has no business traffic, you can submit a ticket, indicating that you have already purchased the three-line Anti-DDoS Pro and the services have been migrated, and apply a refund for the original two-line Anti-DDoS Pro.

## Does Anti-DDoS Pro support wildcard domain names? {#4 .section}

Yes, Anti-DDoS Pro website protection supports wildcard domain names. You can use wildcard domain names when configuring HTTP flood protection and Web application protection.

Wildcard domain name resolution indicates the operation that uses a wildcard character \(asterisk\) as the subdomains, and direct all subdomains to the same IP address. For example, if you configure wildcard domain name resolution for www.taobao.com, all requests that access \*.taobao.com will be resolved to the IP address in the wildcard domain name resolution configuration.

## Can I upgrade to higher protection capabilities at any time if the 20 GB Anti-DDoS Basic capability of my Anti-DDoS Pro instance is insufficient? {#6 .section}

You can adjust Elastic Protection bandwidth on the **Asset** \> **Instance List** page of the [Anti-DDoS Pro console](https://partners-intl.console.aliyun.com/#/ddospro) at any time to obtain higher DDoS protection capability. Elastic protection bandwidth adjustment becomes immediately effective.

## What will happen if my Anti-DDoS Pro instance expires? {#7 .section}

Anti-DDoS Pro loses protection capability after expiration, but the forwarding rule configuration still functions normally. When the traffic exceeds the limit, traffic restrictions are triggered, which may cause random packet loss. You can release the instance from the console.

## What is Anti-DDoS Pro bandwidth? {#8 .section}

Service protection bandwidth for Anti-DDoS Pro is a normal traffic value accumulated by an Anti-DDoS Pro instance \(subject to the maximum value of the inbound traffic or outbound traffic\) in the unit of Mbps. You can upgrade the service bandwidth for your Anti-DDoS Pro instance at any time from the **Asset** \> **Instance List** page of the [Anti-DDoS Pro console](https://partners-intl.console.aliyun.com/#/ddospro). You can upgrade the service bandwidth up to 2 Gbps.

## Does it mean that each Anti-DDoS Pro IP address has a 500 Mbps service bandwidth if I purchase the Anti-DDoS Pro subscription with a service bandwidth of 500 Mbps? {#9 .section}

The purchased business bandwidth is for the entire high-security instance. No, the service bandwidth you have is for the entire Anti-DDoS Pro instance. If you have three Anti-DDoS Pro IP addresses for your Anti-DDoS Pro instance, then the total service bandwidth of these three IP addresses cannot be greater than 500 Mbps.

## Is there any problem if the traffic exceeds the bandwidth of Anti-DDoS Pro? {#10 .section}

If your traffic exceeds the service bandwidth that you have purchased, the system will trigger traffic restrictions, which may cause random packet loss.

## Does it support manual recovery if an Anti-DDoS Pro IP address has been thrown into the black hole? {#11 .section}

Currently, Anti-DDoS Pro supports black hole deactivation to partial ISP lines. Each Anti-DDoS Pro user has up to three chances to deactivate the black hole status in one day. You cannot do the deactivation after the chances exhausted. For more information, see [Deactivate black hole](reseller.en-US/Anti-DDoS Pro Service/User Guide/Layer-7 Protection Settings/Deactivate black hole.md#).

## What is the role of the backup IP address for Anti-DDoS Pro \(Hong Kong\)? {#13 .section}

If the main IP address’ data center crashes or is down, and cannot be quickly restored, you can use the backup IP address for failover. To guarantee smooth failover, make sure that the configuration for the backup IP address and that for the main IP address are synchronized.

**Note:** Protection capability for the main and backup IP addresses are different. Please use the main IP address to protect your service. The backup IP address is only designed for use in failover, and is not recommended for use during normal occasions.

## Will all Anti-DDoS Pro IP addresses be thrown into the black hole if the main IP address for Anti-DDoS Pro \(Hong Kong\) has been thrown into the back hole? {#14 .section}

No. After the main IP address has been thrown into the black hole, the default backup IP address will not be thrown into the black hole. However, in this case, Anti-DDoS Pro does not automatically resolve your service to the backup IP address. The backup IP address’ protection capability is only 500 MB. If you manually resolve your service to the backup IP address, then the backup IP address will also be thrown into the black hole when the attack traffic exceeds the protection capability.

## What are the back-to-source IP addresses of Anti-DDoS Pro? {#15 .section}

You can view the detailed back-to-source IP segments for Anti-DDoS Pro from the [Anti-DDoS Pro console](https://partners-intl.console.aliyun.com/#/ddospro). For more information, see [How to view the Anti-DDoS Pro back-to-source IP segment](reseller.en-US/Anti-DDoS Pro Service/FAQ/How to view the Anti-DDoS Pro IP addresses?.md#).

## Does Anti-DDoS Pro automatically add the Anti-DDoS Pro back-to-source IP addresses to the security group? {#16 .section}

No. Anti-DDoS Pro does not add the Anti-DDoS Pro back-to-source IP segment to the security group. You do not need to add them to your ECS or VPC security group either. However, if you have deployed a firewall or other host security protection software for your origin, you must add the Anti-DDoS Pro back-to-source IP segment to the corresponding whitelist.

## Can I enter the intranet IP address as the origin IP address for Anti-DDoS Pro? {#17 .section}

No. Anti-DDoS Pro is a public network back-to-source service, and does not support intranet IP addresses.

## Is there any delay when I modify the origin IP address for Anti-DDoS Pro? {#18 .section}

After you modify the origin IP address protected by Anti-DDoS Pro, the modifications will come into effect after approximately five minutes. We recommend that you perform modification during off-peak hours.

## How long will it take for configuration modifications to come into effect, if the modifications are made from the Anti-DDoS Pro console? {#19 .section}

Generally, the modified configuration comes into effect in 5 to 10 minutes.

## How can I view the attacker’s IP address from the Anti-DDoS Pro console? {#20 .section}

You can view the attacker’s IP address and the relevant attack information from the Security Report page on the Anti-DDoS Pro console.

## How long will attack source IP address data be kept by Anti-DDoS Pro? {#21 .section}

Anti-DDoS Pro keeps the attack source IP address data for 30 days. We recommend that you retrieve the relevant data from the Anti-DDoS Pro Security Report in a timely manner.

## Is it true that I can only retrieve the last month’s data from the Anti-DDoS Pro security report? {#22 .section}

Yes. Currently, Anti-DDoS Pro Security Report can only support to retrieve the data of the previous month. We recommend that you retrieve the corresponding Security Report in a timely manner.

## How can I know which website is attacked if I have configured multiple websites under the same Anti-DDoS Pro instance? {#23 .section}

From the data packet layer, we cannot identify which of the websites protected by Anti-DDoS Pro is the target of heavy traffic DDoS attacks. We recommend that you use multiple Anti-DDoS Pro instances, and deploy your websites respectively on different Anti-DDoS Pro instances. Then you can identify the information about attacks against each website.

## What is the CNAME scheduling rule for Anti-DDoS Pro? {#24 .section}

When an Anti-DDoS Pro IP address is thrown into the black hole, CNAME Auto Switch function randomly forwards the traffic that has been sent to this IP address to the Anti-DDoS Pro IP address in another line. The effective time of such schedule is subject to the Local DNS cache update time.

**Note:** You must enable CNAME Auto Switch to use it.

## How does a non-website CNAME use CNAME domain name scheduling? {#25 .section}

Website CNAME: Each domain name generates an independent CNAME, which has the automatic scheduling capability after an IP address is thrown into the black hole.

**Note:** If the following conditions are met, the non-website configuration can achieve automatic scheduling function by using a website CNAME.

-   Non-website forwarding configurations for three lines are consistent.
-   The application supports domain name scheduling.

In this case, you can configure website access \(for example, forward.example.com\), and use this website configuration to generate a CNAME to use in non-website forwarding, achieving the CNAME automatic scheduling function.

## Does Anti-DDoS Pro support health check? {#26 .section}

Yes. Web service enables health check by default.

Non-web service disables health check by default, but you can enable it from the console. For more information, see [Anti-DDoS Pro health check configuration](reseller.en-US/Anti-DDoS Pro Service/User Guide/Layer-4 Protection Settings/Health check settings for non-website service.md#).

## How to balance the load if Anti-DDoS Pro is configured with multiple origins? {#27 .section}

-   The web service uses the source address hashing method to perform load balancing.
-   Non-web service uses the weighted round robin \(wrr\) method for round-robin scheduling, and the load weight is 1:1:1.

## Does Anti-DDoS Pro support packet capturing files? {#28 .section}

No. Anti-DDoS Pro in China Telecom and China Unicom lines does not support the download of packet capturing files. You can directly view the attack source IP information from the Alibaba Cloud Security console.

For BGP line Anti-DDoS Pro, you can submit a ticket, indicating the related IP addresses and the black hole time, to retrieve the sampling packet that captures files during the attack.

## Does Anti-DDoS Pro support session persistence? {#29 .section}

Yes. Anti-DDoS Pro supports session persistence, but this function is disabled by default. You can configure session persistence for non-web services from the console. For more information, see [Anti-DDoS Pro session persistence rules](reseller.en-US/Anti-DDoS Pro Service/User Guide/Layer-4 Protection Settings/Session persistence settings for non-website services.md#).

## How does Anti-DDoS Pro perform session persistence? {#30 .section}

After you enable session persistence, Anti-DDoS Pro constantly sends requests from the same IP address to the same server on the origin, during the period set for session persistence. However, if the client’s network environment changes \(for example, switching from a wired network to a wireless network, from the 4G network to a wireless network, and so on\), session persistence may fail because of the change of the IP address.

## What is the default TCP connection timeout value for Anti-DDoS Pro? {#31 .section}

The default TCP connection timeout value for Anti-DDoS Pro is 900s. You can configure session persistence for non-web services from the console. For more information, see [Anti-DDoS Pro session persistence rules](reseller.en-US/Anti-DDoS Pro Service/User Guide/Layer-4 Protection Settings/Session persistence settings for non-website services.md#).

## What is the default HTTP/HTTPS connection timeout value for Anti-DDoS Pro? {#32 .section}

The default HTTP/HTTPS connection timeout value for Anti-DDoS Pro is 120s.

## Does Anti-DDoS Pro support IPv6 protocol? {#33 .section}

No, Anti-DDoS Pro currently does not support IPv6 protocol.

## Does Anti-DDoS Pro support WebSocket protocol? {#34 .section}

Yes, Web service of Anti-DDoS Pro supports WebSocket protocol.

## Does Anti-DDoS Pro support HTTPS two-way authentication? {#35 .section}

-   Anti-DDoS Pro that uses the website access method does not support HTTPS two-way authentication.
-   However, Anti-DDoS Pro that uses the non-website access method and TCP forwarding method supports HTTPS two-way authentication.

## Why cannot old version browsers and Android clients normally access HTTPS sites? {#36 .section}

Please check whether the clients support SNI authentication. For problems that SNI authentication may cause, see [HTTPS access exceptions arising from SNI compatibility](reseller.en-US/Anti-DDoS Pro Service/FAQ/HTTPS access exceptions arising from SNI compatibility.md#).

## What are the SSL protocols and encryption suites supported by Anti-DDoS Pro? {#37 .section}

 **Supported SSL protocols**

-   TLSv1
-   TLSv1.1
-   TLSv1.2

 **Supported encryption suites** 

-   ECDHE-ECDSA-AES128-GCM-SHA256
-   ECDHE-ECDSA-AES256-GCM-SHA384
-   ECDHE-ECDSA-AES128-SHA256
-   ECDHE-ECDSA-AES256-SHA384
-   ECDHE-RSA-AES128-GCM-SHA256
-   ECDHE-RSA-AES256-GCM-SHA384
-   ECDHE-RSA-AES128-SHA256
-   ECDHE-RSA-AES256-SHA384
-   AES128-GCM-SHA256
-   AES256-GCM-SHA384
-   AES128-SHA256
-   AES256-SHA256
-   ECDHE-ECDSA-AES128-SHA
-   ECDHE-ECDSA-AES256-SHA
-   ECDHE-RSA-AES128-SHA
-   ECDHE-RSA-AES256-SHA
-   AES128-SHA
-   AES256-SHA
-   DES-CBC3-SHA
-   RSA+3DES

## What are the total numbers of forwarding ports and domain names supported by Anti-DDoS Pro? {#38 .section}

-   Total number of forwarding ports: TCP and UDP protocols support 50 forwarding ports for each IP address by default, which can be extended to a maximum of 200 ports for each IP address.
-   Total number of supported domain names: HTTP and HTTPS support forwarding a total of 50 domain names for each instance by default, which can be extended to a maximum of 200 domain names for each IP address.

## The server’s traffic does not reach the cleaning threshold. Why does some scrubbed traffic appear in the security report? {#39 .section}

For services that have accessed in the Anti-DDoS Pro service, Anti-DDoS Pro automatically filters some malformed packets in the network traffic \(for example, small SYN packets and SYN flag bit exceptions that do not conform to the TCP protocol\). Thus, your server does not have to waste resources to deal with these obvious malformed packets. This type of filtered malformed packets are also counted in the scrubbed traffic, and that is the reason for that scrubbed traffic appears even if your server’s traffic does not reach the cleaning threshold.

