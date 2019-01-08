# 504 errors reported when handling requests with long processing time {#concept_58735_zh .concept}

While attempting to handle certain POST requests, the website protected by Anti-DDoS Pro waits for much longer time than required and returns a 504 error.

## Analysis { .section}

This issue is because the request needs long processing time, which exceeds the connection threshold of Anti-DDoS Pro. As a result, Anti-DDoS Pro closes the connection. The default connection thresholds of Anti-DDoS are as follows:

-   The TCP connection timeout value is 900s.
-   The HTTP/HTTPS connection timeout value is 120s.

## Resolution { .section}

We recommend that you configure a heartbeat detection for requests with long processing time. Enabling heartbeat detection can help make sure that the connection is active while you wait for a request to be handled.

Additionally, you can bypass Anti-DDoS Pro for certain requests, and have these requests directly access the backend ECS instance.

