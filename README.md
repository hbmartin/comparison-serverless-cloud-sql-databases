# Comparing hosts / providers for serverless cloud functions (FaaS) for Python

This document provides a comparison between hosted, serverless (no cost or management to spin down to zero) providers of SQL cloud databases.

Please join our [discussions](https://github.com/hbmartin/comparison-serverless-cloud-sql-databases/discussions) or fix/update information by [editing this doc](https://github.com/hbmartin/comparison-serverless-cloud-sql-databases/edit/main/README.md)!

See also the [Python FaaS Comparison](https://github.com/hbmartin/comparison-hosts-serverless-cloud-function-faas-for-python)

- [DevEx](#devex)
- [Pricing](#pricing)
- [Runtime Limits](#runtime-limits)
- [Other Platform Products](#other-platform-products)
- [Discussions, Community, and Support](#discussions-community-and-support)

## DevEx

|                                       | Dialect | Status    | SDKs                | Local Testing | Docs |
| ------------------------------------- | -------------- | --------- | ------------------------------- | ------------- | ---- |
| Turso                      | SQLite           |        |      |               |      |
| LiteFS (Fly.io)            | SQLite           |        |      |               |      |
| Xata                       | Postgres         |        |      |               |      |
| Neon                       | Postgres         |        |      |               |      |
| D1 (Cloudflare)            | SQLite           |        |      |               |      |
| CockroachDB                | Distributed SQL  |        |      |               |      |
| Aurora Serverless v2 (AWS) | Postgres / MySQL |        |      |               |      |
| MotherDuck                 | DuckDB           |        |      |               |      |
|                            |                  |        |      |               |  |

## Pricing

Note that the "Free Plan" is intended to represent ongoing free resources i.e. not trials or sign-up credits.

|      | **Free Plan** | Bill Limits | **First Paid Tier** |
| ---- | ------------- | ----------- | ------------------- |
|      |               |             |                     |
|      |               |             |                     |
|      |               |             |                     |
|      |               |             |                     |
|      |               |             |                     |
|      |               |             |                     |
|      |               |             |                     |
|      |               |             |                     |
|      |               |             |                     |
|      |               |             |                     |
|      |               |             |                     |

reqs = requests, m = million, mo = month, s = seconds, mem = memory, k = thousand, ms = milliseconds

## Runtime Limits

AWS allocates 1 vCPU per 1,769 MB of memory configured.



## Discussions, Community, and Support

|      | Ours | Forum | GitHub | SO   | Reddit |
| ---- | ---- | ----- | ------ | ---- | ------ |
|      |      |       |        |      |        |
|      |      |       |        |      |        |
|      |      |       |        |      |        |
|      |      |       |        |      |        |
|      |      |       |        |      |        |
|      |      |       |        |      |        |
|      |      |       |        |      |        |
|      |      |       |        |      |        |
|      |      |       |        |      |        |

## References and Useful Links

- [Comparison by Brecht De Rooms from Feb 6th, 2020](https://fauna.com/blog/comparison-faas-providers)
