# Obtain the real IP address of a visitor {#concept_40535_zh .concept}

This topic describes how to obtain the real IP addresses of access requests to your origin after you enable Anti-DDoS Pro for the origin.

## Non-Web Service \(Layer-4 access\) {#section_bz3_bsp_fgb .section}

Choose and apply the method best suitable for your origin to get the clients’ IP addresses, based on different deployment architectures.

-   Anti-DDoS Pro \> Alibaba Cloud ECS

    If you use the TCP port to forward flows, no special modification is required. IP addresses obtained by the origin server are the clients’ real IP addresses. Additionally, you can configure the ECS security group directly targeted on the clients’ real IP addresses.

    **Note:** If the UDP port is used to forward requests, then the origin ECS cannot obtain the real client IP addresses.

-   Anti-DDoS Pro \> SLB \> ECS

    If you use the TCP port to forward flows, no special modification is required. IP addresses obtained by the origin server are the clients’ real IP addresses.

    **Note:** 

    -   You must add the [Anti-DDoS Pro’s back-to-source CIDR block](reseller.en-US/Anti-DDoS Pro Service/Quick Start/Web service/Step 2. Whitelist local IP subnet.md#) to the whitelist of the Access Control settings in the SLB Management Console.
    -   If the UDP port is used to forward requests, then the origin ECS cannot obtain the real client IP addresses.
    **Notice:** 

    -   For ECS instances that are created after October 2018, clients’ real IP addresses can be obtained directly on the origin ECS server by default.
    -   For ECS instances that are created before October 2018, the origin ECS server cannot obtain clients’ real IP addresses. You have to submit a ticket to enable the corresponding feature.
-   Anti-DDoS Pro \> Non-Alibaba Cloud server

    This architecture is partially supported to obtain clients’ real IP addresses. For more information, see [How can origins outside Alibaba Cloud get the clients’ real source IP addresses](reseller.en-US/Anti-DDoS Pro Service/Best Practice/How can origins outside Alibaba Cloud get clients’ real IP addresses?.md#).


## Web service \(Layer-7 access\) { .section}

When a layer-7 proxy server \(such as Anti-DDoS Pro\) forwards users’ access requests to the backend server, the origin retrieves the back-to-Source IP addresses of this layer-7 proxy server \(such as Anti-DDoS Pro\). The client’s real IP address is placed into the HTTP header’s X-Forwarded-For field by the layer-7 proxy server. The format is as follows: `X-Forwarded-For: Visitor’s real IP address, Anti-DDoS Pro IP address`.

If more than one proxy server is adopted \(for example, the requests pass through WAF, CDN, and other proxy servers\), the format of the HTTP header’s X-Forwarded-For field is as follows: `X-Forwarded-For: Visitor’s real IP address, Proxy 1-IP address, Proxy 2-IP address, Proxy 3-IP address...`

The visitor’s real IP address is placed in the first position, followed by all intermediate proxy servers’ IP addresses. Therefore, the origin can obtain a visitor’s real IP address from the HTTP header’s X-Forwarded-For field.

**Common methods for retrieving the X-Forwarded-For field**

-   ASP

    ```
    Request.ServerVariables(“HTTP_X_FORWARDED_FOR”)
    
    ```

-   ASP.NET\(C\#\)

    ```
    Request.ServerVariables[“HTTP_X_FORWARDED_FOR”]
    
    ```

-   PHP

    ```
    `$_SERVER[“HTTP_X_FORWARDED_FOR”]
    
    ```

-   JSP

    ```
    request.getHeader(“HTTP_X_FORWARDED_FOR”)
    
    ```


After retrieving the HTTP header’s X-Forwarded-For field, use “,” as the delimiter to capture the first IP address, which is the client’s real IP address.

