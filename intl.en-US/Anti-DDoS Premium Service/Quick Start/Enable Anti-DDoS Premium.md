# Enable Anti-DDoS Premium {#concept_86323_zh .concept}

You can add configurations for your domains \(Layer 7\) and ports \(Layer 4\) in Anti-DDoS Premium for DDoS protection.

After purchasing an Anti-DDoS Premium instance, you can add configurations in the console to add forwarding rules of domains and ports to specify the origin servers where clean traffic is forwarded to after DDoS attack mitigation.

After completing the configurations in the console, you change the DNS resolution record for domain or change your business application’s IP to the CNAME or IP assigned by your Anti-DDoS Premium instance, to switch all traffic to the Anti-DDoS Premium’s dedicated IP. Then, all traffic firstly passes through global scrubbing centers and the clean traffic is forwarded back to the origin servers. In this situation, the unlimited full-capacity protection has been enabled for your business.

