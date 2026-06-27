# Protocol Explanations

This document explains the main protocols observed during the Windows Wireshark endpoint traffic analysis lab.

## DNS

**DNS** stands for Domain Name System.

It converts human-readable domain names into IP addresses.

Example:

```text
github.com -> IP address
www.youtube.com -> IP address
web.whatsapp.com -> IP address
```

Wireshark filter:

```wireshark
dns
```

Domain search example:

```wireshark
dns.qry.name contains "youtube"
```

## TCP

**TCP** is a reliable connection-based protocol.

It is commonly used for web browsing, file downloads, login pages, and applications that need ordered delivery.

Important concept:

```text
SYN -> SYN-ACK -> ACK
```

This is called the TCP three-way handshake.

Useful filter:

```wireshark
tcp
```

## UDP

**UDP** is a faster connectionless protocol.

It is commonly used by DNS, streaming, gaming, local discovery, and modern encrypted web traffic such as QUIC.

Useful filter:

```wireshark
udp
```

## TLS / HTTPS

**TLS** encrypts HTTPS traffic.

Wireshark can usually show metadata such as IP addresses, ports, packet size, timing, and sometimes server name information. It normally cannot show private website content because the traffic is encrypted.

Useful filter:

```wireshark
tls
```

## QUIC / UDP 443

**QUIC** is a modern encrypted transport protocol commonly used by browsers and web applications. It runs over UDP port 443.

Practical filter:

```wireshark
udp.port == 443
```

Combined encrypted web traffic filter:

```wireshark
tcp.port == 443 || udp.port == 443
```

## SSDP

**SSDP** stands for Simple Service Discovery Protocol.

It is used for local UPnP/service discovery. A Windows endpoint or browser may send SSDP M-SEARCH messages to discover local devices or services.

Common destination:

```text
239.255.255.250
```

Common port:

```text
UDP/1900
```

Useful filter:

```wireshark
ssdp
```

## mDNS

**mDNS** stands for Multicast DNS.

It is used for local service discovery, such as printers, casting devices, and local `.local` names.

Useful filter:

```wireshark
mdns
```

## NBNS

**NBNS** stands for NetBIOS Name Service.

It is an older Windows name resolution protocol used on local networks.

Useful filter:

```wireshark
nbns
```

## LLMNR

**LLMNR** stands for Link-Local Multicast Name Resolution.

Windows uses it for local name resolution when normal DNS does not resolve a local name.

Useful filter:

```wireshark
llmnr
```

## IGMP

**IGMP** stands for Internet Group Management Protocol.

It is used for multicast group management. In beginner analysis, it can usually be treated as normal network housekeeping traffic unless there is a specific investigation reason.

Useful filter:

```wireshark
igmp
```

## Beginner Mental Model

```text
DNS   = asks where a domain is located
TCP   = reliable connection
UDP   = fast communication
TLS   = encryption for HTTPS
QUIC  = modern encrypted web traffic over UDP/443
SSDP  = local device/service discovery
mDNS  = local service discovery
NBNS  = older Windows name lookup
LLMNR = Windows local name resolution
IGMP  = multicast group management
```
