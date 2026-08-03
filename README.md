## Hi, I'm Konrad 👋

Full-Stack / Backend Developer specializing in high-performance web applications, data consistency, and distributed backend architectures.

- 🛠️ **Backend Ecosystem:** PHP (Laravel, Symfony), Go (Golang)
- 💾 **Databases & Infra:** PostgreSQL, MariaDB / Percona XtraDB Cluster, ProxySQL, Redis, Memcached, RabbitMQ, Elasticsearch, Docker
- 🚀 **Frontend Integration:** Inertia.js (Vue/React), Nuxt, Tailwind, TypeScript

---

### 🛠️ Tech Stack & Tools

![PHP](https://img.shields.io/badge/PHP-777BB4?style=flat-square&logo=php&logoColor=white) ![Laravel](https://img.shields.io/badge/Laravel-FF2D20?style=flat-square&logo=laravel&logoColor=white) ![Symfony](https://img.shields.io/badge/Symfony-000000?style=flat-square&logo=symfony&logoColor=white) ![Go](https://img.shields.io/badge/Go-00ADD8?style=flat-square&logo=go&logoColor=white) ![C++](https://img.shields.io/badge/C%2B%2B-00599C?style=flat-square&logo=c%2B%2B&logoColor=white)  
![PostgreSQL](https://img.shields.io/badge/PostgreSQL-4169E1?style=flat-square&logo=postgresql&logoColor=white) ![MariaDB](https://img.shields.io/badge/MariaDB-003545?style=flat-square&logo=mariadb&logoColor=white) ![Elasticsearch](https://img.shields.io/badge/Elasticsearch-005571?style=flat-square&logo=elasticsearch&logoColor=white) ![Redis](https://img.shields.io/badge/Redis-DC382D?style=flat-square&logo=redis&logoColor=white) ![Memcached](https://img.shields.io/badge/Memcached-000000?style=flat-square&logo=memcached&logoColor=white) ![RabbitMQ](https://img.shields.io/badge/RabbitMQ-FF6600?style=flat-square&logo=rabbitmq&logoColor=white)  
![Vue.js](https://img.shields.io/badge/Vue.js-4FC08D?style=flat-square&logo=vuedotjs&logoColor=white) ![Nuxt.js](https://img.shields.io/badge/Nuxt.js-00DC82?style=flat-square&logo=nuxtdotjs&logoColor=white) ![Inertia.js](https://img.shields.io/badge/Inertia.js-9553E8?style=flat-square&logo=inertia&logoColor=white) ![Docker](https://img.shields.io/badge/Docker-2496ED?style=flat-square&logo=docker&logoColor=white) ![k6](https://img.shields.io/badge/k6-7D64FF?style=flat-square&logo=k6&logoColor=white)

> 💡 *Note: My primary commercial and daily development history is hosted on **[GitLab](https://gitlab.com/kopolot)**.*

---

### 🚀 Featured Projects

* **[Smart Invoice Guard (SIG)](https://github.com/kopolot/example-smart-invoice-guard)**
    * *What it is:* A high-reliability invoice management platform engineered to showcase advanced backend architecture, performance tuning, search capabilities, and distributed infrastructure resilience under load.
    * *Tech Stack:* PHP 8.5, Laravel 13, Inertia.js v3, Vue 3, Tailwind v4, Percona XtraDB Cluster (PXC), ProxySQL, RabbitMQ, Redis, Memcached, Elasticsearch, k6.
    * *Key Implementations:*
        * **High Availability & Caching Layers:** Powered by a 3-node Percona XtraDB Cluster with ProxySQL load balancing, Memcached for hot-path dashboard stats, and Redis Lua scripts for real-time engagement analytics ("Invoice Pulse").
        * **Elasticsearch Search Integration:** Custom indexing service utilizing `edge_ngram` prefixes for real-time document search with automated fallback to SQL `LIKE` queries.
        * **Concurrency & Event-Driven Architecture:** Asynchronous PDF processing and email delivery queued via RabbitMQ with unique execution locks (`lockForUpdate()`), `DB::afterCommit()` dispatch handling, and atomic Redis `SETNX` payment idempotency middleware.
        * **Automated Load Testing (k6):** Comprehensive k6 performance testing suite (Smoke, Load, Stress, Regression) integrated directly into GitHub Actions CI pipelines to enforce response time thresholds under load.

* **[Wikipedia Scraper](https://github.com/kopolot/example-wikipedia-scraper)**
    * *What it is:* A concurrent data extraction pipeline and subscription dashboard designed to crawl, process, and filter high-throughput web structures.
    * *Tech Stack:* Go (Golang), Nuxt 4, Vue 3, PostgreSQL 17, RabbitMQ, Redis, `chromedp`.
    * *Key Implementations:*
        * **Concurrent Browser Pipeline:** Built on top of Go's native concurrency model using `goroutines` and thread-safe channels coupled with a managed `chromedp` pool and proxy rotation.
        * **Async Event-Driven System:** Utilizes RabbitMQ and Redis to orchestrate independent workers across user registrations, subscription management (Basic/Premium tiers), and a dedicated notifications router (`cmd/notify`).

* **[MoodJournal Ecosystem](https://github.com/kopolot/moodjournal)** (Backend) & **[Mobile Client](https://github.com/kopolot/moodjournalmobile)**
    * *What it is:* A decoupled, gamified mood tracking platform splitting backend data processors from an independent cross-platform mobile app.
    * *Tech Stack:* Symfony 8.1, PHP 8.5, Expo (SDK 57), React Native, Lexik JWT, PostgreSQL, Messenger + RabbitMQ.
    * *Key Implementations:*
        * **Decoupled API & Security:** Secure token-based session management using JWT authentication alongside stateful, asynchronous message delivery via Symfony Messenger.
        * **Native Integration:** Multi-step check-in interface featuring localized global state handling, cross-platform notifications, and reactive UI feedback powered by Reanimated.

* **[cpp_chess](https://github.com/kopolot/cpp_chess)**
    * *What it is:* A highly modular chess engine built to demonstrate low-level architecture, custom build chains, and decoupling of core logic from presentation layers.
    * *Tech Stack:* C++20 (Concepts/Templates), CMake, Conan 2, Google Test, Vue 3, WebSockets (`cpp-httplib`).
    * *Key Implementations:*
        * **Core Algorithmic Foundation:** Complete implementation of FIDE regulations using strict compile-time optimizations, templates, and multiple board representations (`Board8x8` / `Board12x12`).
        * **Real-time Engine Web Layer:** Embedded C++ REST/WebSocket API supporting an interactive Vue 3 frontend, Minimax game loops with alpha-beta pruning, and multiplayer matchmaking queues.

---

### 🧠 My Engineering Approach

1. **Focus on Data Integrity & Performance:** A clean UI doesn't matter if the database suffers from race conditions or slow queries. I focus on atomicity (`SETNX` locks, row locking), proper indexing, caching strategies, and robust distributed setups.
2. **Pragmatic Architecture:** I avoid unnecessary complexity while adhering strictly to high-availability patterns. I follow framework standards (Laravel, Symfony, Go standard layout) and make intentional infrastructure choices (ProxySQL, RabbitMQ DLX, Elasticsearch).
3. **Automated Reliability:** Unit, integration, and performance load tests (PHPUnit, k6, GTest) are integral to my definition of "done." I ensure application behavior and latency limits are validated before code reaches production.

---

📥 **How to reach me:** You can find my contact details and current commercial portfolio directly in my CV or feel free to open an issue/PR here!
