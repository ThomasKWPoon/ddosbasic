# Protect origin sites that use Anti-DDoS Pro {#concept_40525_zh .concept}

This topic describes methods and principles for different scenarios to protect your origin sites under Anti-DDoS Pro.

**Note:** The origin sites protection can prevent your origin against light-traffic HTTP flood and Web attacks, but cannot defend against heavy traffic DDoS attacks. In addition, it does not prevent DDoS attacks directly targeting the origin through traffic that bypasses Anti-DDoS Pro, which may even throw the origin IP address into the black hole.

## Web service \(layer-7 forwarding\) {#section_xs3_dyp_fgb .section}

-   **Anti-DDoS Pro \> ECS or origins outside Alibaba Cloud**

    Under this architecture, visitors’ source IP addresses that send requests to ECS and non-Alibaba cloud origins are converted to Anti-DDoS Pro [back-to-source IP addresses](reseller.en-US/Anti-DDoS Pro Service/Quick Start/Web service/Step 2. Whitelist local IP subnet.md#).

    You can use the origin’s security software \(such as iptables and firewall\), to only allow Anti-DDoS Pro back-to-source IP addresses, and block all other IP addresses.

-   **Anti-DDoS Pro \> SLB \> ECS**

    Under this architecture, the IP address that sends requests to ECS becomes SLB’s IP address.

    We recommend that you use SLB’s whitelist to only allow Anti-DDoS Pro to access SLB. For more information about whitelist settings, see Configure a whitelist.

-   **Anti-DDoS Pro \> WAF/CDN \> ECS**

    Under this architecture, the IP address that sends requests to ECS becomes WAF or Alibaba Cloud CDN’s IP address.

    Whenever possible, we recommend that you configure relevant policies on WAF and Alibaba Cloud CDN, and configure origin policies based on the back-to-source IP addresses of WAF or Alibaba Cloud CDN.


## Non-Web service \(layer-4 protection\) { .section}

Origin sites protection is not necessary for layer-4 forwarding. Because the attackers can always bypass Anti-DDoS Pro and directly attack the origin, which may bring congestion or trigger the back hole. Origin protection does not work in this case.

## Configure ECS security group to protect the origin { .section}

Follow these steps to set up the security group for an ECS origin:

1.  Log on to the **ECS console**.
2.  In the left-side navigation pane, click **Security Group**, select the target region \(a security group can only be applied to ECS instances within the same region\), and click **Create Security Group**.
3.  Specify Security Group Name, Description, and Network Type, and then click **OK**.
4.  Click **Configure Rules** under the Actions column of the newly added security group, and then click **Add Security Group Rules**.
5.  Assume that the Anti-DDoS Pro IP segment is `1.1.1.0/24`, you can add the security group rules as shown in the following figure.

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/79580/154710609935044_en-US.png)

    **Note:** 

    -   You can only add one IP address or IP segment in the Authorization Object field at one time. If you have more than one IP address or IP segment, you must add a corresponding rule for each of them.
    -   When the same authorization object matches multiple rules, the rule with the highest Priority overrides the rest of the rules.
6.  Follow Step 4 to 5 to add security group rules for all Anti-DDoS Pro back-to-source IP segments to allow access from Anti-DDoS Pro. Add a security group rule to reject access from all IP addresses, and assign a lower priority \(less than 10 in this example\) to this rule.
7.  When the security group rules are configured, assign this security group to the ECS instance that needs to allow access from the Anti-DDoS Pro back-to-source IP addresses. You can click Manage Instances under the Actions column of the security group, and then click **Add an ECS Instance** to add this ECS instance to the security group.

