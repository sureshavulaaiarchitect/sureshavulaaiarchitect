# Suresh Babu Avula

**Enterprise Data & AI Architect** — petabyte-scale data platforms, multi-cloud database engineering, and runtime security for AI agents.

I spend my time on the layer most teams discover too late: the data model underneath a billion-dollar product, the database that has to stay up through a cloud migration, and — lately — the policy plane that decides whether an autonomous agent is allowed to run the tool call it just generated.

Currently enterprise architect for retail AI data platforms at **Impact Analytics**. Previously Innovaccer, FourKites, S&P Global, EY, HP, Citi, IBM.

`Hyderabad, India` · `PostgreSQL · Oracle · ClickHouse · Snowflake · AWS/GCP/Azure` · `AI agent security`

---

## Projects

### [opa-policy-engine](https://github.com/sureshavulaaiarchitect/opa-policy-engine) — runtime security control plane for AI agents

[![License](https://img.shields.io/badge/license-Apache%202.0-blue)](https://github.com/sureshavulaaiarchitect/opa-policy-engine/blob/main/LICENSE)
[![PyPI](https://img.shields.io/badge/PyPI-aegis--anthropic-3775A9?logo=pypi&logoColor=white)](https://pypi.org/project/aegis-anthropic/)
![Recall](https://img.shields.io/badge/attack%20recall-88.7%25-success)
![Chain](https://img.shields.io/badge/chain%20violations-0-success)

An agent framework will happily execute a tool call constructed from a prompt-injected model response. This sits between "the model said so" and "the database was dropped."

Every prompt is scanned, every tool call is authorized against a 10-layer policy pipeline backed by Open Policy Agent, and every decision is written to an ed25519-signed, Merkle-rooted audit chain that a regulator can verify offline. Self-hosted, model-agnostic, tool-agnostic — prompts never leave the deployment.

```python
from sdk.acp_client import Client, DeniedError

acp = Client()

@acp.protect(agent_id="agent_42", tool="db.query")
def query(sql: str) -> list[dict]:
    return db.execute(sql)

query("SELECT name FROM users LIMIT 10")   # runs
query("DROP TABLE users")                  # DeniedError, before execution
```

| | |
|---|---|
| **Architecture** | 19 Python/FastAPI microservices, OPA/Rego policy layer, PostgreSQL + Redis, ES256 service mesh |
| **Measured** | 88.7% attack recall / 98.6% precision across 123 payloads · 0 audit-chain violations · ~150 ms deny path |
| **Resilience** | Fail-closed on auth, tenancy, PII, injection, and policy layers; 16 s recovery under Decision-service chaos kill |
| **Distribution** | 5 PyPI packages (Anthropic, OpenAI, LangChain, Bedrock, offline verifier) · Terraform to a full AWS topology · Apache 2.0 |

Threat model, chaos engineering results, scalability sweep, and the itemized AWS bill are published in the [16-section test report](https://github.com/sureshavulaaiarchitect/opa-policy-engine/tree/main/docs/testing) rather than summarized as claims.

---

<!--
Add 2-3 more repos in the same shape. The template that works:
  what breaks without it → what it does → how it's built → what's measured.
Skip anything with no commits in the last year.
-->

### `project-two` — one-line description

What problem it solves, in two or three sentences. What it's built with. One number that proves it works.

### `project-three` — one-line description

Same shape.

---

## Engineering focus

**Data & database architecture.** End-to-end ownership from business semantics through logical modeling to physical implementation and 24×7 operations. OLTP, OLAP, in-memory, search, and lakehouse workloads — designed together rather than as separate silos.

**Multi-cloud database engineering.** Relational, NoSQL, in-memory, and search stores across AWS, Azure, GCP, OCI, and on-premises. Migrations, HA/DR topology, connection-pool and query-path tuning, reliability engineering practice from scratch.

**Applied AI engineering.** RAG pipelines over operational knowledge (pgvector, ChromaDB, Ollama), MCP servers exposing databases to agents, and the governance layer that makes agentic systems auditable enough to run in a regulated enterprise.

**FinOps.** Workload right-sizing, AI-assisted query optimization, and enterprise EDP/MAP commercial negotiation — roughly $40M in cumulative multi-year cloud spend removed across AWS and Azure programs.

---

## Selected work

| Where | What I owned |
|---|---|
| **Impact Analytics** · 2026– | Data architecture for retail AI products on GCP — high-throughput ingestion and columnar analytics on ClickHouse and OceanBase |
| **Innovaccer** · 2021–2025 | Built the database reliability engineering function; healthcare analytics platform serving hundreds of thousands of concurrent users, Snowflake data products over millions of patient records daily |
| **FourKites** · 2019–2021 | PostgreSQL, Cassandra, and Redis direction for real-time supply-chain visibility on an event-driven architecture; time-series at scale |
| **Ernst & Young** · 2018–2019 | OpenShift platform architecture for the Andhra Pradesh government's e-Pragathi digital-governance program |
| **S&P Global** · 2016–2018 | Fintech-grade database infrastructure and the Helix infrastructure-as-code platform for on-prem-to-cloud migration |
| **HP / Citi / IBM** · 2010–2016 | 100+ Oracle RAC and DR builds; the HPI/HPE corporate separation across multiple datacenters; banking integration programs across APAC, EMEA, Japan, and the US |

---

## Stack

**Databases** PostgreSQL · Oracle · MySQL · MongoDB · Cassandra · Redis · Elasticsearch
**Analytics** Snowflake · BigQuery · Redshift · Databricks · ClickHouse · SingleStore · OceanBase
**Data engineering** dbt · Airflow · Kafka · Delta Lake · Apache Iceberg
**Cloud & platform** AWS · GCP · Azure · OCI · Kubernetes · OpenShift · Terraform · Ansible · Docker
**AI** RAG · MCP servers · LangChain · Ollama · pgvector · ChromaDB · Open Policy Agent
**Observability & FinOps** Prometheus · Grafana · Datadog · Splunk · Apptio Cloudability

MCA, JNTU Hyderabad · AWS Solutions Architect – Associate · Oracle Certified Professional (11g) · PMP · ITIL V3

---

## Contact

Open to conversations about enterprise data architecture, agentic AI security, and cloud cost engineering.

[LinkedIn](https://www.linkedin.com/in/YOUR-LINKEDIN-HANDLE) · [sureshbabuavula@gmail.com](mailto:sureshbabuavula@gmail.com)
