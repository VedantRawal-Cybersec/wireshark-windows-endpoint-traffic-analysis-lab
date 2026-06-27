# Wireshark Filters Used

This file documents the display filters used during the Windows endpoint traffic analysis lab.

## Endpoint Traffic

Show all traffic where the endpoint is either the source or destination:

```wireshark
ip.addr == <endpoint_ip>
```

Show traffic sent by the endpoint:

```wireshark
ip.src == <endpoint_ip>
```

Show traffic received by the endpoint:

```wireshark
ip.dst == <endpoint_ip>
```

## DNS Analysis

Show all DNS packets:

```wireshark
dns
```

Show DNS queries only:

```wireshark
dns.flags.response == 0
```

Show DNS responses only:

```wireshark
dns.flags.response == 1
```

Search for a domain keyword:

```wireshark
dns.qry.name contains "youtube"
```

```wireshark
dns.qry.name contains "whatsapp"
```

Search for an exact domain:

```wireshark
dns.qry.name == "www.youtube.com"
```

## Encrypted Web Traffic

Show HTTPS/TLS traffic over TCP:

```wireshark
tcp.port == 443
```

Show QUIC/HTTP3-style traffic over UDP:

```wireshark
udp.port == 443
```

Show both TCP/443 and UDP/443:

```wireshark
tcp.port == 443 || udp.port == 443
```

Show TLS packets:

```wireshark
tls
```

Show QUIC packets when Wireshark decodes them:

```wireshark
quic
```

## Local Discovery and Name Resolution

Show SSDP traffic:

```wireshark
ssdp
```

Show mDNS traffic:

```wireshark
mdns
```

Show NBNS traffic:

```wireshark
nbns
```

Show LLMNR traffic:

```wireshark
llmnr
```

Show local discovery and name resolution protocols together:

```wireshark
dns || mdns || nbns || ssdp || llmnr
```

## ICMP and Troubleshooting

Show ping/ICMP traffic:

```wireshark
icmp
```

Show IPv6 ICMP traffic:

```wireshark
icmpv6
```

## TCP Troubleshooting

Show TCP traffic:

```wireshark
tcp
```

Show TCP connection start packets:

```wireshark
tcp.flags.syn == 1 && tcp.flags.ack == 0
```

Show TCP retransmissions:

```wireshark
tcp.analysis.retransmission
```

Show TCP analysis warnings:

```wireshark
tcp.analysis.flags
```

## Notes

- Display filters are applied after packets are captured.
- Capture filters are applied before packets are captured.
- This lab primarily uses display filters because they are safer and easier for analysis.
- Encrypted traffic generally does not reveal page content; it shows metadata such as IPs, ports, timing, and packet sizes.
