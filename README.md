## Hi, I'm Konrad 👋

Full-Stack / Backend Developer specializing in robust web applications, data consistency, and reliable backend services.

- 🛠️ **Backend Ecosystem:** PHP (Laravel, Symfony), Go (Golang)
- 💾 **Databases & Infra:** PostgreSQL, MariaDB, Redis, RabbitMQ, Docker
- 🚀 **Frontend Integration:** Inertia.js (Vue/React), Nuxt, Tailwind, TypeScript

---

### 🛠️ Tech Stack & Tools

![PHP](https://img.shields.io/badge/PHP-777BB4?style=flat-square&logo=php&logoColor=white) ![Laravel](https://img.shields.io/badge/Laravel-FF2D20?style=flat-square&logo=laravel&logoColor=white) ![Symfony](https://img.shields.io/badge/Symfony-000000?style=flat-square&logo=symfony&logoColor=white) ![Go](https://img.shields.io/badge/Go-00ADD8?style=flat-square&logo=go&logoColor=white) ![C++](https://img.shields.io/badge/C%2B%2B-00599C?style=flat-square&logo=c%2B%2B&logoColor=white)  
![PostgreSQL](https://img.shields.io/badge/PostgreSQL-4169E1?style=flat-square&logo=postgresql&logoColor=white) ![MariaDB](https://img.shields.io/badge/MariaDB-003545?style=flat-square&logo=mariadb&logoColor=white) ![Redis](https://img.shields.io/badge/Redis-DC382D?style=flat-square&logo=redis&logoColor=white) ![RabbitMQ](https://img.shields.io/badge/RabbitMQ-FF6600?style=flat-square&logo=rabbitmq&logoColor=white)  
![Vue.js](https://img.shields.io/badge/Vue.js-4FC08D?style=flat-square&logo=vuedotjs&logoColor=white) ![Nuxt.js](https://img.shields.io/badge/Nuxt.js-00DC82?style=flat-square&logo=nuxtdotjs&logoColor=white) ![Inertia.js](https://img.shields.io/badge/Inertia.js-9553E8?style=flat-square&logo=inertia&logoColor=white) ![Docker](https://img.shields.io/badge/Docker-2496ED?style=flat-square&logo=docker&logoColor=white)

> 💡 *Note: My primary commercial and daily development history is hosted on **[GitLab](https://gitlab.com/kopolot)**.*

---

### 🚀 Featured Projects

* **[Smart Invoice Guard (SIG)](https://github.com/kopolot/example-smart-invoice-guard)**
    * *What it is:* A showcase application built to demonstrate high-reliability backend patterns in web applications, focusing on data security, background task safety, and modern billing workflows.
    * *Tech Stack:* Laravel 13, Inertia.js v3, Vue 3, Tailwind v4, MariaDB, Redis, Fortify, Sanctum.
    * *Key Implementations:*
        * **Idempotent Payment Middleware:** Implemented atomic locking via Redis `Cache::add` (`SETNX` logic) protecting financial endpoints against parallel/double-submits.
        * **Race-Condition Resistant Queues:** Configured unique job execution backed by database-level row locking (`lockForUpdate()`) and `DB::afterCommit()` dispatch handling for bulletproof document delivery.
        * **Security & Compliance:** Transparent field encryption for tax numbers using Laravel Crypt adapters, comprehensive state history tracking via model observers (`InvoiceObserver`), and context-aware API rate limiting.

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

1. **Focus on Data Integrity:** A clean UI doesn't matter if the database is prone to duplicate actions or race conditions. I care about how data flows, atomicity, and endpoint-level security (`SETNX` locks, transaction control).
2. **Pragmatic Code Structure:** I don't write overengineered abstraction layers for simple applications. I follow framework standards (like Laravel's Form Requests, Symfony's Dependency Injection, or Go's standard layout) and write maintainable code.
3. **Automated Stability:** Feature, unit, and integration tests (PHPUnit, GTest) are part of my definition of "done." I make sure critical business paths are covered before shipping to staging.

---

📥 **How to reach me:** You can find my contact details and current commercial portfolio directly in my CV or feel free to open an issue/PR here!
