# Evidence: DNS YouTube Query

## Filter Used

```wireshark
dns.qry.name contains "youtube"
```

## Observation

The capture showed DNS query and response activity for a YouTube domain.

## Interpretation

The endpoint performed domain resolution before web traffic continued. DNS responses can return different record types, including IPv4 and IPv6-related records.

## Security Relevance

This demonstrates how analysts can use DNS evidence to understand which services an endpoint attempted to contact.

## Privacy Note

Only the protocol behavior is documented. Raw packet bytes and unnecessary identifiers were not published.
