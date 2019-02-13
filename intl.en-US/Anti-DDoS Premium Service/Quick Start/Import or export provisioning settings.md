# Import or export provisioning settings {#concept_ghy_nrk_ggb .concept}

If you have multiple provisioning settings of website domain or layer-4 forwarding, and you want to back up or migrate the service provisioning settings, you can quickly complete such operations through the import/export functionalities of the provisioning settings.

-   The import/export of layer-4 forwarding rule settings supports the TXT format.

-   The import/export of website domain provisioning settings supports the XML format with high compatibility.

    The XML format has more parameter extensibility and readability than the TXT format. Additionally, the import/export also supports the provisioning setting that uses a domain as the origin site.


## Bulk import website domain name Configuration {#section_jr5_5tk_ggb .section}

1.  Log on to the [Anti-DDoS Premium Service console](https://partners-intl.console.aliyun.com/#/ddosdip).
2.  Go to **Provisioning** \> **Website**, click **Import** at the bottom of the domain setting list to add provisioning settings for multiple domains.
3.  In the Add Multiple Rules dialog box, enter the domain setting parameters in the specified XML format.

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/79673/155005726535279_en-US.png)

    **Note:** You can copy and paste the content in the text box.

    -   Parameter definition

        The domain setting parameter content must start with `<DomainList>`, and end with `</DomainList>`. Between these two tags, there is the domain provisioning setting parameters to be imported. The parameters of each domain provisioning setting start with `<DomainConfig>` and end with `</DomainConfig>`. For details about corresponding parameters for the domain provisioning setting, see the following table.

        |Parameter|Description|
        |---------|-----------|
        |`<Domain>a.com</Domain>`|Domain name to be provisioned. You can enter only one domain in this parameter.|
        |         ```
<ProtocolConfig>
<ProtocolList>http,https</ProtocolList>
</ProtocolConfig>
        ```

 |Protocol type. Separate multiple protocols with “,”. In this example, the protocols of the website domain are HTTP and HTTPS.|
        |         ```
<InstanceConfig>
<InstanceList>ddoscoo-cn-4590lwcny001</InstanceList>
</InstanceConfig>
        ```

 |Anti-DDoS Premium instance ID.**Note:** Since each Anti-DDoS Premium instance has one dedicated anycast IP, just specify the Anti-DDoS Premium instance ID. Separate multiple Anti-DDoS Premium instance IDs with “,”.

|
        |         ```
<RealServerConfig>
<ServerType>0</ServerType>
<ServerList>1.2.3.4</ServerList>
</RealServerConfig>
        ```

 |Origin site :        -   `<ServerType>0</ServerType>`: For origin IP
        -   `<ServerType>1</ServerType>`: For origin domain
In the `<ServerList>1.2.3.4</ServerList>` tags, specify the origin site address. Separate multiple origin site addresses with “,”.**Note:** For one domain, you cannot set both IP and domain addresses as the origin site.

|

    -   Sample

        ```
        <DomainList>
         <DomainConfig>
         <Domain>a.com</Domain>
         <ProtocolConfig>
         <ProtocolList>http,https</ProtocolList>
         </ProtocolConfig>
         <InstanceConfig>
         <InstanceList>ddosDip-cn-v0h0v9a3x07</InstanceList>
         </InstanceConfig>
         <RealServerConfig>
         <ServerType>0</ServerType>
         <ServerList>1.2.3.4</ServerList>
         </RealServerConfig>
         </DomainConfig>
         <DomainConfig>
         <Domain>b.com</Domain>
         <ProtocolConfig>
         <ProtocolList>http,websocket,websockets</ProtocolList>
         </ProtocolConfig>
         <InstanceConfig>
         <InstanceList>ddosDip-cn-v0h0v9a3x07,ddosDip-cn-0pp0u9slr01</InstanceList>
         </InstanceConfig>
         <RealServerConfig>
         <ServerType>1</ServerType>
         <ServerList>q840a82zf2j23afs.gfvip05al.com</ServerList>
         </RealServerConfig>
         </DomainConfig>
         </DomainList>
        ```

4.  Click **Next**.

    After the XML content passes the validation, it is resolved to the domain provisioning settings to be imported.

5.  Select the domain provisioning settings to be added, and click **OK** to import these settings.

## Export provisioning settings of website domain {#section_zcq_vwk_ggb .section}

1.  Go to **Provisioning** \> **Website**, click **Export** at the bottom of the domain setting list.
2.  Click **OK** to start an export task of current domain provisioning settings.
3.  Click the Task List icon in the upper right corner of the Provisioning page, to view the progress of the export task.
4.  After the task completes, click **Download** in the Task List dialog box, to download the domain provisioning settings to your local computer.

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/79673/155005726535284_en-US.png)

    **Note:** If the status of the tasks is **Preparing**, please be patient and wait for the export task to complete.


## Import forwarding rules {#section_img_pyk_ggb .section}

1.  Go to **Provisioning** \> **Non-Website** page.
2.  Click **Add Multiple Rules** \> **Add Forwarding Rules** at the bottom, to import multiple forwarding rules.

    **Note:** You can also select **Session Persistence/Health-Check** or **DDoS Mitigation Policies** to import corresponding settings.

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/79673/155005726535288_en-US.png)

3.  Refer to the samples to enter information about the settings.
    -   Forwarding rules

        ```
        
        tcp 90 91 192.136.12.41
        udp 22 13 12.14.1.23,10.23.4.12
        ```

        From left to right, the above fields are Protocol, Forwarding Port, Origin site port, and Origin site IP.

    -   Session persistence/health-check settings

        ```
        
        8081 tcp 4000 tcp 22 5 5 3 3
        8080 tcp 4000 http 22 5 5 3 3 /search.php www.baidu.com
        ```

        From left to right, the above fields are Forwarding Port, Forwarding Protocol, Session Persistence Timeout, Health Check Type, Ports, Response Timeout, Check Interval, Unhealthy Threshold, Healthy Threshold, URI \(Required when the health check type is http\), domain \(Optional when the health check type is http\). "Forwarding Port" must be a forwarding port that has policies configured.

    -   DDoS mitigation policies

        ```
        
        8081 tcp 2000 50000 20000 100000 1 1500 on on
        8080 udp 1000 50000 20000 100000 1 1500
        ```

        From left to right, the above fields are Forwarding Port, Forwarding Protocol, New Connection Speed Limits for Source IP, Concurrent Connection Speed Limits for Source IP, New Connection Speed Limits for Destination IP, Concurrent Connection Speed Limits for Destination IP, Minimum Length of Packets, Maximum Length of Packets, and False Sources and Null Session Connections \(This value is only effective for the TCP protocol. To enable the Null Session Connection setting, you must have the False Sources setting enabled\) .

4.  Click **Add** to import the settings.

## Export forwarding rules {#section_mwb_hhl_ggb .section}

1.  Go to **Provisioning** \> **Non-Website** page.
2.  Click **Export** \> **Export Forwarding Rules** at the bottom.

    **Note:** You can also select **Session Persistence/Health-Check** or **DDoS Mitigation Policies** to export corresponding settings.

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/79673/155005726535303_en-US.png)

3.  In the prompt box, click **OK**, to start an export task for current forwarding rules.
4.  Click the Task List icon in the upper right corner of the **Provisioning** page, to view the progress of the export task.
5.  After the task completes, click **Download** in the Task List dialog box, to download the forwarding rule settings to your local computer.

    **Note:** If the status of the tasks is **Preparing**, please be patient and wait for the export task to complete.


