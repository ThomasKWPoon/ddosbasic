# Elastic protection FAQ {#concept_44095_zh .concept}

-   [Do I need to pay any fees for Elastic Protection when no attack occurs within one month?](#)
-   [What is my final protection capability if I have purchased the 20 GB Anti-DDoS Basic and 50 GB Elastic Protection?](#)
-   [What if the maximum Elastic Protection capability is exceeded?](#)
-   [How will I be charged if I have purchased the 50 GB Elastic Protection, but the actual attack traffic is only 30 GB?](#)
-   [Can I change the Elastic Protection capability from the current 100 GB to 200 GB?](#)
-   [How to calculate the fees if an IP has been attacked multiple times in one day?](#)
-   [Will I be charged based on the maximum attack traffic, if I have purchased a two-line subscription, and both the China Telecom and China Unicom IP addresses have been attacked?](#)
-   [How do I stop using the Elastic Protection capability to avoid the post-payment fees after purchasing an anti-DDoS Pro instance?](#)

## Do I need to pay any fees for Elastic Protection when no attack occurs within one month? {#2 .section}

In this case, you only need to pay the subscription fee for the Anti-DDoS Basic bandwidth, and no additional fees are incurred.

**Note:** If the service traffic exceeds the specification of Anti-DDoS Pro \(200 Mbps for hosts inside Alibaba Cloud, and 100 Mbps for hosts outside Alibaba Cloud\), corresponding traffic fees are incurred.

## What is my final protection capability if I have purchased the 20 GB Anti-DDoS Basic and 50 GB Elastic Protection? {#3 .section}

The final protection capability is 50 GB, which is subject to the Elastic Protection capability. For example, if you select the 20 GB Elastic Protection, you can only enjoy a protection capability of 20 GB, which is equivalent to without Elastic Protection.

## What if the maximum Elastic Protection capability is exceeded? {#4 .section}

When the attack traffic exceeds the maximum elastic protection capability for an IP address, this IP address is thrown into the black hole, and all traffic to/from it is blocked.

## How will I be charged if I have purchased the 50 GB Elastic Protection, but the actual attack traffic is only 30 GB? {#5 .section}

Basically, the fees are charged by the peak attack traffic. When the attack traffic is smaller than 20 GB \(covered by Anti-DDoS Basic\), no additional fee is charged. When the peak attack traffic is 30 GB, you only pay for protection of 30 GB. For specific fees, please contact our customer support representative.

## Can I change the Elastic Protection capability from the current 100 GB to 200 GB? {#6 .section}

Yes. You can adjust the Elastic Protection bandwidth in the Anti-DDoS Pro console, and you can either increase or decrease the bandwidth.

**Note:** When the protection bandwidth is changed, the changes are effective from the following day because you are already charged for the attacks that occurred during the present day.

## How to calculate the fees if an IP has been attacked multiple times in one day? {#7 .section}

The fees are charged based on the peak attack traffic during the day \(0:00-24:00\), and is charged only once. If an IP address is attacked three times in a day, and the attack traffic is 50 GB, 100 GB, and 200 GB respectively, then the Elastic Protection fee is charged based on the attack traffic of 200 GB.

## Will I be charged based on the maximum attack traffic, if I have purchased a two-line subscription, and both the China Telecom and China Unicom IP addresses have been attacked? {#8 .section}

The fees are charged based on individual IP addresses, rather than the Anti-DDoS Pro instance. Therefore, both lines are separately charged for Elastic Protection based on the maximum attack traffic of these two IP addresses.

## How do I stop using the Elastic Protection capability to avoid the post-payment fees after purchasing an anti-DDoS Pro instance? {#9 .section}

You can set the Elastic Protection bandwidth for your Anti-DDoS Pro instance to the same value as the Anti-DDoS Basic bandwidth. In this case, the system does not enable Elastic Protection when your IP address suffers from attack traffic that is higher than the Anti-DDoS Basic bandwidth.

You can log on to the Anti-DDoS Pro console and go to the **Asset** \> **Instance List** to adjust the Elastic Protection bandwidth for your Anti-DDoS Pro instance.

