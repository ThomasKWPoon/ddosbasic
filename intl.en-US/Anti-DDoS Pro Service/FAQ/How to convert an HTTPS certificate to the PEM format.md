# How to convert an HTTPS certificate to the PEM format {#concept_40526_zh .concept}

A PEM certificate file \(\*.pem\) usually takes the following format:

**Note:** You can use notepad++ and other text editors to open PEM certificate files.

![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/79639/154693060535286_en-US.png)

CER/CRT certificates can be converted to the PEM format by directly modifying the file extension of the certificate file. For example, you can directly rename the server.crt certificate file as server.pem to convert it to the PEM format.

## Convert PFX certificates to the PEM format { .section}

PFX certificates are generally used in Windows Server and can be converted by using the OpenSSL tool.

For example, you can run the following OpenSSL commands to convert the certname.pfx certificate to the PEM format:

-   Extract the private key: `openssl pkcs12 -in certname.pfx -nocerts -out key.pem -nodes` 
-   Extract the certificate: `openssl pkcs12 -in certname.pfx -nokeys -out cert.pem` 

## Convert P7B certificates to the PEM format { .section}

P7B certificates are generally used in Windows Server and Tomcat servers, and can be converted by using the OpenSSL tool.

## Procedure { .section}

Follow these steps to convert a P7B certificate to the PEM format.

1.  Convert the certificate. For example, run the `openssl pkcs7 -print_certs -in incertificate.p7b -out outcertificate.cer` command to convert the incertificate.p7b certificate file to outcertificate.cer.
2.  Extract the certificate content from `[-----BEGIN CERTIFICATE-----` to `-----END CERTIFICATE-----]` in the outcertificat.cer file.
3.  Save the certificate content as the PEM format.

## Convert DER certificates to the PEM format { .section}

DER certificates are generally used on Java platforms and can be converted to the PEM format by using the OpenSSL tool.

For example, you can run the following OpenSSL commands to convert the certificate.cer certificate to the PEM format:

-   Extract the certificate: `openssl x509 -inform der -in certificate.cer -out certificate.pem` 
-   Extract the private key: `openssl rsa -inform DER -outform PEM -in privatekey.der -out privatekey.pem` 

