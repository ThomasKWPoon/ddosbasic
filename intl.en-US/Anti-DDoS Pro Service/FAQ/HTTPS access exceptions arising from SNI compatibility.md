# HTTPS access exceptions arising from SNI compatibility {#concept_40519_zh .concept}

## What is SNI {#section_c1t_lxk_ggb .section}

The web hosting concept is introduced to HTTP servers to allow multiple domain names to use the same IP address, as the IPv4 addresses become scarce. A server can forward requests to different domain names \(web hosts\) based on the specified host in the request.

However, on an HTTPS server where an IP address is shared by multiple domain names \(web hosts\), the server doesn’t know the specific host that a client requests at the start of the handshaking process. Therefore, the server cannot forward the request to the specific web host. But to complete the handshaking process, the server must obtain the certificate information in the web host’s configuration.

Server name indication \(SNI\) is designed to resolve this issue. SNI requires the client to carry the host information of the domain name to be accessed before the handshake process with the server. The server can then choose the correct web host’s certificate to establish a handshake and TSL connection with the client.

SNI was first introduced in 2014 and is now supported by all mainstream browsers, servers, and testing tools.

## Why must the client support SNI to use Anti-DDoS Pro and WAF { .section}

When processing reverse proxy of HTTPS services, Anti-DDoS Pro and WAF interact with the real server \(RS\) on behalf of the client. So the certificates and private keys must be uploaded in the configurations of HTTPS protection. Because the Anti-DDoS Pro and WAF servers are limited in number, it is impossible to assign a physical server to a domain name. Therefore, the Anti-DDoS Pro and WAF clusters must contain servers that are shared by multiple domain names. As a result, the client must support SNI to interact normally with the Anti-DDoS Pro and WAF servers.

When you use a browser that does not support SNI to access a website protected by Anti-DDoS Pro or WAF, the Anti-DDoS Pro or WAF server fails to know the specific domain name which the client has requested. When the server cannot obtain the correct web host’s certificate to interact with the client, the built-in certificate is adopted by default. In this case, the client browser prompts “Server certificate cannot be trusted”.

**Note:** In theory, when an IP address is not shared by multiple domain names, it’s not necessary for the client browser to support SNI. However, even if the real server serves only one domain name, the Anti-DDoS Pro or WAF server still need to conduct reverse proxy between the client and the origin. Therefore, the client still must support SNI to establish the connection with the Anti-DDoS Pro or WAF server.

## Resolution { .section}

**Server end**

Configure your server to enable multiple HTTPS web hosts with one IP address.

**Client end**

If your client does not support SNI, consider the following suggestions:

-   We recommend that you use the latest version of Google Chrome and Firefox browsers.
-   Do not configure layer-7 website protection in Anti-DDoS Pro. Instead, configure website protection by using the layer-4 port 443 forwarding method.

    **Note:** The layer-4 protection does not protect your website against HTTP flood attacks.


**SNI compatibility**

**Note:** SNI is compatible with the TLS 1.1 and later versions, but is not compatible with the SSL protocol.

SNI is supported by the following **desktop browsers in clients**:

-   Chrome 5 and later versions
-   Chrome 6 and later versions
-   Firefox 2 and later versions
-   Internet Explorer 7 and later versions \(Only supports Windows Vista, Windows Server 2008, and later OS versions. In Windows XP, no IE browsers support SNI\)
-   Konqueror 4.7 and later versions
-   Opera 8 and later versions
-   Safari 3.0 and later versions \(Only supports Windows Vista, Windows Server 2008, and later Windows versions, or Mac OS X 10.5.6 and later Mac versions\)

SNI is supported by the following **mobile phone browsers in clients**:

-   Android 3.0 Honeycomb and later versions
-   iOS 4 and later versions
-   Windows Phone 7 and later versions

SNI is supported by the following **servers**:

-   Apache 2.2.12 and later versions
-   Apache Traffic Server 3.2.0 and later versions
-   Cherokee
-   HAProxy 1.5 and later versions
-   IIS 8.0 and later versions
-   Lighttpd 1.4.24 and later versions
-   LiteSpeed 4.1 and later versions
-   Nginx 0.5.32 and later versions

SNI is supported by the following **command lines**:

-   cURL 7.18.1 and later versions
-   wget 1.14 and later versions

SNI is supported by the following **libraries**:

-   GNU TLS
-   JSSE \(Oracle Java\) 7 and later versions \(only for use as a client\)
-   libcurl 7.18.1 and later versions
-   NSS 3.1.1 and later versions
-   OpenSSL 0.9.8j and later versions
-   OpenSSL 0.9.8f and later versions \(flag must be configured\)
-   QT 4.8 and later versions

