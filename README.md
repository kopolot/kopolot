## Hi, I'm Konrad 👋

Backend Developer (PHP, Go) with ~4.5 years of commercial experience, mostly in e-commerce and integrations: high-performance web applications, data consistency and distributed backend systems.

- 🛠️ **Backend Ecosystem:** PHP (Laravel, Symfony), Go (Golang)
- 💾 **Databases & Infra:** PostgreSQL, MariaDB / Percona XtraDB Cluster, ProxySQL, Redis, Memcached, RabbitMQ, Elasticsearch, Docker
- 🤖 **AI / LLM:** OpenAI-compatible APIs (OpenAI, Groq, OpenRouter, Ollama), LLM as an optional layer with deterministic fallbacks
- 🚀 **Frontend Integration:** Inertia.js (Vue/React), Nuxt, Tailwind, TypeScript
- 📱 **Mobile:** Kotlin + Jetpack Compose (Android), Expo / React Native

---

### 🛠️ Tech Stack & Tools

![PHP](https://img.shields.io/badge/PHP-777BB4?style=flat-square&logo=php&logoColor=white) ![Laravel](https://img.shields.io/badge/Laravel-FF2D20?style=flat-square&logo=laravel&logoColor=white) ![Symfony](https://img.shields.io/badge/Symfony-000000?style=flat-square&logo=symfony&logoColor=white) ![Go](https://img.shields.io/badge/Go-00ADD8?style=flat-square&logo=go&logoColor=white) ![Kotlin](https://img.shields.io/badge/Kotlin-7F52FF?style=flat-square&logo=kotlin&logoColor=white) ![C++](https://img.shields.io/badge/C%2B%2B-00599C?style=flat-square&logo=c%2B%2B&logoColor=white)  
![PostgreSQL](https://img.shields.io/badge/PostgreSQL-4169E1?style=flat-square&logo=postgresql&logoColor=white) ![MariaDB](https://img.shields.io/badge/MariaDB-003545?style=flat-square&logo=mariadb&logoColor=white) ![Elasticsearch](https://img.shields.io/badge/Elasticsearch-005571?style=flat-square&logo=elasticsearch&logoColor=white) ![Redis](https://img.shields.io/badge/Redis-DC382D?style=flat-square&logo=redis&logoColor=white) ![Memcached](https://img.shields.io/badge/Memcached-000000?style=flat-square&logo=memcached&logoColor=white) ![RabbitMQ](https://img.shields.io/badge/RabbitMQ-FF6600?style=flat-square&logo=rabbitmq&logoColor=white)  
![Vue.js](https://img.shields.io/badge/Vue.js-4FC08D?style=flat-square&logo=vuedotjs&logoColor=white) ![Nuxt.js](https://img.shields.io/badge/Nuxt.js-00DC82?style=flat-square&logo=nuxtdotjs&logoColor=white) ![Inertia.js](https://img.shields.io/badge/Inertia.js-9553E8?style=flat-square&logo=inertia&logoColor=white) ![Docker](https://img.shields.io/badge/Docker-2496ED?style=flat-square&logo=docker&logoColor=white) ![k6](https://img.shields.io/badge/k6-7D64FF?style=flat-square&logo=k6&logoColor=white)

> 💡 *Note: My primary commercial and daily development history is hosted on **[GitLab](https://gitlab.com/kopolot)**.*

---

### 🚀 Featured Projects

* **[Smart Invoice Guard (SIG)](https://github.com/kopolot/smart-invoice-guard)**
    * *What it is:* A high-reliability invoice management platform engineered to showcase advanced backend architecture, performance tuning, search capabilities, and distributed infrastructure resilience under load.
    * *Tech Stack:* PHP 8.5, Laravel 13, Inertia.js v3, Vue 3, Tailwind v4, Percona XtraDB Cluster (PXC), ProxySQL, RabbitMQ, Redis, Memcached, Elasticsearch, k6.
    * *Key Implementations:*
        * **High Availability & Caching Layers:** Powered by a 3-node Percona XtraDB Cluster with ProxySQL load balancing, Memcached for hot-path dashboard stats, and Redis Lua scripts for real-time engagement analytics ("Invoice Pulse").
        * **Elasticsearch Search Integration:** Custom indexing service utilizing `edge_ngram` prefixes for real-time document search with automated fallback to SQL `LIKE` queries.
        * **Concurrency & Event-Driven Architecture:** Asynchronous PDF processing and email delivery queued via RabbitMQ with unique execution locks (`lockForUpdate()`), `DB::afterCommit()` dispatch handling, and atomic Redis `SETNX` payment idempotency middleware.
        * **Security:** NIP encrypted at rest with a custom cast, token-aware API rate limiting, 2FA (TOTP) and passkeys (WebAuthn) via Fortify.
        * **Automated Load Testing (k6):** Comprehensive k6 performance testing suite (Smoke, Load, Stress, Regression) integrated directly into GitHub Actions CI pipelines to enforce response time thresholds under load.

* **[Resilient Webhook Engine](https://github.com/kopolot/resilient-webhook-engine)**
    * *What it is:* A compact Symfony microservice that accepts domain events over HTTP and delivers webhooks asynchronously to client endpoints under rate limits and fault conditions.
    * *Tech Stack:* PHP 8.4+, Symfony 7.4, Symfony Messenger, HttpClient, Redis, FrankenPHP, Docker, PHPStan (Level 9), PHPUnit, k6.
    * *Key Implementations:*
        * **Fault Tolerance:** Redis-backed **Circuit Breaker** with a single half-open probe (`SET NX`), fixed-delay retries (1m → 5m → 15m → 1h) and a Dead Letter Queue for exhausted messages. Non-retryable 4xx responses are dropped.
        * **Per-endpoint Concurrency Limits:** an atomic Redis **Lua semaphore** (one `EVAL` round-trip) keeps a burst of workers from flooding one customer and earning a `429` ban.
        * **Quality Gates:** PHPStan Level 9, PHPUnit unit + integration tests, and a Compose E2E + k6 job in GitHub Actions on every push/PR.

* **[MoodJournal Ecosystem](https://github.com/kopolot/moodjournal)** (Backend) & **[Mobile Client](https://github.com/kopolot/moodjournalmobile)**
    * *What it is:* A decoupled, gamified mood tracking platform splitting backend data processors from an independent cross-platform mobile app.
    * *Tech Stack:* Symfony 8.1, PHP 8.5, Expo (SDK 57), React Native, Lexik JWT, PostgreSQL, Messenger + RabbitMQ.
    * *Key Implementations:*
        * **Decoupled API & Security:** Secure token-based session management using JWT authentication alongside stateful, asynchronous message delivery via Symfony Messenger.
        * **Optional LLM Analysis:** mood patterns are computed in code first; an OpenAI-compatible client (OpenAI, Groq, OpenRouter, local Ollama) only adds a narrative on top, gets aggregates instead of raw notes, and falls back to the pattern engine on error or timeout.
        * **Native Integration:** Multi-step check-in interface featuring localized global state handling, cross-platform notifications, and reactive UI feedback powered by Reanimated.

* **[Wikipedia Scraper](https://github.com/kopolot/wikipedia-scraper)**
    * *What it is:* A concurrent data extraction pipeline and subscription dashboard designed to crawl, process, and filter high-throughput web structures.
    * *Tech Stack:* Go (Golang), Nuxt 4, Vue 3, PostgreSQL 17, RabbitMQ, Redis, `chromedp`.
    * *Key Implementations:*
        * **Concurrent Browser Pipeline:** Built on top of Go's native concurrency model using `goroutines` and thread-safe channels coupled with a managed `chromedp` pool and proxy rotation.
        * **Async Event-Driven System:** Utilizes RabbitMQ and Redis to orchestrate independent workers across user registrations, subscription management (Basic/Premium tiers), and a dedicated notifications router (`cmd/notify`).

* **[HC Sheets Sync](https://github.com/kopolot/hc-sheets-sync)**
    * *What it is:* A sideloaded Android app (not on the Play Store) that syncs daily health totals from Health Connect (Samsung Health) to Google Sheets, where an AI coaching bot reads them.
    * *Tech Stack:* Kotlin, Jetpack Compose, WorkManager, Health Connect API, Google Apps Script, DataStore.
    * *Key Implementations:*
        * **Self-healing Sync:** a daily background job re-sends the last 7 days and upserts them by date, so missed runs and late-logged meals catch up on their own. Workouts are upserted by session ID, so deleted sessions disappear from the sheet too.
        * **Correct Aggregation:** daily sums come from Health Connect's aggregate API (cross-app deduplication, records split at midnight). Missing data stays empty instead of 0, and BMR-only calorie days are flagged.
        * **Diagnostics & Tests:** an in-app screen compares aggregates with raw record sums per source app; unit tests cover the day logic and the Apps Script receiver. No secrets or health data in the repo.

---

### 🧠 My Engineering Approach

1. **Focus on Data Integrity & Performance:** A clean UI doesn't matter if the database suffers from race conditions or slow queries. I focus on atomicity (`SETNX` locks, row locking), proper indexing, caching strategies, and robust distributed setups.
2. **Pragmatic Architecture:** I avoid unnecessary complexity while adhering strictly to high-availability patterns. I follow framework standards (Laravel, Symfony, Go standard layout) and make intentional infrastructure choices (ProxySQL, RabbitMQ DLX, Elasticsearch).
3. **Automated Reliability:** Unit, integration, and performance load tests (PHPUnit, k6) are integral to my definition of "done." I ensure application behavior and latency limits are validated before code reaches production.

---

📥 **How to reach me:** You can find my contact details and current commercial portfolio directly in my CV or feel free to open an issue/PR here!
