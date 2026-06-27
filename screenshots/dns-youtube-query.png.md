# Evidence: DNS YouTube Query

This evidence represents the Wireshark filter:

```wireshark
dns.qry.name contains "youtube"
```

Observed behavior:

- DNS query packet for a YouTube domain
- DNS response packet returning related records
- Demonstrates endpoint domain-resolution analysis

Sensitive packet details were not published in raw form.
