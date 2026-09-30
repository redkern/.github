# redkern

Production-grade Node-RED palettes for teams that run Node-RED under real load:
millions of events per day, multiple pods, Kubernetes, and on-call.

Each package works on its own. Install only what you need.

## Packages

| Package | What it does | Status |
| --- | --- | --- |
| [`@redkern/node-red-redis`](https://github.com/redkern/node-red-redis) | Redis Streams with consumer groups, PEL recovery, DLQ, backpressure | in development |
| [`@redkern/node-red-kafka`](https://github.com/redkern/node-red-kafka) | Kafka consumer groups with manual commit and Protobuf via Schema Registry | in development |
| [`@redkern/node-red-gateway`](https://github.com/redkern/node-red-gateway) | Centralized outbound HTTP with distributed rate limiting | in development |
| [`@redkern/node-red-prometheus`](https://github.com/redkern/node-red-prometheus) | Contract-based Prometheus metrics with cardinality limits | in development |
| [`@redkern/node-red-migrate`](https://github.com/redkern/node-red-migrate) | Editor plugin to migrate flows from legacy packages | in development |

## Principles

- **At-least-once by default.** No silent message loss on redeploy, pause or crash.
- **Multi-pod aware.** Consumer identity, backpressure and cleanup work with HPA.
- **Secure by default.** Secrets in credentials, admin APIs behind Node-RED permissions.
- **Small footprint.** No palette depends on another one.

## Contact

- Bugs and questions: open an issue in the package repository
- Security: see our [security policy](https://github.com/redkern/.github/blob/main/SECURITY.md)
- Everything else: support@redkern.com
