# Owen Anderson

[Portfolio](https://owanden.github.io/) · [Try the queue preview](https://owanden.github.io/demos/office-hours-queue/)

## Selected projects

### [CrawlIndex](https://github.com/owanden/crawlindex)

Go / PostgreSQL / Docker. Crawl controlled HTML origins, retrieve extracted documents and search a PostgreSQL full-text index. Workers share durable job leases, URL deduplication and per-origin rate reservations.

- [Run the two-worker local demo](https://github.com/owanden/crawlindex#run-locally) for submission, extraction and search
- [Inspect verification](https://github.com/owanden/crawlindex/blob/main/docs/verification.md) covering killed-worker recovery, graceful shutdown and persistence across restart
- [Read the architecture and boundaries](https://github.com/owanden/crawlindex/blob/main/docs/architecture.md)

The demo uses controlled fixture pages. Kubernetes manifests render, but cluster operation and GCP deployment remain unverified.

### [Dispatch](https://github.com/owanden/dispatch)

Python / SQLite / HTTPS. Durable webhook delivery with idempotent enqueueing, bounded retries, signed requests and inspectable attempt history.

- [Run the local HTTPS demo](https://github.com/owanden/dispatch#run-the-demo)
- [Inspect actual worker-crash recovery](https://github.com/owanden/dispatch/blob/main/docs/crash-recovery.md), including duplicate acceptance and receiver deduplication
- [Read repeated workload measurements](https://github.com/owanden/dispatch/blob/main/docs/benchmarks.md) and [isolated wheel installation](https://github.com/owanden/dispatch/blob/main/docs/installation.md)

Delivery is at least once. Measurements use synthetic local workloads; public service deployment and production usage are not established.

### [Office Hours Queue](https://github.com/owanden/OH-Queue)

TypeScript / React / Express. Student queue and TA management with authenticated admin APIs and explicit public response fields.

- [Try the browser preview](https://owanden.github.io/demos/office-hours-queue/) with fixed synthetic data and simulated roles
- [Run the full-stack local walkthrough](https://github.com/owanden/OH-Queue/blob/main/docs/demo.md) with fake notifications

The preview makes no backend requests. The actual backend keeps separate room queues in memory; restarting discards them. The configured administrator manages all rooms.

### [Incident Triage Agent](https://github.com/owanden/cf_ai_incident_triage_agent)

TypeScript / Cloudflare Workers / Durable Objects. Structured incident summaries, hypotheses and next steps with transactional conversation updates.

- [Try the browser preview](https://owanden.github.io/demos/incident-triage/) with fixed responses and sessions held only in the tab
- [Run the provider-free fixture](https://github.com/owanden/cf_ai_incident_triage_agent#run-the-fixture-demo), including a reproducible failure case and keyboard controls
- [Inspect concurrency checks](https://github.com/owanden/cf_ai_incident_triage_agent/blob/main/tests/api.test.cjs) for delayed and overlapping responses

Fixture responses are predetermined, not a model-quality evaluation. The project has no authentication boundary; use synthetic incidents.
