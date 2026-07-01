# DevRadar

> Radar for the developer ecosystem: what's new, what's accelerating, what's adopted, what's vulnerable.

DevRadar monitors the pulse of open-source package ecosystems — npm, PyPI, Maven Central, Go modules, and crates.io — and surfaces what matters across four pillars:

- **What's new** — fresh releases across ecosystems, anchored on GitHub Releases and version data.
- **What's accelerating** — packages whose downloads and dependents are growing week over week.
- **What's adopted** — real usage proxied by download counts and dependent-package graphs.
- **What's vulnerable** — security advisories from OSV.dev, tracked over time per package.

## Status

🚧 In development.

DevRadar is built as a long-form engineering project — incrementally, with a clear path from monolith to event-driven architecture. The roadmap (~40 phases) is publicly tracked.

## Tech stack

**Core**
- Java 25 (LTS) + Spring Boot 4
- PostgreSQL — time-series, window functions, partitioning
- Redis — hot rankings (Sorted Sets), response caching
- Apache Kafka (KRaft mode) — event-driven core

**Concurrency**
- Virtual threads (Project Loom)
- Structured concurrency (JEP 505)
- Scoped values (JEP 506)

**Web & bot**
- Thymeleaf + HTMX + Pico.css — server-side dashboard
- Telegram Bot API — long polling

**Quality**
- JUnit 5, Mockito, AssertJ
- Testcontainers for integration tests
- GitHub Actions CI/CD
- OpenTelemetry for observability

## Sources

All data comes from official public APIs:

- [deps.dev](https://deps.dev) — Google Open Source Insights (versions, dependency graph, dependent counts)
- npm / PyPI download stats endpoints
- [GitHub Releases API](https://docs.github.com/en/rest/releases)
- [OSV.dev](https://osv.dev) — security advisories

No scraping. No private feeds.

## License

MIT — see [LICENSE](./LICENSE)
