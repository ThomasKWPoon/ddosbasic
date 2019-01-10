# Billing method {#concept_40498_zh .concept}

Anti-DDoS Pro uses a hybrid billing method.

## Billing description {#section_sf1_z4m_2gb .section}

Billing type: Mixed

Unit: USD

Billing item: Basic protection and Elastic protection

Payment option: Subscription or Pay-As-You-Go

Billing cycle: Basic protection bandwidth \(Unit: Gbps\) and HTTP Flood protection capacity \(Unit: QPS\) are charged either monthly or yearly. A subscription bill is generated at purchase.

Settlement cycle: Elastic protection bandwidth \(Unit: Gbps\) and HTTP flood protection capacity \(Unit: QPS\) are charged daily. A Pay-As-You-Go bill is generated based on the actual attack peak that exceeds the basic DDoS protection capacity or HTTP flood protection capacity \(only the larger billing range is counted\) on the day before.

## Expiry description { .section}

-   You are sent reminder text messages/e-mails to renew your service seven days, three days, and one day before your upcoming expiry service.
-   If you fail to renew the service after its expiry, the Anti-DDoS Pro service will be restored to the Anti-DDoS Basic protection capability.
-   Your Anti-DDoS Pro configurations are retained for seven days after your service expires. If you renew the service within seven days, the protection continues without interruption. However, if the service is not renewed during this seven days grace period, your previous Anti-DDoS Pro IP gets auto released and the previous service configurations becomes unavailable.

## Overdue instructions { .section}

-   You receive **inner-site** notifications, three days before your Anti-DDoS Pro instance service expiration. You must renew your subscription. The Anti-DDoS Pro instance is disabled, if it is not renewed before its expiry. Moreover, the Anti-DDoS protection is restored to the default while having 5 GB capability offered for free.
-   When your protection service expires, Anti-DDoS Pro saves your configuration for additional seven days. If the service is renewed within these seven days, the Anti-DDoS Pro protection continues. Otherwise, the IP address of the Anti-DDoS Pro instance is released and the service becomes unavailable.

## Pricing {#section_iwh_4pm_2gb .section}

Basic protection \(monthly subscription\)

**Note:** HTTP flood protection capacity is the protection capacity against HTTP flood attacks. If your normal business consumes a large number of QPS, choose an appropriate package accordingly.

|DDoS protection capacity|HTTP flood protection capacity|China Telecom + China Unicom \(USD/Month\)|China Telecom + China Unicom + China Mobile \(USD/Month\)|
|5 Gbps|15,000 QPS|600|-|
|10 Gbps|30,000 QPS|1,310|-|
|20 Gbps|60,000 QPS|2,490|2,956|
|30 Gbps|100,000 QPS|3,970|4,686|
|40 Gbps|130,000 QPS|6,920|7,988|
|50 Gbps|160,000 QPS|9,880|11,290|
|100 Gbps|300,000 QPS|29,100|32,516|
|150 Gbps|450,000 QPS|36,490|41,164|
|200 Gbps|600,000 QPS|42,410|48,239|
|300 Gbps|1,000,000 QPS|-|**Discount Price: 62,580 Per Year**|
|\> 300 Gbps|\> 1,000,000 QPS|[Contact sales](https://www.alibabacloud.com/contact-sales)|

Elastic protection \(daily Pay-As-You-Go\)

|DDoS attack peak|HTTP flood attack peak|China Telecom + China Unicom \(USD/Day\)|China Telecom + China Unicom + China Mobile \(USD/Day\)|
|Attack peak≤20 Gb|Attack peak≤60,000 QPS|Covered by monthly basic protection package|
|20 Gb<Attack peak≤30 Gb|60,000 QPS<Attack peak≤100,000 QPS|270|270|
|30 Gb<Attack peak≤40 Gb|100,000 QPS<Attack peak≤130,000 QPS|470|470|
|40 Gb<Attack peak≤50 Gb|130,000 QPS<Attack peak≤160,000 QPS|660|660|
|50 Gb<Attack peak≤60 Gb|160,000 QPS<Attack peak≤200,000 QPS|860|860|
|60 Gb<Attack peak≤70 Gb|200,000 QPS<Attack peak≤230,000 QPS|1,350|1,350|
|70 Gb<Attack peak≤ 80Gb|230,000 QPS<Attack peak≤260,000QPS|1,650|1,650|
|80Gb<Attack peak≤100Gb|260,000QPS<Attack peak≤300,000 QPS|1,940|1,940|
|100 Gb<Attack peak≤150 Gb|300,000 QPS<Attack peak≤450,000 QPS|2,440|2,440|
|150 Gb<Attack peak≤200 Gb|450,000 QPS<Attack peak≤600,000 QPS|2,830|2,830|
|200 Gb<Attack peak≤300 Gb|600,000 QPS<Attack peak≤1,000,000 QPS|3,900|3,900|
|300 Gb<Attack peak≤400 Gb|1,000,000 QPS<Attack peak≤1,500,000 QPS|6,300|6,300|
|400 Gb<Attack peak≤500 Gb|1,500,000 QPS<Attack peak≤2,000,000 QPS|7,900|7,900|
|500 Gb<Attack peak≤600 Gb|2,000,000 QPS<Attack peak≤2,500,000 QPS|9,500|9,500|

**Note:** 

-   Daily Pay-As-You-Go pricing of elastic protection is calculated for each individual Anti-DDoS Pro instance that has the elastic protection capacity enabled. If more than one Anti-DDoS Pro instances are attacked, then all the affected instances are charged.
-   Elastic protection payment is calculated based on the actual attack peak that exceeds the basic DDoS protection capacity or HTTP flood protection capacity \(only the larger billing range is counted\) one day before.
-   If you do not want to enable elastic protection, set the elastic protection bandwidth to the same as the basic protection bandwidth. After this action, Anti-DDoS Pro instance will no longer have the elastic protection capacity.

Limits

|Specification|Limit|Description|
|-------------|-----|-----------|
|Bandwidth|100 Mbps/instance|Bandwidth consumed by normal business traffic in non-DDoS attack status.|
|QPS \(For web service\)|3,000 QPS/instance|QPS consumed by normal business request in non-DDoS attack status.|
|Forwarding port volume|50/IP address|Number of entries supported by TCP/UDP forwarding.|
|Protected domain volume|50/IP address|Number of entries supported by HTTP/HTTPS forwarding. Wildcard domain name forwarding is supported and only occupies one forwarding entry.|
|Number of servers protected|20 servers/instance|The total number of different IP addresses configurable for four-layer and seven-layer configuration.|
|New connection volume|50,000/VIP|The number of new connections for single VIP.|
|Concurrent connection|200,000/VIP|The number of concurrent connections for single VIP.|

**Note:** 

-   If you use an Alibaba Cloud web server, you can enjoy a maximum of business bandwidth of 200 Mbps.
-   The bandwidth limits applies to both IN and OUT directions.
-   The preceding plans are only available online. To meet the growing demands of your business, you can Contact sales for a customized solution.

## Renew and upgrade service { .section}

You can renew or upgrade your service.

-   Renew: After topping up your account, you can select to prolong the service cycle of the Anti-DDoS service.
-   Upgrade: You can upgrade your instance to increase the bandwidth, domain or port volumes.

