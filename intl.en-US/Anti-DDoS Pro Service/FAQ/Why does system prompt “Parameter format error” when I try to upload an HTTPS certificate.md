# Why does system prompt “Parameter format error” when I try to upload an HTTPS certificate {#concept_40527_zh .concept}

When I upload the HTTPS certificate while configuring Anti-DDoS Pro, the system prompts “Parameter format error.”

Common issues, causes, and solutions to the “Parameter format error” upon uploading the certificate are listed as follows:

-   The certificate name exceeds the length limit.

    Solution: Modify the certificate name to contain less than 10 characters.

-   The certificate file name contains special characters.

    Solution: Only use English letters or numbers to name the certificate, and do not use spaces, underscores\(\_\), delimiters, or other special characters.

-   The certificate contains non-standard content. For example, the highlighted content of the following certificate file is invalid.

    Example

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/79642/154693073935289_en-US.png)

    Solution

    Remove the certificate content before `---BEGIN CERTIFICATE---`.

    -   A standard certificate \(.pem file\) looks like the following:

        ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/79642/154693073935290_en-US.png)

    -   A standard private key \(.key file\) looks like the following:

        ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/79642/154693073935291_en-US.png)


For more information about HTTPS certificate format conversion, see [Convert an HTTPS certificate to the PEM format](reseller.en-US/Anti-DDoS Pro Service/FAQ/How to convert an HTTPS certificate to the PEM format.md#).

