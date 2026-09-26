

# Wireshark Network Traffic Analysis

A hands-on Wireshark lab analyzing DNS, TCP, ICMP, and TLS network traffic to investigate client-server communications and network protocols.

## DNS Query and Response Analysis

### DNS Query

![image alt](https://github.com/zhasansec/wireshark-network-traffic-analysis/blob/eb33540e7a6f72716614f040e79c2b19dbe4d6b0/dns%20query%20.png)


 Isolated a DNS A-record query for example.com utilizing the unique transaction ID 0x0379. The packet details confirm a standard outbound Type A (Host Address), Class IN request initiated by the workstation to locate the domain's IPv4 mapping.

### DNS Response


![image alt](https://github.com/zhasansec/wireshark-network-traffic-analysis/blob/356eda0f478dd6009cd2e72631800a8b93a89866/dns%20query%20.png)

 Correlated the outbound request with the server's inbound response using the matching 0x0379 transaction ID. The authoritative DNS response successfully resolved example.com to two distinct destination IPv4 addresses: 
  - 172.66.147.243  
  - 104.20.23.154.


The matching transaction ID 0x0379 was used to correlate the DNS query with its response.

### Security and Risk Analysis

Protocol Baseline: This capture establishes a normal baseline for the DNS name-resolution process, demonstrating how transaction IDs prevent protocol mismatching

.Risk Perspective: From a security standpoint, monitoring these plaintext DNS queries is critical. Unencrypted DNS traffic can expose internal user behavior, map out corporate assets to an eavesdropper, or flag potential indicators of compromise (IoCs) such as connections to unauthorized malicious domains or data exfiltration via DNS tunneling.


