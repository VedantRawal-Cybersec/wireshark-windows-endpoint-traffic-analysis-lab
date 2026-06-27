# Evidence: SSDP Local Discovery

## Filter Used

```wireshark
ssdp
```

## Observation

The capture showed SSDP M-SEARCH packets from the endpoint to a multicast discovery address.

## Interpretation

SSDP M-SEARCH means the endpoint was looking for local UPnP/network services. This can be triggered by Windows, browser features, media/casting functions, or local network service discovery.

## Security Relevance

SSDP is important to recognize because it can appear frequently in normal endpoint traffic. Analysts should be able to identify it as local discovery behavior and avoid confusing it with website browsing traffic.

## Privacy Note

The raw packet details were not published directly. The finding is documented at protocol level only.
