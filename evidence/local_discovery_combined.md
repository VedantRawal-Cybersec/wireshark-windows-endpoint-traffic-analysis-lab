# Evidence: Combined Local Discovery Traffic

## Filter Used

```wireshark
dns || mdns || nbns || ssdp
```

## Observation

The capture showed multiple name-resolution and local-discovery protocols in the same packet set.

## Interpretation

Windows endpoints commonly generate discovery traffic in the background. This can include DNS, mDNS, NBNS, LLMNR, and SSDP depending on the device, browser, operating system, and local network environment.

## Security Relevance

Understanding normal discovery traffic helps analysts avoid false positives and identify unusual discovery behavior when it appears at abnormal volume or from unexpected devices.

## Privacy Note

Only protocol-level behavior is documented publicly.
