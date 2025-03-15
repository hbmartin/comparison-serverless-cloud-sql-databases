# Comparing hosts for serverless cloud SQL databases

This document provides a comparison between hosted, serverless (no cost or management to spin down to zero) providers of SQL cloud databases.

PlanetScale has been removed due to their user hostile pricing changes. Render has been removed since their free plan is disabled after 30 days.

Please join our [discussions](https://github.com/hbmartin/comparison-serverless-cloud-sql-databases/discussions) or fix/update information by [editing this doc](https://github.com/hbmartin/comparison-serverless-cloud-sql-databases/edit/main/README.md)!

See also the [Python FaaS Comparison](https://github.com/hbmartin/comparison-hosts-serverless-cloud-function-faas-for-python)

See also the [Authentication Providers Comparison](https://github.com/hbmartin/comparison-web-app-authentication-providers?tab=readme-ov-file)

- [DevEx](#devex)
- [Pricing](#pricing)
- [Runtime Limits](#runtime-limits)
- [Discussions, Community, and Support](#discussions-community-and-support)

## DevEx

|                                | Dialect                                                      | Status  | Cloud      | Cnxn         | OSS  | Examples                                                     | Docs |
| ------------------------------ | ------------------------------------------------------------ | ------- | ---------- | ------------ | ---- | ------------------------------------------------------------ | ---- |
| **Aurora Serverless v2 (AWS)** | PostgreSQL / MySQL                                           | GA      | AWS        |              |      |                                                              |      |
| **Azure SQL Serverless**       |                                                              | GA      | Azure      |              |      |                                                              |      |
| **CockroachDB**                | [Postgres compat.](https://www.cockroachlabs.com/docs/stable/postgresql-compatibility) | GA      | AWS / GCP  | Pool         | ✅    | [Link](https://www.cockroachlabs.com/docs/stable/example-apps) | 🚀    |
| **D1 (Cloudflare)**            | SQLite                                                       | GA      | Cloudflare | HTTP         | 🚫    | [Link](https://developers.cloudflare.com/d1/get-started/)    | 🚀    |
| **Gel**                        | PosgreSQL + EdgeQL                                           | Early   | AWS        |              |      |                                                              |      |
| **Fauna**                      | FQL                                                          | GA      | ?          | HTTP         | 🚫    | [Link](https://docs.fauna.com/fauna/current/guides/todo)     | 👍    |
| **LiteFS**                     | SQLite                                                       | GA (v0) | Fly.io     | N/A          | ✅    | [Link](https://fly.io/docs/litefs/speedrun/)                 | 🚀    |
| **MotherDuck**                 | DuckDB                                                       |         |            |              |      |                                                              |      |
| **Neon**                       | PostgreSQL                                                   | GA      |            |              |      |                                                              |      |
| **Nile**                       | PostgreSQL                                                   | Early   |            | Pool         |      | [Link](https://github.com/niledatabase/niledatabase/tree/main/examples) | 👍    |
| **Nhost**                      | PostgreSQL + GQL                                             | GA      |            |              |      |                                                              | 👍    |
| **Prisma**                     | PostgreSQL                                                   | GA      | Vultr      |              | ✅    | [Link](https://github.com/prisma/prisma-examples)            | 🚀    |
| **Supabase**                   | PostgreSQL                                                   |         |            | Pool / HTTP  |      |                                                              |      |
| **SurrealDB**                  | SurrealQL (PSQL-ish)                                         |         |            |              | ✅    | [Link](https://github.com/surrealdb/examples)                | 🚀    |
| **Tembo**                      | PostgreSQL                                                   |         |            |              |      |                                                              |      |
| **Turso**                      | SQLite                                                       | GA      | ?          | Embed + HTTP | ✅    | [Link](https://github.com/tursodatabase/awesome-turso)       | 🚀    |
| **Xata**                       | PostgreSQL                                                   | Early   |            |              |      |                                                              |      |

## Pricing

Note that the "Free Plan" is intended to represent ongoing free resources i.e. not trials or sign-up credits.

|                                              | **Free Plan**                                                | Bill Limits | **First Paid Tier**                                          |
| -------------------------------------------- | ------------------------------------------------------------ | ----------- | ------------------------------------------------------------ |
| **Aurora Serverless v2 (AWS)**               |                                                              |             |                                                              |
| **Azure SQL Serverless**                     |                                                              |             |                                                              |
| **CockroachDB**                              | 10 GiB + 50M RUs / mo.                                       | Yes         | $0.50 / GiB + $0.20 / 1M RUs (over free)                     |
| **D1 (Cloudflare)**                          | 5M RR / day + 100k RW / day + 5 GB                           |             | $5 / mo for 25B RR + 50M RW + 5GB, after $0.001 / M RR + $1.00 / M RW + $0.75 / GB-mo |
| **Gel**                                      | 1/16 vCPU, 1/2 GiB RAM, 1GB storage                          |             | $20 / mo for 1/8 vCPU, 1 GiB RAM, 10GiB storage, 100GiB transfer |
| **Fauna**                                    | 100k TRO + 50k TWO + 500k TCO + 1GB storage + 5 DB + 2 GB / mo egress (@ 1k TRO/s + 250 TWO/s + 1k TCO/s) | ?           | $0.46/M TRO + $2.28/M TWO +  $2.05/M TCO + $1.00/GB/mo storage + $0.20/GB/mo egress (over 10GB) |
| **LiteFS (Fly.io)**                          | 3 GB storage (including VM) + 160 GB egress (per ?)          | ?           | $0.15 per GB / mo + $0.02 per GB egress (over free, min $5 / mo) + optional $0.50/GB / mo for backups |
| **MotherDuck**                               |                                                              |             |                                                              |
| **[Neon](https://neon.tech/pricing)**        | 500 MB, 190 CPU hours                                        |             | $20 / mo = 10 GB, 300 CPU hours                              |
| **[Nile](https://www.thenile.dev/pricing)**  | 1GB storage, 50M query tokens                                |             | $15 / mo = 5GB storage, 150M query tokens                    |
| **[Nhost](https://nhost.io/pricing)**        | 1 GB storage, 5 GB egress                                    |             | $25/mo = 10 GB storage, 50 GB egress + $0.20 / GB add'l storage |
| **[Prisma](https://www.prisma.io/pricing)**  | 1 GB storage, 100k ops, 5MB response, 10s duration           | Yes         | $50/mo = 5 GB storage (+ $1.5 / GB), 100k ops (+ $8 / M), 10 MB response, 20s durtration |
| **[Supabase](https://supabase.com/pricing)** | 500 MB, 5GB bw, 50k MAU                                      |             | $25 / mo =  8GB storage, 250 GB bw + $0.125 / GB + $0.09 / GB bw |
| **SurrealDB**                                | 1 GB storage Limited compute node size                       |             |                                                              |
| **[Tembo](https://tembo.io/pricing/)**       | 10 GB storage, 0.25 vCPU, 1 GB Memory                        |             | $33/mo = 0.5 vCPU · 1Gi mem, 10 Gi storage                   |
| **Turso**                                    | 500 DBs, 9 GB, 1B row reads                                  |             | 10k DBs, 24 GB                                               |
| **[Xata](https://xata.io/pricing)**          | 15 GB storage                                                |             | $20/mo =  15 GB storage + $2 / GB                            |

RUs = CPU + IOPs, mo = month, M = million, k = thousand, RR = rows read, RW = rows written, B = billion, bw = bandwidth

## Runtime Limits

|                                | DB Size            |                | # DBs              |                | Duration                             |
| ------------------------------ | ------------------ | -------------- | ------------------ | -------------- | ------------------------------------ |
|                                | **Default / Free** | **Max / Paid** | **Default / Free** | **Max / Paid** |                                      |
| **Aurora Serverless v2 (AWS)** |                    |                |                    |                |                                      |
| **Azure SQL Serverless**       |                    |                |                    |                |                                      |
| **CockroachDB**                |                    |                |                    |                |                                      |
| **D1**                         | 500 MB             | 2 GB           | 10                 | 50k            | 30 s                                 |
| **Fauna**                      | 1GB                |                | 5 DB               | 100 DB         | Paid: 4k TRO/s + 1k TWO/s + 4k TCO/s |
| **LiteFS**                     |                    |                |                    |                |                                      |
| **MotherDuck**                 |                    |                |                    |                |                                      |
| **Neon**                       |                    |                |                    |                |                                      |
| **Nhost**                      |                    |                |                    |                |                                      |
| **Prisma**                     |                    |                | 10                 | 60             | See above                            |
| **Supabase**                   |                    |                |                    |                |                                      |
| **Turso**                      | 9 GB               | 24 GB          | 500                | 10k            |                                      |
| **Xata**                       |                    | Early          |                    |                |                                      |

## Discussions, Community, and Support

|                                | Ours | Forum                                                        | GitHub                                                       | SO                                                           | Reddit                                                 |
| ------------------------------ | ---- | ------------------------------------------------------------ | ------------------------------------------------------------ | ------------------------------------------------------------ | ------------------------------------------------------ |
| **Aurora Serverless v2 (AWS)** |      |                                                              |                                                              |                                                              |                                                        |
| **Azure SQL Serverless**       |      |                                                              |                                                              |                                                              |                                                        |
| **CockroachDB**                |      | [Forum](https://forum.cockroachlabs.com/) [Slack](https://cockroa.ch/slack) | [GitHub](https://github.com/cockroachdb/cockroach)           | [SO](https://stackoverflow.com/questions/tagged/cockroachdb) | [r/CockroachDB](https://www.reddit.com/r/CockroachDB/) |
| **D1 (Cloudflare)**            |      | [Forum](https://community.cloudflare.com/) [Discord](https://discord.com/invite/cloudflaredev) | [Projects](https://developers.cloudflare.com/d1/reference/community-projects/) | [SO](https://stackoverflow.com/questions/tagged/cloudflare-workers) | [r/CloudFlare](https://www.reddit.com/r/CloudFlare/)   |
| **Fauna**                      |      | [Forum](https://forums.fauna.com/) [Discord](https://discord.com/invite/NHwJFdG2B2) | [Drivers](https://github.com/fauna)                          | [SO](https://stackoverflow.com/questions/tagged/faunadb)     | [r/FaunaDB](https://www.reddit.com/r/FaunaDB/)         |
| **Gel**                        |      |                                                              |                                                              |                                                              |                                                        |
| **LiteFS (Fly.io)**            |      | [Fly.io Forum](https://community.fly.io/)                    | [LiteFS](https://github.com/superfly/litefs)                 |                                                              |                                                        |
| **MotherDuck**                 |      |                                                              |                                                              |                                                              |                                                        |
| **Neon**                       |      |                                                              |                                                              |                                                              |                                                        |
| **Prisma**                     |      |                                                              |                                                              |                                                              |                                                        |
| **Turso**                      |      | [Discord](https://discord.com/invite/turso)                  | [GitHub](https://github.com/tursodatabase)                   | [SO](https://stackoverflow.com/questions/tagged/turso)       |                                                        |
| **Xata**                       |      |                                                              |                                                              |                                                              |                                                        |

## References and Useful Links

- [Vercel Data Latency Tester](https://edge-data-latency.vercel.app/)
- [Article by Lee Robinson from Jan 28, 2023](https://leerob.substack.com/p/databases-serverless-edge)
- [Article by Alex Patterson from June 6, 2023](https://codingcat.dev/post/2023-databases-for-serverless)
- [Comparison by Pritam Barhate from March 29, 2023](https://mobisoftinfotech.com/resources/blog/serverless-database/)
- [Article by Jignesh Solanki from Dec 12, 2021](https://www.simform.com/blog/serverless-databases/)
- [Article by Alex DeBrie from June 20, 2019](https://www.serverless.com/blog/choosing-a-database-with-serverless)
- [7+ Free PostgreSQL Hosting Platforms by Probir Sarkar from Nov 6, 2024](https://dev.to/probir-sarkar/7-free-postgresql-hosting-platforms-for-developers-in-2024-fi5)
- [Serverless Database Query Performance](https://bejamas.com/compare/neon-vs-supabase-vs-xata)
