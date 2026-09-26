

# Wireshark Network Traffic Analysis

A hands-on Wireshark lab analyzing DNS, TCP, ICMP, and TLS network traffic to investigate client-server communications and network protocols.

## DNS Query and Response Analysis

### DNS Query

![image alt](https://github.com/zhasansec/wireshark-network-traffic-analysis/blob/eb33540e7a6f72716614f040e79c2b19dbe4d6b0/dns%20query%20.png)


The workstation initiated a DNS A-record query for example.com. The query requested the IPv4 address associated with the domain. The packet was isolated using the DNS transaction ID 0x0379, and the query details show a Type A (Host Address) request with Class IN.

### DNS Response


![image alt](https://github.com/zhasansec/wireshark-network-traffic-analysis/blob/356eda0f478dd6009cd2e72631800a8b93a89866/dns%20query%20.png)

The DNS server returned a corresponding response for example.com containing two IPv4 addresses:

- 172.66.147.243
- 104.20.23.154

The matching transaction ID 0x0379 was used to correlate the DNS query with its response.

### Analysis

This capture demonstrates the DNS name-resolution process. The client sends a DNS query requesting the IPv4 address associated with a domain name, and the DNS server responds with the corresponding A records. Analyzing the transaction ID allows the request and response to be correlated in Wireshark.



