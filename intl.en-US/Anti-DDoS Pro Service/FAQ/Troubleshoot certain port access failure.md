# Troubleshoot certain port access failure {#concept_57660_zh .concept}

This topic is applicable to scenarios where certain port accesses are blocked for a long time.

**Note:** If your Anti-DDoS Pro network links of all the three lines \(BGP, China Telecom, and China Unicom\) encounter failure at the same time, see [Troubleshoot Anti-DDoS Pro access problems](reseller.en-US/Anti-DDoS Pro Service/FAQ/Troubleshoot Anti-DDoS Pro access problems.md#).

A client fails to access the Anti-DDoS Pro IP address of a certain ISP \(such as China Telecom\) or a certain region \(such as Lanzhou\). However, the same client can access another Anti-DDoS Pro IP address of a different ISP or region.

## Resolution { .section}

Follow these steps to resolve this issue:

1.  Make sure that the client uses the same ISP network as the destination Anti-DDoS Pro IP address.
2.  Collect the following basic information: client IP address, ISP information, and the port that cannot be accessed.
3.  Perform further inspection and acquire the following diagnostic information:
    -   Screenshot of the Ping test result
    -   Screenshot of the Port telnet test result
    -   Full-screen screenshot of the specific error message
    -   Port route trace record, and result of the Port availability test
    -   Link testing result \(If the ports cannot be pinged, you can use TRACERT or MTR to perform link testing.\)
4.  Once you have identified the issue based on the preceding information, contact the relevant team to solve it.

## Case study { .section}

**Symptoms**

An Anti-DDoS Pro user has reported that a China Telecom user in ABC city, XYZ province has encountered an exception while accessing Port 80 of an Anti-DDoS Pro instance, but the access port 443 can be accessed normally.

**Resolution**

1.  Collect the following basic information:
    -   This China Telecom user was in ABC city, XYZ province, and the faulty Anti-DDoS Pro port was 80. The scope of the issue is clear.
    -   This user can normally access Port 443, it means that the entire link is open, and the problem lies on certain ports.
    -   We contacted the end user to retrieve the specific IP address: x.x.x.x
    -   We contacted the end user to retrieve the ping/telnet error messages.
    -   We contacted the end user to retrieve the comparison between normal and abnormal port accesses.
2.  Identify the problem. Based on the comparison between normal and abnormal port accesses, the tracking route was disconnected at a network exit in that city.
3.  Resolve the problem. We contacted the operator to resolve the problem. The problem was caused because of the Municipal jurisdiction security regulation policy.

