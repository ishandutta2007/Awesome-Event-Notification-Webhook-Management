# Awesome-Event-Notification-Webhook-Management

## Top Event Notification & Webhook Management Ecosystem

**Curated List of SaaS Platforms & Open-Source GitHub Projects**  
*Focused on Outbound Webhook Delivery, Inbound Proxying & Multi-Channel Notifications*  
**Last updated: March 2026**

This repository tracks notable **SaaS platforms** and **open-source projects** for **Event Notification & Webhook Management**. These tools help applications reliably deliver events to customer endpoints—covering everything from outbound webhook fan-out with retries and signing to inbound webhook proxies that buffer, inspect, and forward events to your local or private services.

**Examples** include Svix, Hookdeck, Hook0, Convoy, Hookdash, Novu, Courier, Inngest, and Pipedream (the category leaders).

**Open-source emphasis**: This section highlights every major active project for self-hosted webhook delivery, open-source notification infrastructure, and community-driven event gateways—ideal for developers seeking data sovereignty and avoiding per-event or per-message SaaS pricing. The open-source landscape splits into **outbound delivery engines** (Hook0, Outpost, Convoy) that fan out events to customer webhooks, and **notification infrastructure** (Novu) that unifies email, SMS, push, and chat alongside webhooks.

Contributions welcome! Open an PR to add/update entries. Keep descriptions factual and link to official sites.

## Table of Contents
- [SaaS/Hosted Platforms](#saas-products)
- [Open-Source GitHub Projects](#open-source-github-projects)
- [How to Contribute](#how-to-contribute)
- [Disclaimer](#disclaimer)

## SaaS/Hosted Platforms

| Product | Company Scale (Valuation / Revenue) | Description | Pricing (Starting) | Free Tier / Trial Limits |
|---------|------------------------------------|-------------|-------------------|--------------------------|
| **[Zapier Webhooks](https://zapier.com/)** | **$5.0B** valuation / ~$310M+ ARR | No-code webhook triggers and actions within Zapier. Receives inbound webhooks and sends outbound requests as part of multi-step Zaps. | Professional starts at **$19.99/month** (billed annually) or **$29.99/month** (monthly) for 750 tasks | **Free forever**: 100 tasks/month, limited to 2-step Zaps (1 trigger, 1 action), 15-minute polling interval |
| **[Inngest](https://www.inngest.com/)** | **~$105M - $175M** est. valuation ($34M total funding) | **Workflow orchestration for event-driven automations.** Durable step functions with retries, flow control (concurrency, throttling, debouncing), and event replay. | Pro starts at **$99/month** for 1,000,000 executions and higher concurrency | **Free forever**: 50,000 executions/month, 5 concurrent steps, 5 seats, 24-hr trace history (executions pause when limit reached) |
| **[Pipedream](https://pipedream.com/)** | **~$80M** valuation (Acquired by Workday; $20M+ funding) | **Integration platform for event-driven workflows.** Connects 3,000+ APIs with pre-built components and custom Node.js/Python/Go/Bash code. | Startup starts at **$99/month** (billed annually) or **$150/month** (monthly) for 10,000 credits & up to 100 users | **Free forever (Development/Test Plan)**: Daily credit allowance (~333 credits/day, 1 credit = 30s compute), 750s builder test runtime/day, development/testing only |
| **[Courier](https://www.courier.com/)** | **~$50M - $100M+** est. valuation ($57M+ funding) | **Multi-channel notification API.** Sends notifications across email, SMS, push, and chat with a unified API, visual workflow studio, and logs. | Business starts at **$0.005 per send** (pay-as-you-go after free allowance or with billing added) | **Free forever (Developer Plan)**: 10,000 sends/month across all channels with full API, template, and SDK access |
| **[Svix](https://www.svix.com/)** | **~$25M - $50M** est. valuation ($13M+ funding) | **The webhook service standard.** Hosted webhook delivery with a Rust-based open-source server as its foundation. Standard Webhooks originator (HMAC-SHA256). 8 retries over ~28 hours, payload replay, and rate limiting per endpoint. | Basic starts at **$20/month** (includes production 99.9% uptime SLA and pay-as-you-go scaling) | **Free forever**: 50,000 messages/month, 50 messages/second rate limit, 7-day payload retention |
| **[Hookdeck](https://hookdeck.com/)** | **~$10M - $20M** est. valuation ($2.7M funding, ~$880K ARR) | **Inbound webhook proxy and event gateway.** Receives webhooks from providers (Stripe, GitHub, Shopify), buffers them, and forwards to your application with retries and observability. | Team starts at **$39/month** (includes 7-day retention and unlimited team users) | **Free forever (Developer Plan)**: 10,000 events/month, 3-day event history retention, 1 user seat |

## Open-Source GitHub Projects

| Project | Star Badge | Description |
|---------|------------|-------------|
| **[Hook0](https://github.com/hook0/hook0)** | [![Stars](https://img.shields.io/github/stars/hook0/hook0?style=social&color=white)](https://github.com/hook0/hook0/stargazers) | **The most complete open-source outbound webhook platform with full-feature-parity self-hosting.** **SSPL-1.0 licensed, no closed tier**. **Multi-tenant label-based filtering**, HMAC signatures, fixed escalating backoff retries capped by max retries + window, **dead letter queue** (failed attempts kept and replayable), dot-notation event type hierarchy, delivery logs and replay, REST API, and **SDKs for 12+ languages** (JS, Rust, Python, Go, Ruby, PHP, C#, Java, Kotlin, Lua, Zig). Authentication via Biscuit tokens + service tokens. EU data plane available . **Best for SaaS products needing to offer webhooks to customers** without per-event fees . |
| **[Outpost (Hookdeck)](https://github.com/hookdeck/outpost)** | [![Stars](https://img.shields.io/github/stars/hookdeck/outpost?style=social&color=white)](https://github.com/hookdeck/outpost/stargazers) | **Production-ready self-hosted outbound webhook and event destinations infrastructure.** Apache-2.0, Go binary/Docker. Delivers to **11 destination types**: webhooks, AWS SQS, S3, EventBridge, Kinesis, GCP Pub/Sub, Azure Service Bus, RabbitMQ, Kafka, Cloudflare Queues, and Hookdeck Event Gateway . **Exponential backoff** with 30-second base, up to 10 retries. HMAC-SHA256 signing or Standard Webhooks headers. **Multi-tenant with a customer portal** for endpoint management and failed delivery retries. **Same codebase as managed Outpost**—no feature removal . **Best for teams wanting production-grade delivery to queues and webhooks** without vendor lock-in . |
| **[Convoy](https://github.com/frain-dev/convoy)** | [![Stars](https://img.shields.io/github/stars/frain-dev/convoy?style=social&color=white)](https://github.com/frain-dev/convoy/stargazers) | **Go-based webhooks gateway with dashboard, retries, and rate limiting.** **Elastic License v2.0**—paid features behind a license key. Acts as an edge gateway for both outbound delivery and inbound routing. **Horizontally scalable** with independent api/worker/scheduler/socket-server components. **Fan-out** to multiple endpoints based on event type or payload. **Rate limiting per endpoint**, retries (constant or exponential with jitter), **customer-facing iframe dashboard** for debugging and retries, and endpoint failure notifications (email/Slack) . **Best for teams wanting a dedicated webhook message queue** that handles both directions . |
| **[Hookdash](https://www.npmjs.com/package/hookdash)** | [![Stars](https://img.shields.io/github/stars/hookdash/hookdash?style=social&color=white)](https://github.com/hookdash/hookdash/stargazers) | **Zero-config self-hosted webhook gateway with SQLite only—no Redis, no Postgres.** MIT licensed. **`npx hookdash start`** runs in seconds. **Signature verification for Stripe, GitHub, Twilio, Shopify, and generic HMAC**. Smart retries with exponential backoff and jitter. **Circuit breaker** auto-disables failing endpoints and probes for recovery. **Dead letter queue** and **one-click replay** from dashboard. **Beautiful dark UI** with live event stream. Docker ready . **Best for small teams and solo developers** wanting webhook handling without database infrastructure . |
| **[Novu](https://github.com/novuhq/novu)** | [![Stars](https://img.shields.io/github/stars/novuhq/novu?style=social&color=white)](https://github.com/novuhq/novu/stargazers) | **Open-source notification infrastructure for transactional and multi-channel communications.** **Email, SMS, push, in-app, and chat** channels with 60+ provider integrations. **Workflows** define multi-step notification logic; **Inbox** component provides embeddable notification UI; **Agent Communication Infrastructure (ACI)** for agent conversations. Self-hostable on your own infrastructure . **Best for products needing unified multi-channel notifications** with webhooks as one channel among many . |

### Additional Strong Open-Source Options

| Project | Star Badge | Description |
|---------|------------|-------------|
| **[good-webhooks](https://github.com/pplytas/good-webhooks)** | [![Stars](https://img.shields.io/github/stars/pplytas/good-webhooks?style=social&color=white)](https://github.com/pplytas/good-webhooks/stargazers) | **Outbox-pattern webhook library that joins your database transaction.** MIT licensed. **`publish()` writes in the same transaction as your business logic**—no separate outbox table, no lost events if the app crashes before HTTP delivery. Standard Webhooks signing (HMAC-SHA256), **8 retries over ~28 hours** with `Retry-After` on 429/503, automatic pause after 5 days of failures or 410, replay (single or page), PostgreSQL storage . **Best for teams wanting webhook delivery as a library** rather than a separate service . |
| **[Inngest (OSS)](https://github.com/inngest/inngest)** | [![Stars](https://img.shields.io/github/stars/inngest/inngest?style=social&color=white)](https://github.com/inngest/inngest/stargazers) | **Durable workflow orchestration with self-hosting support.** **Single binary with SQLite or PostgreSQL**—zero dependencies for initial setup. Event API, queue with flow control (concurrency, throttling, rate limiting, debouncing), and state store for step functions. **The same code powers the cloud platform** . **Best for teams wanting event-driven workflows with durability** rather than pure webhook delivery . |

**Frameworks for building custom systems**: Choose **Hook0** for full-feature-parity outbound webhooks with multi-tenant filtering , **Outpost** for production delivery to queues and webhooks with a customer portal , or **Hookdash** for zero-config SQLite-only handling —all without per-event SaaS fees. For **multi-channel notifications**, **Novu** unifies webhooks with email, SMS, and push.

## How to Contribute

1. Fork the repo.
2. Add/edit entries in `README.md` (follow existing format).
3. Include: name, link, 1–2 sentence description, and whether it's SaaS or open-source.
4. Submit PR with a short explanation.

Star the repo if you find it useful!

## Disclaimer

- This is a **community-curated** list — not exhaustive and not an endorsement.
- Webhook and notification platforms handle event payloads that may contain sensitive data; enforce HMAC signature verification, HTTPS-only endpoints, and idempotent processing (delivery is **at-least-once**, not exactly-once) .
- **Open-source webhook tooling has different licensing and feature trade-offs.** **Hook0 is SSPL-1.0**—not OSI-approved, but full-feature-parity self-hosting with no closed tier . **Svix's open-source server is open-core**—some hosted features are not in the repo, and supported on-prem requires Enterprise . **Outpost is Apache-2.0** with the same codebase as managed Hookdeck—no feature removal . **Convoy uses Elastic License v2.0** with paid features behind a license key . **Hookdash is MIT** and requires only SQLite—no Redis or Postgres . **Novu is open-source** but competes in a different category (multi-channel notifications, not pure webhook delivery) . **Validate whether you need outbound delivery (Hook0, Outpost), inbound proxying (Hookdeck Event Gateway), or multi-channel notifications (Novu)** before committing.

---

**Made for developers, platform engineers, and teams building event-driven infrastructure.**  
Let's make event notification and webhook management more open, reliable, and developer-friendly.
