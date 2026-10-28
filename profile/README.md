<p align="center">
  <picture>
    <source media="(prefers-color-scheme: dark)" srcset="./assets/banner-dark.svg">
    <img alt="redkern: Node-RED palettes for teams that run Node-RED under real load" src="./assets/banner-light.svg" width="100%">
  </picture>
</p>

<p align="center">
  <img alt="Node.js 22 or later" src="https://img.shields.io/badge/Node.js-22%2B-339933?logo=nodedotjs&logoColor=white">
  <img alt="Node-RED 4.1 and 5.x" src="https://img.shields.io/badge/Node--RED-4.1%20%7C%205.x-8F0000?logo=nodered&logoColor=white">
  <img alt="License Apache-2.0" src="https://img.shields.io/badge/license-Apache--2.0-0969da">
</p>

Production-grade Node-RED palettes and plugins for teams that run Node-RED under real load:
millions of events per day, multiple pods, Kubernetes, and on-call.

Each palette works on its own. Install only what you need:

```bash
npm install @redkern/node-red-gateway
```

## Palettes

| | Package | What it does | Status |
| :---: | --- | --- | --- |
| <img src="./assets/gateway.svg" width="36" alt=""> | [`@redkern/node-red-gateway`](https://github.com/redkern/node-red-gateway) | Gateway between Node-RED instances over WebSocket: distributed rate limiting (GCRA), Redis Streams queue, idempotency, deadlines and retries | [![npm](https://img.shields.io/npm/v/@redkern/node-red-gateway?label=npm&color=A9DCD6)](https://www.npmjs.com/package/@redkern/node-red-gateway) |
| <img src="./assets/prometheus.svg" width="36" alt=""> | [`@redkern/node-red-prometheus`](https://github.com/redkern/node-red-prometheus) | Contract-based Prometheus metrics with cardinality limits; one `/metrics` for all redkern palettes | ![in development](https://img.shields.io/badge/in%20development-6e7681) |
| <img src="./assets/snowflake.svg" width="36" alt=""> | [`@redkern/node-red-snowflake`](https://github.com/redkern/node-red-snowflake) | Snowflake queries with key-pair auth, a managed connection pool, timeouts, cancellation and row limits | ![in development](https://img.shields.io/badge/in%20development-6e7681) |
| <img src="./assets/redis.svg" width="36" alt=""> | [`@redkern/node-red-redis`](https://github.com/redkern/node-red-redis) | Redis commands, Pub/Sub and Streams with consumer groups, PEL recovery, DLQ, backpressure and drain for rollouts | ![in development](https://img.shields.io/badge/in%20development-6e7681) |
| <img src="./assets/kafka.svg" width="36" alt=""> | [`@redkern/node-red-kafka`](https://github.com/redkern/node-red-kafka) | Kafka on librdkafka: consumer groups with manual ack, Protobuf and Avro via Schema Registry, SCRAM | ![in development](https://img.shields.io/badge/in%20development-6e7681) |
| <img src="./assets/scheduler.svg" width="36" alt=""> | [`@redkern/node-red-scheduler`](https://github.com/redkern/node-red-scheduler) | Schedules built in the editor instead of cron: a timezone per schedule, a preview of the next runs, overlap protection and optional run-once across pods | ![planned](https://img.shields.io/badge/planned-d0d7de) |

## Plugins

| | Package | What it does | Status |
| :---: | --- | --- | --- |
| <img src="./assets/flow-splitter.svg" width="36" alt=""> | [`@redkern/node-red-flow-splitter`](https://github.com/redkern/node-red-flow-splitter) | Splits `flows.json` into per-tab files with stable names for Git review and audit trails | ![in development](https://img.shields.io/badge/in%20development-6e7681) |
| <img src="./assets/migrate.svg" width="36" alt=""> | [`@redkern/node-red-migrate`](https://github.com/redkern/node-red-migrate) | Editor plugin that migrates flows from legacy `@yroshcha/*` packages tab by tab, keeping settings, secrets and consumer identity | ![in development](https://img.shields.io/badge/in%20development-6e7681) |

## Library

| | Package | What it does | Status |
| :---: | --- | --- | --- |
| <img src="./assets/kit.svg" width="36" alt=""> | [`@redkern/node-red-kit`](https://github.com/redkern/node-red-kit) | Zero-dependency runtime library shared by all redkern packages: config, secrets, auth, lifecycle, resilience, Redis client factory, metrics | [![npm](https://img.shields.io/npm/v/@redkern/node-red-kit?label=npm&color=D0D7DE)](https://www.npmjs.com/package/@redkern/node-red-kit) |

## Principles

**Honest delivery guarantees.** No silent message loss on redeploy, pause or rollout. Where at-least-once means a message can arrive twice, the docs say so.

**Multi-pod aware.** Consumer identity, backpressure, drain and cleanup work with HPA and rolling deploys.

**Secure by default.** Secrets live in credentials, admin APIs sit behind Node-RED permissions, and no listener accepts unauthenticated traffic beyond loopback.

**Independent palettes.** Packages share only `@redkern/node-red-kit`, which has no runtime dependencies. No palette depends on another palette.

**Safe to migrate.** Data names such as Redis keys, Kafka group IDs and metric names never change, so dashboards and offsets survive the switch.

## Releases

Stable versions from 1.0.0 are published to npm from GitHub Actions with provenance. Pre-releases are available as tarballs on GitHub Releases. Every package follows semver and keeps a changelog.

## Contact

- Bugs and questions: open an issue in the package repository
- Security: see our [security policy](https://github.com/redkern/.github/blob/main/SECURITY.md)
- Everything else: support@redkern.com

---

<sub>Apache-2.0 licensed. Made in Kyiv.</sub>