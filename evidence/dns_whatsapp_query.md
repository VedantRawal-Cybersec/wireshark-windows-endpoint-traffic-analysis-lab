# Evidence: DNS WhatsApp Query

## Filter Used

```wireshark
dns
```

## Observation

The capture showed DNS query activity for a WhatsApp Web domain.

## Interpretation

DNS packets show that the endpoint attempted to resolve a domain name before establishing web/app communication.

## Security Relevance

DNS analysis is useful in SOC work because it can help identify:

- Domains contacted by an endpoint
- Suspicious or unusual domain lookups
- Malware callback indicators
- Normal vs abnormal browsing-related behavior

## Privacy Note

Raw packet details and environment-specific values were not published directly.
