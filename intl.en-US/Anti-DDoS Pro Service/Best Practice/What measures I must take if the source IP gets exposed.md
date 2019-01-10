# What measures I must take if the source IP gets exposed {#concept_57378_zh .concept}

If your source IP can still be attacked after being protected under Anti-DDoS Pro, you can change the source IP address.

**Note:** Before changing the source IP address, make sure that you have eliminated all insecure factors that may expose the source IP address.

## Insecure factors checklist {#section_cdq_mxp_fgb .section}

Follow this checklist to confirm that no insecure factor may expose your source IP address.

1.  Check whether the origin server contains security risks such as Trojans or webshells.
2.  Check whether Anti-DDoS Pro is enabled for all services in the origin server, especially the records other than Web records such as MX records for mail servers and bbs records.

    **Note:** Double-check your DNS records to confirm that no record points to the source IP.

3.  Check whether the source code leaks your website information. For example, the `phpinfo()` command may contain IP addresses and other information.
4.  Check the origin server for malicious scanning. You can prevent this risk by only allowing the Anti-DDoS Pro IP addresses on the origin. Check if you have businesses resolved to the origin server. For more information, see [Protect the origin](reseller.en-US/Anti-DDoS Pro Service/Best Practice/Protect origin sites that use Anti-DDoS Pro.md#).
5.  Make sure that no business is resolved to the origin.
    1.  Use a Ping tester \(for example [DNS Checker](https://dnschecker.org/)\) to test the current domain name.
    2.  Check your DNS records again to make sure no record points to the source IP.

## Change source IP { .section}

After eliminating all the insecure factors that may expose the source IP, you can change the exposed source IP. For more information, see [Change ECS IP](reseller.en-US/Anti-DDoS Pro Service/User Guide/Instance management/Change ECS IP.md#).

**Additional solution**

If you do not want to change the source IP or have changed the source IP but still have a problem, we recommend that you deploy an SLB server in front of the backend of your ECS server.

You can deploy SLB by using the following architecture: Client \> Anti-DDoS Pro \> SLB \> ECS

**Note:** In this architecture, you must add the IP address of the load balancing server as the source IP in the Anti-DDoS Pro console.

With this architecture, even if the origin is put into a black hole after being attacked, to access the server through Anti-DDoS Pro remains unaffected. Because the traffic from the load balancing server to the origin is transmitted through the intranet, even if the origin IP is put into a black hole, Anti-DDoS Pro can still access the origin through the load balancing server.

