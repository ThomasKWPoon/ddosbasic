# How can origins outside Alibaba Cloud get clients’ real IP addresses? {#concept_52477_zh .concept}

If you have configured Anti-DDoS Pro for your hosts outside Alibaba Cloud, you can use the methods introduced in this topic to obtain the clients’ real IP addresses.

The methods described in this document support the following operating systems:

-   Redhat Linux
-   Centos 6.x

Consider these recommendations before you proceed with the steps:

-   Perform a demo in a test environment. Make sure the business is stable before making the official release.
-   Keep the original kernel. You can switch to the original kernel for recovery in case of restart failure.

## Procedure { .section}

Follow these steps to obtain the clients’ real IP addresses:

1.  Download the following kernel installation files:
    -   [kernel-2.6.32-220.23.2.ali\_github.el6.x86\_64.rpm](http://docs-aliyun.cn-hangzhou.oss.aliyun-inc.com/assets/attach/52477/cn_zh/1491917761209/kernel-2.6.32-220.23.2.ali_github.el6.x86_64.rpm) 
    -   [kernel-firmware-2.6.32-220.23.2.ali\_github.el6.x86\_64.rpm](http://docs-aliyun.cn-hangzhou.oss.aliyun-inc.com/assets/attach/52477/cn_zh/1491917803344/kernel-firmware-2.6.32-220.23.2.ali_github.el6.x86_64.rpm) 
2.  Install the kernel. Locate the installation directory and run the following command:

    ```
    rpm -ivh kernel-2.6.32-220.23.2.ali_github.el6.x86_64.rpm
    
    ```

    **Note:** You do not need to install kernel-firmware for CentOS 6.2 and later versions.

3.  Configure the toa module to enable auto-load.
    1.  Create a file /etc/sysconfig/modules/toa.modules, and add the following content:

        ```
        ! /bin/bash
        if [ -e /lib/modules/uname -r/kernel/net/toa/toa.ko ] ;
        then 
        modprobe toa > /dev/null 2>&1
        fi
        
        ```

    2.  Run the following command to grant the executable permission to the toa module.

        ```
        sudo chmod +x /etc/sysconfig/modules/toa.modules
        ```

4.  Run the `reboot` command to restart the system.

## Functional testing {#section_b3q_3lp_fgb .section}

In general, the host can obtain the clients’ real IP addresses once you complete the installation. If the host cannot retrieve the clients’ IP addresses, you can run the `lsmod|grep toa` command to check the loading status of the toa module.

If the toa module is not loaded, run the `modprobe toa` command to manually load it. When the module is loaded successfully, test the host again and see if it can get the clients’ real IP addresses.

## FAQ {#section_vh5_jlp_fgb .section}

-   Will the network performance be slowed down when the network connection has to pass through the toa module?

    The toa module is deployed on the supplementary access, and has little influence on the network performance.

-   Do I need to worry about the stability after loading the new kernel module?

    We recommend that you keep the original kernel. You can switch to the original kernel for recovery in case of restart failure. Additionally, you can find the source code of the current version on Github.


