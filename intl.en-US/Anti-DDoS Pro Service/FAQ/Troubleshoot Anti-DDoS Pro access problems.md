# Troubleshoot Anti-DDoS Pro access problems {#concept_55870_zh .concept}

## Symptoms {#section_xjy_sqk_ggb .section}

When a client attempts to access a website protected by Anti-DDoS Pro, the response becomes slow and choppy. It also suffers serious delay and packet loss.

## Analysis { .section}

Collect the affected clients’ source IP addresses, and perform link testing by using Traceroute/TRACERT, MTR, or network monitoring tools to determine the cause of this issue.

## Resolution { .section}

-   **Cross-network accesses**

    Anti-DDoS Pro supports the following types of lines: China Telecom, China Unicom, and BGP lines. The BGP line is used to optimize the network quality of China Mobile and small telecommunication operators.

    -   When a non-China Telecom client \(for example, a client using the China Unicom or China Mobile network\) accesses the China Telecom line, delay and packet loss may occur.
    -   When a non-China Unicom client \(for example, a client using the China Telecom or China Mobile network\) accesses the China Unicom line, delay and packet loss may occur.
    Solution: We recommend that you configure multiple lines for clients with different ISPs. For example, make the China Telecom clients access the China Telecom line, China Unicom clients access the China Unicom line, and clients using China Mobile and other networks access the BGP line.

-   **Backend server exceptions**

    Depending on the origin type, you can use the following troubleshooting methods to detect exceptions on your backend server.

    -   **For Server Load Balancer \(SLB\) origins**

        Follow these steps to troubleshoot issues on a Server Load Balancer origin.

        1.  Run the tcping tool for SLB IP addresses and ports, to check for exceptions in the log.
        2.  Check the status of the SLB instance for exceptions. For example, you can check the connection count and backend server.
        3.  Check for a blacklist/whitelist or any other access control policies on the SLB. Make sure that the Anti-DDoS Pro back-to-source IP segments are allowed in these settings.
        4.  Check for security software or any other IP address blocking policies on ECS or VPC.

            **Note:** A security software may regard the Anti-DDoS Pro IP addresses as malicious IP addresses because all access requests are forwarded by Anti-DDoS Pro to the backend server after you enable the service. Therefore you must set rules in the security software to allow Anti-DDoS IP addresses to pass through.

        5.  Check if the SLB IP address is exposed.
    -   **For cloud server \(ECS/VPC\) origins**

        Follow these steps to troubleshoot issues on an ECS or a VPC origin.

        1.  Run the tcping tool for server IP addresses and ports, to check for exceptions in the log.
        2.  Check for exceptions on the backend server. For example, the server IP address is in the black hole, the server is subject to traffic cleaning, the CPU consumption is high, the database response is slow, and the outbound bandwidth is full.
        3.  Check for a blacklist/whitelist or any other access control policies on the server. Make sure that the Anti-DDoS Pro back-to-source IP segments are allowed in these settings.
        4.  Check for any security software or other IP address blocking policies on the ECS or VPC instance. Make sure that the Anti-DDoS Pro back-to-source IP addresses are not blocked.
        5.  Check if the server IP address is exposed.
    -   **For non-Alibaba Cloud server origins**

        Follow these steps to troubleshoot issues on a non-Alibaba Cloud server origin.

        1.  Run the tcping tool for server IP address and ports, to check for exceptions in the log.
        2.  Check for exceptions on the server, such as high CPU consumption, slow database response, and full outbound bandwidth.
        3.  Check for a blacklist/whitelist or any other access control policies on the server. Make sure that the Anti-DDoS Pro back-to-source IP segments are allowed in these settings.
        4.  Check for any security software or other IP address blocking policies on the server.

            **Note:** Make sure that the Anti-DDoS Pro back-to-source IP addresses are not blocked.

        5.  Check if the server IP address is exposed.

            **Note:** We recommend that you replace your origin IP address after enabling Anti-DDoS Pro, and stop using the IP address that is already exposed.

-   **Traffic-cleaning events**

    In cases where Anti-DDoS Pro IP address is subject to a traffic-cleaning event, follow these steps to determine the issue:

    1.  Run the tcping tool for the affected ports to detect delay or packet loss. Record the result.
    2.  Run the tcping tool for the unaffected ports to detect delay or packet loss. Record the result.
    Compare the recorded results with the following table to determine the issue.

    |Delay or packet loss on affected ports|Delay or packet loss on unaffected ports|Analysis|
    |--------------------------------------|----------------------------------------|--------|
    |Yes|No|The traffic cleaning policy causes no false positives. You can check the backend server’s status and protection performance. If the server’s protection capability is relatively weak, you must apply a more stringent protection policy.|
    |Yes|Yes|The traffic cleaning policy causes false positives. You can submit a ticket for further backend inspection.|
    |No|No|The issue is not caused by the traffic cleaning policy.|
    |No|Yes|Generally, such a case does not exist.|

    For the first two cases, we recommend that you submit a ticket to our after-sales technical support team and describe the issue in detail. Upon receiving a ticket, Alibaba Cloud technical professionals will help you solve the issue. If you want to apply a more stringent protection policy, you must contain the detailed parameters of your server’s protection capability in the ticket. These parameters are:

    -   Description of normal user access
    -   Main service interaction process
    -   External service capability of your application
-   **Black hole events**

    In cases where Anti-DDoS Pro IP address is subject to a black hole event, identify the affected IP address and check if all affected requests pass through this IP address. Under certain circumstances, Anti-DDoS Pro supports automatic failover when an IP address is thrown into the black hole. But the actual time required for the changes to come into effect on clients depends on the time of DNS resolution, and local DNS caching and update.

    -   **Web services**

        Go to the **Anti-DDoS Pro** \> **Web Service** page, and check if the CNAME Auto Switch function is enabled. CNAME Auto Switch can switch the Anti-DDoS Pro service to a healthy line when the current line becomes unavailable. It provides the failover capability to guarantee the service continuity and availability.

        -   When the IP address of the China Telecom line is thrown into the black hole, CNAME automatically cancels resolution to the China Telecom IP address, and only resolves to China Unicom and BGP lines.
        -   When the IP address of the China Unicom line is thrown into the black hole, CNAME automatically cancels resolution to the China Unicom IP address, and only resolves to China Telecom and BGP lines.
        -   When the IP address of the China BGP line is thrown into the black hole, CNAME automatically cancels resolution to the BGP IP address, and only resolves to China Telecom and China Unicom lines.
    -   **Non-web services**

        For non-website access, you can only depend on the built-in scheduling configuration because Anti-DDoS Pro does not provide CNAME automatic switching for it.

        You can configure your application in a way that it is empowered with the failover capability. So that when the IP address of a line is thrown into the black hole, the application can switch to a healthy line.

-   **Other issues**

    If the issue persists, submit a ticket to contact the after-sales technical support team. We recommend that you include the following access information in the ticket to help our technical professionals quickly identify and analyze the issue.

    |Line|Source IP address|Anti-DDoS Pro IP address|Ping info|Traceroute or MTR info|Tcping or port connection info|
    |----|-----------------|------------------------|---------|----------------------|------------------------------|
    |China Telecom line|For example, 1.1.1.1|For example, 180.97.163.0|Results of more than 10 consecutive ping requests.|For example, Tracert or Traceroute info of accessing 180.97.163.0 from 1.1.1.1|Results of more than 10 consecutive tcping requests. Or the port connection information.|
    |China Unicom line|...|...|...|...| |
    |BGP line|...|...|...|...| |

    The following information also helps identify the issue:

    -   Configuration type of Anti-DDoS Pro back-to-source IP addresses, such as SLB, cloud server \(ECS/VPC\), and non-Alibaba Cloud server.
    -   Back-to-source IP addresses, and logs for the SLB, cloud server \(ECS/VPC\), or non-Alibaba Cloud server, including CPU, memory, bandwidth, and total connections.
    -   Access control policies applied in the origin.
    -   Security software installed in the origin, such as cloud locks, dongles, and the built-in iptables.
    -   Security policies applied in the origin, such as inspection and filtering for IP addresses.
    -   Traffic-cleaning or black hole events that Anti-DDoS Pro IP address is subject to.
    -   Service type, such as website, client games, web games, App, and so on.
    -   Operations that involve modifying or deleting the Anti-DDoS Pro instance during the occurrence of the issue.
     


## Commonly used network monitoring tools { .section}

**Traceroute command line tool**

Traceroute is a network testing tool pre-installed on almost all versions of Linux. It tracks the path of transferring data packets to a target IP address using Internet Protocol \(IP\).

Traceroute firstly sends UDP testing packets whose maximum Time To Live \(Max\_TTL\) period is short, and then listens to the ICMP TIME\_EXCEEDED response on the entire link starting from the gateway. The testing starts when TTL=1 and continues as the TTL value increases until you receive the ICMP PORT\_UNREACHABLE message. The ICMP PORT\_UNREACHABLE message identifies if the target host is located, or if the maximum TTL value to track the path of transferring data packets is reached.

**Note:** Traceroute sends UDP data packets for link testing by default. You can set the -I parameter so that traceroute sends an ICMP data packet for link testing.

Usage:

```
[root@centos ~]# traceroute -I 223.5.5.5
traceroute to 223.5.5.5 (223.5.5.5), 30 hops max, 60 byte packets
 1  * * *
 2  192.168.17.20 (192.168.17.20)  3.965 ms  4.252 ms  4.531 ms
 3  111.1.20.41 (111.1.20.41)  6.109 ms  6.574 ms  6.996 ms
 4  111.1.34.197 (111.1.34.197)  2.407 ms  2.451 ms  2.533 ms
 5  211.138.114.25 (211.138.114.25)  1.321 ms  1.285 ms  1.304 ms
 6  211.138.114.70 (211.138.114.70)  2.417 ms 211.138.114.66 (211.138.114.66)  1.857 ms 211.138.114.70 (211.138.114.70)  2.002 ms
 7  42.120.244.194 (42.120.244.194)  2.570 ms  2.536 ms 42.120.244.186 (42.120.244.186)  1.585 ms
 8  42.120.244.246 (42.120.244.246)  2.706 ms  2.666 ms  2.437 ms
 9  * * *
10  public1.alidns.com (223.5.5.5)  2.817 ms  2.676 ms  2.401 ms

```

**TRACERT command line tool**

TRACERT \(or Trace Route\) is a Windows command line utility for network diagnosis. It tracks the path of an IP data packet sent to the target IP address.

TRACERT sends ICMP data packets to determine the route to the target address. In these data packets, TRACERT uses different TTL values of IP addresses. Since routers along the data packet forwarding path must at least reduce the TTL by 1 before forwarding data packets, the TTL is actually equivalent to a hop counter. When the TTL of a packet reaches zero, the corresponding node sends an ICMP “timeout” message to the source computer.

TRACERT firstly sends the packet whose TTL value is 1, increases the TTL value by 1 and sends the corresponding packet in each subsequent transmission until the destination responds or the maximum TTL value is reached. The ICMP “timeout” messages sent back from intermediate routers contain information of corresponding nodes.

Usage:

```
C:\> tracert -d 223.5.5.5
Use at most 30 hops to track the routes of 223.5.5.5.

  1     *        *        *     Request timeout.
  2     9 ms     3 ms    12 ms  192.168.17.20
  3     4 ms     9 ms     2 ms  111.1.20.41
  4     9 ms     2 ms     1 ms  111.1.34.197
  5    11 ms     *        *     211.140.0.57
  6     3 ms     2 ms     2 ms  211.138.114.62
  7     2 ms     2 ms     1 ms  42.120.244.190
  8    32 ms     4 ms     3 ms  42.120.244.238
  9     *        *        *     Request timeout.
 10     3 ms     2 ms     2 ms  223.5.5.5

Tracking is finished.

```

For more information about TRACERT command line tool, see [Link testing tools for ping packet loss or ping failure](https://help.aliyun.com/knowledge_detail/40573.html).

**TCPing tool**

TCPing tool uses TCP method to view the port status and detect TCP delay and connection information. [Click to download the TCPing tool](http://docs-aliyun.cn-hangzhou.oss.aliyun-inc.com/assets/attach/55870/cn_zh/1498570697864/Tcping.zip).

-   **Usage in Windows**

    Copy the TCPing tool to the specified Windows directory and run the following command: `C:\>tcping.exe www.aliyun.com 80`

    Example

    ```
    C:\>tcping.exe www.aliyun.com 80
    
    Probing 140.205.62.8:80/tcp - Port is open - time=19.550ms
    Probing 140.205.62.8:80/tcp - Port is open - time=8.761ms
    Probing 140.205.62.8:80/tcp - Port is open - time=10.899ms
    Probing 140.205.62.8:80/tcp - Port is open - time=13.013ms
    
    Ping statistics for 140.205.62.8:80
         4 probes sent.
         4 successful, 0 failed.
    Approximate trip times in milli-seconds:
         Minimum = 8.761ms, Maximum = 19.550ms, Average = 13.056ms
    
    ```

-   **Usage in Linux**

    Run the following command to install the TCping tool.

    ```
    tar zxvf tcping-1.3.5.tar.gz
    cd tcping-1.3.5
    make tcping.linux
    
    ```

    Usage example:

    ```
    [root@aliyun tcping-1.3.5]# for ((i=0; i<10; ++i)) ; do ./tcping  www.aliyun.com 80;done
    www.aliyun.com port 80 open.
    www.aliyun.com port 80 open.
    www.aliyun.com port 80 open.
    www.aliyun.com port 80 open.
    www.aliyun.com port 80 open.
    www.aliyun.com port 80 open.
    www.aliyun.com port 80 open.
    www.aliyun.com port 80 open.
    www.aliyun.com port 80 open.
    www.aliyun.com port 80 open.
    
    ```


