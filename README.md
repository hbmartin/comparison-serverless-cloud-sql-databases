# Comparing hosts / providers for serverless cloud functions (FaaS) for Python

This document provides a comparison between hosted, serverless (no cost or management to spin down to zero) providers of SQL cloud databases.

Please join our [discussions](https://github.com/hbmartin/comparison-serverless-cloud-sql-databases/discussions) or fix/update information by [editing this doc](https://github.com/hbmartin/comparison-serverless-cloud-sql-databases/edit/main/README.md)!

See also the [Python FaaS Comparison](https://github.com/hbmartin/comparison-hosts-serverless-cloud-function-faas-for-python)

- [DevEx](#devex)
- [Pricing](#pricing)
- [Runtime Limits](#runtime-limits)
- [Discussions, Community, and Support](#discussions-community-and-support)

## DevEx

|                                       | Dialect | Status    | Cloud | Cnxn | OSS | Examples         | Docs |
| ------------------------------------- | -------------- | --------- | ------------------------------- | ---- | ------------------------------------- | ------------------------------------- | ------------------------------------- |
| **Aurora Serverless v2 (AWS)** | PostgreSQL / MySQL |        | AWS |  |  |      |      |
| **Azure SQL Serverless** |  | | Azure |  |  | | |
| **CockroachDB** | Distributed SQL ([PG compat.](https://www.cockroachlabs.com/docs/stable/postgresql-compatibility)) | GA | AWS / GCP | Pool | ✅ | [Link](https://www.cockroachlabs.com/docs/stable/example-apps) | 🚀 |
| **D1**        | SQLite           |        | Cloudflare |  |  |      |      |
| **Fauna** | FQL | | | | | | |
| **LiteFS**        | SQLite           |        | Fly.io |  |  |      |      |
| **MotherDuck**             | DuckDB           |        |        |        |        |      |      |
| **Neon**                   | PostgreSQL |        |        |        |        |      |      |
| **PlanetScale** | MySQL |        |        |        |        |      |  |
| **Render** | PostgreSQL | | | | | | |
| **Supabase** | PostgreSQL | | | Pool / HTTP | | | |
| **Turso**                  | SQLite           |        |        |        |        |      |      |
| **Xata**                   | PostgreSQL |        |        |        |        |      |      |

## Pricing

Note that the "Free Plan" is intended to represent ongoing free resources i.e. not trials or sign-up credits.

|                                | **Free Plan**            | Bill Limits | **First Paid Tier**                      |
| ------------------------------ | ------------------------ | ----------- | ---------------------------------------- |
| **Aurora Serverless v2 (AWS)** |                          |             |                                          |
| **Azure SQL Serverless**       |                          |             |                                          |
| **CockroachDB**                | 10 GiB + 50M RUs per mo. | Yes         | $0.50 / GiB + $0.20 / 1M RUs (over free) |
| **D1 (Cloudflare)**            |                          |             |                                          |
| **Fauna**                      |                          |             |                                          |
| **LiteFS (Fly.io)**            |                          |             |                                          |
| **MotherDuck**                 |                          |             |                                          |
| **Neon**                       |                          |             |                                          |
| **PlanetScale**                |                          |             |                                          |
| **Turso**                      |                          |             |                                          |
| **Xata**                       |                          |             |                                          |

RUs = CPU + IOPs, mo = month, M = million

## Runtime Limits

AWS allocates 1 vCPU per 1,769 MB of memory configured.

## Discussions, Community, and Support

|                                | Ours | Forum                                                        | GitHub                                             | SO                                                           | Reddit                                                 |
| ------------------------------ | ---- | ------------------------------------------------------------ | -------------------------------------------------- | ------------------------------------------------------------ | ------------------------------------------------------ |
| **Aurora Serverless v2 (AWS)** |      |                                                              |                                                    |                                                              |                                                        |
| **Azure SQL Serverless**       |      |                                                              |                                                    |                                                              |                                                        |
| **CockroachDB**                |      | [Forum](https://forum.cockroachlabs.com/) [Slack](https://cockroa.ch/slack) | [GitHub](https://github.com/cockroachdb/cockroach) | [SO](https://stackoverflow.com/questions/tagged/cockroachdb) | [r/CockroachDB](https://www.reddit.com/r/CockroachDB/) |
| **D1 (Cloudflare)**            |      |                                                              |                                                    |                                                              |                                                        |
| **Fauna**                      |      |                                                              |                                                    |                                                              |                                                        |
| **LiteFS (Fly.io)**            |      |                                                              |                                                    |                                                              |                                                        |
| **MotherDuck**                 |      |                                                              |                                                    |                                                              |                                                        |
| **Neon**                       |      |                                                              |                                                    |                                                              |                                                        |
| **PlanetScale**                |      |                                                              |                                                    |                                                              |                                                        |
| **Turso**                      |      |                                                              |                                                    |                                                              |                                                        |
| **Xata**                       |      |                                                              |                                                    |                                                              |                                                        |

## References and Useful Links

- [Article by Lee Robinson from Jan 28, 2023](https://leerob.substack.com/p/databases-serverless-edge)
- [Article by Alex Patterson from June 6, 2023](https://codingcat.dev/post/2023-databases-for-serverless)
- [Comparison by Pritam Barhate from March 29, 2023](https://mobisoftinfotech.com/resources/blog/serverless-database/)
- [Article by Jignesh Solanki from Dec 12, 2021](https://www.simform.com/blog/serverless-databases/)
- [Article by Alex DeBrie from June 20, 2019](https://www.serverless.com/blog/choosing-a-database-with-serverless)
- 
