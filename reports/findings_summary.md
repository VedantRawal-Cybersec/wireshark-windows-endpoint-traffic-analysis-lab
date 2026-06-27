# Findings Summary

## Summary Table

| Area | Observation | Why It Matters |
|---|---|---|
| DNS | Domain lookup packets were observed | DNS helps analysts understand what domains an endpoint tried to resolve |
| Port 443 | Encrypted traffic metadata was visible | Shows modern HTTPS/QUIC behavior without exposing private content |
| SSDP | M-SEARCH local discovery packets were observed | Shows how endpoints discover local UPnP/network services |
| Local Discovery | mDNS/NBNS/LLMNR-style activity appeared in the capture | Common Windows/local network behavior analysts should recognize |
| Privacy | Raw sensitive details were redacted before publishing | Keeps the lab safe for public documentation |

## Key Takeaways

1. Wireshark is useful even when traffic is encrypted because metadata remains valuable.
2. DNS analysis can reveal domain resolution activity, but not every website will appear if DNS is cached or encrypted.
3. UDP/443 often indicates modern encrypted web communication such as QUIC/HTTP3.
4. SSDP, mDNS, NBNS, and LLMNR are common local discovery/name-resolution protocols.
5. A professional traffic analysis report should include scope, filters, evidence, findings, limitations, and privacy controls.

## Practical Value

This lab builds beginner-level skill in:

- Packet capture
- Display filtering
- Protocol interpretation
- Network troubleshooting fundamentals
- SOC-style evidence writing
- Ethical traffic analysis
