# Chen Junbing | Senior Java Backend Engineer

> 11 years in Java backend · 8 years in the education assessment domain · National Senior Certifications: System Architect & System Analyst

---

## Personal Information

- **Phone / WeChat**: 186 **** 2114
- **Email**: 142****351@qq.com
- **Education**: Beijing Information Science and Technology University · Software Engineering · Bachelor's
- **Experience**: 11 years (Java development)
- **Objective**: Senior Java Backend Engineer
  - Language Flexibility: Open to **Python / Golang** backend roles (Java-centric, transferable engineering skills, quick to ramp up on new languages)
  - Full-Stack Boundary: Open to **backend-leaning hybrid full-stack** (covering admin dashboards and internal tools, not a pure frontend role)
- **Location**: Beijing · Lishuiqiao
- **Preferred City**: Beijing

---

## Core Business Scale

> Scope: The Student Comprehensive Assessment System is deployed **independently per region**; figures below represent **active regions combined**; decommissioned regions are listed separately and excluded.

- **Active Scale**: 8 independently deployed regions · **7,200+ schools** · **13.5M+ users** (12.86M students / 650K+ teachers) · **5M+** currently enrolled students
- **Data Volume**: **1.36B+ evaluation records** accumulated (312M student-side / 1.049B teacher-side, all generated within the Student Comprehensive Assessment System); single-region max **547M records**
- **Peak Throughput**: Per-region peak during **concentrated submission windows** — **120K TPM** (~**2,000 QPS**)
- **Historical Footprint**: The Student Comprehensive Assessment System was previously deployed in the Zunyi (junior high school) region, serving **410+ schools** with **1B+ cumulative evaluation records** (region decommissioned, excluded from active figures above)

---

## Key Strengths

- **Large-Scale Data Governance**: Sustained storage, aggregation, and querying of **1.36B+ evaluation records**; led slow-query and slow-endpoint remediation, achieving order-of-magnitude improvements on statistical query latency.
- **High Concurrency & Performance**: Expert-level in-process caching + Redis multi-layer caching; built a **monitorable thread pool** for resource isolation and async offloading of long-running operations, reliably sustaining peak throughput during concentrated submission windows; hands-on JVM/GC tuning and load-test-driven optimization; restructured batch report generation for significant speedup.
- **High Availability & Observability**: Built a self-developed APM full-link monitoring system (microkernel + plugin architecture) covering all business systems, enabling distributed tracing, thread pool monitoring, and exception/slow-log email alerting; led privacy data encryption initiatives.
- **Architecture Evolution & Collaboration**: Led microservice infrastructure buildout (Spring Cloud Gateway / Nacos / OpenFeign) and DDD shared-component consolidation; served as core Module Owner in a **3–5 person backend team**, driving code standards, design reviews, and tech-sharing sessions; able to read English technical documentation (CET-6).

---

## Work Experience

### Muhua Qingcheng (Beijing) Education Technology Co., Ltd. | Jan 2019 – Present
**Java Developer → Technical Core (Core R&D / Module Owner)**

As Module Owner, drove core business delivery: built **5 business systems** — centered on the **Student Comprehensive Assessment** system and extended to (including full rebuilds and iterative rework) **Primary School Assessment / Vocational Education Assessment / Teacher Evaluation / AI Experimental Class** — plus supporting smaller projects; consolidated shared platform components using **DDD and Clean Architecture**, improving cross-system reuse efficiency; delivered ~**40 requirements/year**, owning ~**40%** as Module Owner.

**High Concurrency & Performance**
- Caching & Async: Introduced in-process caching + Redis multi-layer caching, optimizing response times for **40+ list endpoints**; offloaded long-running exports/report generation to business thread pools, moving them out of the synchronous request path to prevent peak-hour timeouts.
- Thread Isolation: Built a self-developed **monitorable thread pool** component (resource isolation + monitoring), shared by both business systems and APM, preventing slow tasks from blocking core pathways; resolved GC anomalies and deadlocks, improving per-instance throughput and stability.
- Load Testing & Tuning: Henan report — **800K student records** processed in a single-machine batch, measured at ~**5 hours**, validating single-node full-batch feasibility; through index optimization + query refactoring + caching, reduced statistical slow-endpoint latency from **tens of seconds to milliseconds**.
- Batch Speedup: Restructured the report generation pipeline, reducing **single-node total time by ~50%** at equivalent data volume, with support for multi-node parallel sharding for further speedup.

**High Availability & Stability**
- Observability: Built an observability stack covering MySQL / MongoDB / Redis / HTTP tracing, thread pool monitoring, and exception/slow-log email alerting, enabling rapid fault localization.
- Security & Disaster Recovery: Privacy data encryption initiative covering **8.9M+ records**; microservice decomposition improved fault isolation and horizontal scalability, strengthening service governance and graceful degradation.

**AI Engineering (Pre-research)**
- Technical Exploration: Built LLM integration and Function Calling with Spring AI; set up a RAG retrieval-augmented pipeline (document loading / chunking / vector retrieval / QA chain) and Prompt template management — establishing a practical foundation for embedding LLM capabilities into business systems.
- Dev Efficiency: Proficient with **Cursor / Codex** AI coding tools in daily development, feeding LLM capabilities back into the engineering workflow.

### Beijing Jieyi Car Rental Co., Ltd. | Jul 2018 – Jan 2019
**Java Developer (Backend-focused, with frontend responsibilities)**

- Shared Components: Consolidated and maintained team shared libraries; built a standardized **Maven** project skeleton template supporting one-command project scaffolding, standardizing team engineering structure.
- High-Volume Log Storage: Replaced MySQL with **HBase wide-column** storage for vehicle rental operation logs (write-heavy, read-light, massive time-series), designing **salted RowKeys (tenant/vehicle ID + reversed timestamp)** for Region load balancing and efficient time-range retrieval; decoupled from the main transaction path via **async batch writes**, enabling operation audit and trajectory tracing with MySQL hot-data tiered governance.

### Xiaofu Wallet Technology (Beijing) Co., Ltd. | Jul 2015 – May 2018
**Java Developer**

- Workflow Engine Integration: Independently researched **Activiti**, implementing batch-configurable BPM task assignment, executable operations, flow control, comments/attachments, deadlines, and status — deployed in the Jilin Municipal E-Government approval project.
- Payment & Architecture Upgrade: Integrated and maintained **Alipay and WeChat Pay**; implemented **idempotency and deduplication** in payment callbacks and reconciliation file processing, ensuring financial data consistency with zero duplicate entries; migrated from SSI to SSM, unified session management with **Spring Session + Redis**, implemented **OAuth**-based web authentication, consolidating multi-platform login logic and reducing API/page coupling.

### Retail Industry · Career Transition Period | Jul 2014 – Jun 2015
**Non-technical Role**

- Worked in the retail industry after graduation; transitioned into software development in Jul 2015, continuously specializing in Java backend engineering since.

---

## Project Experience

### Student Comprehensive Assessment System (Core, Jan 2019 – Present) | Backend Developer / Module Owner

- **Scale**: Core load-bearing system; the "Core Business Scale" section's active figures represent this system's deployment and data scale; extended to build Primary School Assessment / Vocational Assessment / Teacher Evaluation / AI Experimental Class on this foundation.
- **Background**: Serves education departments and schools, focusing on student and teacher process records, multi-dimensional assessment, and report generation.
- **Responsibilities**: Backend architecture, database schema design, shared component platformization, leading the development of multiple business systems including Assessment and Teacher Evaluation.
- **Technical Highlights**: Multi-dimensional data aggregation queries; batch PDF report generation (**JODConverter + poi-tl**); **QLExpress rule engine** driving assessment algorithms; Redis multi-layer caching + business thread pool async offloading.

### Self-Developed APM Full-Link Monitoring System (Jun 2019 – Present) | Solo Full-Stack Developer

- **Background**: Business systems were evolving from monolithic to distributed, lacking cross-service link observability and a unified alerting framework.
- **Architecture**: Evaluated open-source solutions and designed a "microkernel + plugin extension" architecture, implementing the Agent client, data processing center, management dashboard, and UI; adopted a **push-pull hybrid (Agent active push + central on-demand pull)** data collection model — some deployed regions have no outbound network access and cannot push data, requiring pull-based fallback; covers MySQL / MongoDB / Redis / HTTP links.
- **Tech Stack**: Agent-side data collection via SDK explicit instrumentation; monitoring log/link data transport via **RocketMQ**; data processing center is a self-built service; link data stored in MongoDB; management dashboard and UI built with Vue.
- **Technical Challenges**: Solved **hierarchical nesting and time-sequence alignment** across service links; Agent collection/reporting reuses the self-developed **monitorable thread pool** (resource isolation + runtime metrics monitoring), paired with exception/slow-log email alerting, ensuring monitoring overhead does not slow down business links.
- **Outcome**: Integrated into **15+ systems** (covering Student Assessment / Primary School Assessment / Teacher Evaluation / Vocational Assessment / AI Experimental Class — all business systems), iterated **30+ times**, significantly improving fault localization efficiency in distributed environments.

### Jilin Municipal E-Government Platform (Mar 2017 – May 2018) | Backend Developer

- Municipal e-government project (internet filing portal + government approval portal + dual mobile apps); participated in filing and approval business flows using a **Java + Node.js** dual stack; independently researched **Activiti** workflow engine, implementing batch-configurable task assignment, approval operations, flow control, comments/attachments, deadlines, and status — enabling flexible configuration and rapid reuse of multi-department approval workflows. **Outcome**: Completed the full design and implementation of the configurable approval workflow model; project did not go into production due to client-side factors.

---

## Open Source & Technical Writing

- **Code Repository**: <https://github.com/WilSenwish>
  - [Spring-WebFlux-Learn](https://github.com/WilSenwish/Spring-WebFlux-Learn) — Side-by-side Spring WebMvc / WebFlux implementation of the same business logic, a complete case study for learning WebFlux<br>Link: <https://github.com/WilSenwish/Spring-WebFlux-Learn>
- **Technical Articles**:
  - [Core Philosophical Principles & Methodologies of Software Engineering — Finale (Dao-Fa-Shu-Qi-Shi × 9 Approaches)](https://wilsenwish.github.io/Java-Spring-AI/cppam-of-software-engineering/index.html) — A 5-layer "Dao·Fa·Shu·Qi·Shi" framework × 9 approaches, systematically organizing the philosophical foundations of software engineering<br>Link: <https://wilsenwish.github.io/Java-Spring-AI/cppam-of-software-engineering/index.html>
  - [Cognitive Map of Engineering Wisdom: 53 Laws × 149 Methodologies × Dao-Fa-Shu-Qi-Shi](https://wilsenwish.github.io/Java-Spring-AI/Laws-Theories-Principles-and-Patterns/index.html) — 53 engineering laws × 149 methodologies, drawing a cognitive map of engineering wisdom<br>Link: <https://wilsenwish.github.io/Java-Spring-AI/Laws-Theories-Principles-and-Patterns/index.html>

---

## Technical Skills

- **Expert**: Java (JVM/GC tuning / multi-threaded concurrency), Redis (multi-layer caching · distributed locks), MySQL & MongoDB (index optimization · slow-query governance), Spring Boot
- **Proficient**: Spring Cloud Gateway / Nacos / OpenFeign, RocketMQ (monitoring log/link data transport), Activiti workflow, QLExpress rule engine, Node.js, Vue (frontend assist: admin dashboards and internal tools), AI Coding (Cursor / Codex), Jenkins CI/CD · Maven · Linux · Nginx · Swagger
- **Familiar (Pre-research)**: Dubbo, Spring AI / LLM integration / RAG / Prompt engineering

---

## Education

**Beijing Information Science and Technology University** | Software Engineering | Bachelor's | Sep 2010 – Jun 2014

---

## Certifications

**System Architect** (National Senior) · **System Analyst** (National Senior) · College English Test Band 6 (CET-6)

---

_Resume URL: <https://wilsenwish.github.io/>_
