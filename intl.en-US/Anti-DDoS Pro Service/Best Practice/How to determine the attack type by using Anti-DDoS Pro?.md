# How to determine the attack type by using Anti-DDoS Pro? {#concept_58737_zh .concept}

This topic describes the method for you to identify the attack your Anti-DDoS Pro IP addresses suffer, from HTTP flood attack and DDoS attack.

-   HTTP flood attack: mainly indicates layer-7 website connection attacks.
-   DDoS attack: mainly indicates layer-4 heavy traffic attacks.

## Procedure { .section}

You can log on to the [Anti-DDoS Pro console](https://partners-intl.console.aliyun.com/#/ddospro) and go to the **Report** \> **Security Report** page to check attack records in the DDoS Protection and HTTP Flood Protection reports to determine the attack type.

-   For DDoS attack, you can find attack traffic record in the **DDoS Protection** report, and traffic cleaning is triggered. However, no associated record can be found in the **HTTP Flood Protection** report.
-   For HTTP flood attack, you can find attack traffic record in both of the **DDoS Protection** and **HTTP Flood Protection** reports, and traffic cleaning is triggered in the DDoS Protection report.

The DDoS Protection report only records layer-4 traffic. The HTTP flood attacks are layer-7 attacks, and the relevant protection result can only be viewed in the HTTP Flood Protection report.

