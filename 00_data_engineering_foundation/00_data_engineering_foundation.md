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

## 3. Is this the right path for me?

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

## 4. My 12-week plan

| Weeks | Focus | What I'll do |
|---|---|---|
| 1-3 | Foundations | SQL (CTEs, window functions), Python basics, pandas |
| 4-6 | First pipelines | Git, local Postgres, API → clean → load script, Docker basics |
| 7-9 | Real tooling | Airflow or Dagster, dbt, data modeling (star schema, lakehouse) |
| 10-12 | Capstone | End-to-end scheduled pipeline with data quality checks, documented on GitHub |

---

## 5. Rules for staying consistent

- Study a little every day; an hour beats one long weekend session
- Write code myself instead of only watching tutorials
- Log what I built each week
- Getting stuck is part of the process, not a sign I'm not cut out for it

---

## 6. Weekly log

| Week | Dates | What I learned / built | What I struggled with |
|---|---|---|---|
| 1 | | | |
| 2 | | | |
| 3 | | | |

---

## 7. Review at the end of the trial

*(Fill in January 2027)*

- What I built:
- What I enjoyed:
- What was hard:
- Decision (continue / adjust / stop):