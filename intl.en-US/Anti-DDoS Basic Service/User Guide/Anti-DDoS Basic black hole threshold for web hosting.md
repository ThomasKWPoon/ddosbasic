# Anti-DDoS Basic black hole threshold for web hosting {#concept_40053_zh .concept}

The default black hole threshold for web hosting is as follows \(unit: bps\).

**Note:** For shared web hosting, the specific black hole threshold cannot be defined as multiple web hosting may share one IP address. Additionally, the actual threshold must be lower than the default threshold value. When a shared web hosting server triggers the black hole, all the other servers that share IP address with this server becomes inaccessible. We strongly recommend that you buy ECS instance if you give utmost importance to the security.

|Region|Web hosting threshold|
|------|---------------------|
|China \(Hangzhou\)|5 G|
|China \(Qingdao\)|5 G|
|China \(Shenzhen\)|2 G|
|China \(Beijing\)|2 G|
|China \(Shanghai\)|2 G|
|Hong kong|500 M|
|US West|500 M|
|Singapore|500 M|

The black hole duration is the amount of time the triggered back hole lasts, 2.5 hours by default. The actual black hole duration varies from 30 minutes to 24 hours, depending on attack intensity. Additionally, the following factors are considered:

-   Attack Continuity. The black hole duration is extended, if the attack continues.
-   Attack Frequency. The black hole duration is shortened automatically when the ECS instance is attacked for the first time, but can be prolonged accordingly, if under frequent attacks.

**Note:** If an ECS instance triggers too many black holes, Alibaba Cloud Security reserves the right to extend the black hole duration and lower its threshold. You can check the actual duration and threshold information in Alibaba Cloud Anti-DDoS Basic console.

