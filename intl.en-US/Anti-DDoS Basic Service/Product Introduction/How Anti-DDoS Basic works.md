# How Anti-DDoS Basic works {#concept_28404_zh .concept}

Anti-DDoS Basic currently supports BGP and DNS redirection technologies. Its dominant protection mode is passive cleansing, supplemented by active suppression. The service comprehensively manages DDoS attacks.

On the basis of conventional technologies, such as proxy, detection, rebound, authentication, black/white lists, and message compliance, Alibaba Cloud Anti-DDoS Basic also integrates web security and filtering, reputation analysis, Layer-7 application analysis, user behavior analysis, feature learning, defense and counter-work, and other technologies. This service can block and filter threats, and guarantees that the protected users are secured even during the attack.

The present Anti-DDoS system built by Alibaba Cloud offers T-level defense capacity. Meanwhile, Alibaba Cloud is also expanding its protection nodes in various regions.

Based on independently developed Alibaba Cloud Security, Alibaba Cloud offers anti-DDoS service to defend against Layer-3 to Layer-7 DDoS attacks such as SYN flood, UDP flood, ACK flood, ICMP flood, DNS Query flood, NTP Reply flood, and HTTP flood attacks. The attacks protected against by Anti-DDoS Basic service are listed in the following figure:

![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/79444/154503671934068_en-US.png)

Anti-DDoS Basic builds DDoS attack detection and cleansing systems at the egress of Alibaba Cloud data centers and mainly adopts the bypass deployment architecture. The network topology of Anti-DDoS Basic service is illustrated as follows:

![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/79444/154503671934069_en-US.png)

