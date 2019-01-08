# Fail to upload large files on the website with Anti-DDoS Pro enabled {#concept_58736_zh .concept}

After enabling Anti-DDoS Pro protection for the domain name, I cannot upload large files to the website, and the system throws a 413 error.

## Analysis { .section}

Anti-DDoS Pro limits the maximum file size allowed to be uploaded to the website. If you attempt to upload a file that exceeds 300 Mb in size, a 413 error is thrown.

## Resolution { .section}

-   Method 1

    Compress the file before uploading it, and make sure that the file you upload is smaller than 300 MB.

-   Method 2

    We recommend that you store large files in an Alibaba Cloud OSS bucket, rather than uploading it directly to the origin ECS server.

-   Method 3

    For occasional upload needs, you can temporarily map the HOST name to the IP address to bypass Anti-DDoS Pro, and directly access the ECS instance to upload the file.


