# 00 | Data Engineering Foundation

> **Started:** 9 October 2026
> **Target checkpoint:** January 2027
> **Background:** Data Analyst, self-taught in tech, moving into Data Engineering

This is the starting point of my learning log. Before writing any pipeline code, I want to be clear on three things: **who a data engineer is**, **what the job feels like in real companies**, and **whether this is the right path for me**.

---

## 1. Who is a Data Engineer?

A data engineer builds and looks after **data pipelines**, the flow of data from where it is created to where it is used.

In my own words: a data engineer connects two or more systems and sets things up so data moves from the sources into the destination **automatically**, without someone copying it by hand.

The part that is easy to miss is that the goal is not just *moving* data. It is moving it **reliably**:

- **On time**: it arrives when people expect it
- **Correct**: it matches the source and the business rules
- **Hands-off**: it runs without manual effort

### How this differs from a Data Analyst (where I'm coming from)

| | Data Analyst | Data Engineer |
|---|---|---|
| Focus | Using data to answer questions | Making data available and trustworthy |
| Typical output | Dashboards, reports, insights | Pipelines, data models, warehouses/lakehouses |
| Main tools | SQL, BI tools, Excel, some Python | SQL, Python, orchestration, cloud, dbt/Spark |
| Success looks like | A decision gets made | The data is there, correct and on time |

As an analyst I was the person *receiving* the data. Now I'm learning to build what delivers it. Having been on the receiving end, I know what bad data looks like when it lands.

---

## 2. What the job feels like in real companies

Day to day, the work splits into two modes.

### Build mode
Planned work where I design and create something new.
- Designing and building new pipelines
- Creating data models (how tables are structured and related)
- Updating and extending the lakehouse/warehouse
- Adding new data sources

### Fix mode
Reactive work where something is wrong and people are waiting.
- A pipeline failed overnight
- Numbers don't match between two systems
- Someone upstream changed a column, a schema or a file format
- Data arrived late, duplicated or incomplete

A lot of the real job is **fix mode**. Writing a pipeline is one skill. Keeping it running when the world changes around it is the bigger one.

### Things I expect to deal with often
- Schema changes from upstream teams
- Late or missing files
- Duplicate records
- Slow queries and rising costs
- Explaining to non-technical people why the numbers look off

---

## 3. How data moves: flow vs pipeline structure

These are two views of the same thing. The **data flow** is *what happens to the data*. The **pipeline structure** is *how that flow is built and run automatically*.

### View 1: The data flow (concept)

```
Sources → Ingest/Extract → Raw storage → Transform → Load/Serve → Consumers
                 (orchestration + monitoring across all steps)
```

| Stage | What happens |
|---|---|
| **Sources** | Databases, APIs, CSV/Excel files, SaaS tools, event streams, logs |
| **Ingest / Extract** | Pulling data out of the source, in batches or continuously (ingest and extract are basically the same step) |
| **Raw storage** | Data saved exactly as it arrived (bronze layer in a lakehouse). Keeping the raw copy means I can reprocess if something goes wrong |
| **Transform** | Cleaning and reshaping: remove duplicates, fix types, handle nulls, join tables, apply business rules (silver and gold layers) |
| **Load / Serve** | Final data goes into target tables, such as a warehouse or gold layer, shaped by data models like star schemas |
| **Consumers** | Analysts, dashboards, data scientists, applications. This is where I used to sit |

**ETL vs ELT:** in ETL, data is transformed *before* loading. In ELT, it's loaded raw first and transformed inside the warehouse (usually with SQL and dbt). ELT is very common in modern cloud setups.

### View 2: The pipeline structure (how it's built)

Each stage of the flow becomes a **task**, and tasks are linked into a **DAG** (directed acyclic graph): steps with a clear order and no loops.

```
extract_orders → load_raw_orders → clean_orders → build_sales_table → data_quality_check
```

Boxes are tasks, arrows are dependencies ("don't start until the previous step succeeds"), and the whole chain runs on a schedule. Tools like Airflow or Dagster manage this.

What the structure adds on top of the flow:

- **Scheduling:** when it runs, or what triggers it
- **Dependencies:** what must finish before the next step starts
- **Retries and alerts:** what happens when a task fails
- **Idempotency:** running the same job twice doesn't create duplicates
- **Backfills:** re-running for past dates when something was wrong
- **Logging and monitoring:** knowing what ran, when, and whether the data was correct

**Restaurant analogy:** the flow is "ingredients → prep → cooking → plating → table". The pipeline structure is the kitchen's system: who does which step, in what order, what happens if the oven breaks, and how to avoid cooking the same order twice.

---

## 4. Is this the right path for me?

**Why it fits**
- I already know SQL and how messy real data is
- I understand what analysts and stakeholders need from data
- I like the idea of building systems that run on their own
- Much of the work is practical and learned by building

**Where it will stretch me**
- Coding. I'm not yet strong here and my background is self-taught
- Unfamiliar tools: orchestration, cloud platforms, Docker, Git
- Debugging. Fix mode means reading errors and tracing problems calmly

**Honest take:** this will stretch me, and that's fine. Most of the coding in data engineering is practical (Python and SQL for moving and transforming data) rather than puzzle-style. Consistency matters more than talent here.

**Decision:** I'm committing to a trial period from **9 Oct 2026 to Jan 2027**. At the end I'll review honestly: *Did I enjoy the building? Did the debugging frustrate me or interest me? Do I want to keep going?*

---

## 5. My 12-week plan

| Weeks | Focus | What I'll do |
|---|---|---|
| 1-3 | Foundations | Advanced SQL (CTEs, window functions), Python basics, pandas |
| 4-6 | First pipelines | Git, local Postgres, API → clean → load script, Docker basics |
| 7-9 | Real tooling | Airflow or Dagster, dbt, data modeling (star schema, lakehouse) |
| 10-12 | Capstone | End-to-end scheduled pipeline with data quality checks, documented on GitHub |

---

## 6. Rules for staying consistent

- Study a little every day; an hour beats one long weekend session
- Write code myself instead of only watching tutorials
- Log what I built each week
- Getting stuck is part of the process, not a sign I'm not cut out for it

---

## 7. Weekly log

| Week | Dates | What I learned / built | What I struggled with |
|---|---|---|---|
| 1 | | | |
| 2 | | | |
| 3 | | | |

---

## 8. Review at the end of the trial

*(Fill in January 2027)*

- What I built:
- What I enjoyed:
- What was hard:
- Decision (continue / adjust / stop):
