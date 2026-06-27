# Evidence: Router / Local Device Discovery Response

## Filter Used

```wireshark
ip.addr == <gateway_or_endpoint_ip>
```

## Observation

The capture showed local discovery response traffic between the endpoint and a local network device.

## Interpretation

Local discovery protocols can produce request-and-response traffic between an endpoint and network devices such as routers, media devices, printers, or UPnP-enabled services.

## Security Relevance

This evidence helps demonstrate endpoint-to-local-network communication and shows why analysts must separate local discovery traffic from internet browsing traffic.

## Privacy Note

The public documentation avoids exposing complete device identifiers or raw packet contents.
