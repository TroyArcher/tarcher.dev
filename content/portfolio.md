---
title: "Portfolio"
date: 2024-01-10T12:00:00-05:00
draft: false
author: "Troy Archer"
hidemeta: false
comments: false
description: "Troy Archer's software engineering portfolio showcasing projects, skills, and experience."
canonicalURL: "https://tarcher.dev/portfolio/"
disableHLJS: true
disableShare: false
hideSummary: false
searchHidden: false
ShowReadingTime: false
ShowBreadCrumbs: true
ShowPostNavLinks: false
ShowWordCount: false
ShowRssButtonInSectionTermList: false
UseHugoToc: true
showToc: true
TocOpen: false
---

# Portfolio

Senior Software Engineer with expertise in building scalable distributed systems, high-throughput telecommunications platforms, and cloud-native infrastructure.

## About Me

I am Troy Archer, a Senior Software Engineer specializing in backend systems, microservices architecture, and cloud infrastructure. I design and implement reliable software that processes high volume messaging traffic on Amazon Web Services (AWS). I build microservices in Go, Python, and Java. I use Claude Code, Antigravity, and Codex to orchestrate AI agents with custom skills and workflows. I use devcontainers to isolate agent runtimes for security, speed, and automated test execution.

### Technical Expertise

**Languages**
- Go
- Python
- Java
- TypeScript / JavaScript
- Rust
- SQL

**Backend & Architecture**
- Microservices Architecture (Go, Python, Java)
- Java & Spring Boot HTTP Services
- In-House Workflow Systems
- RESTful APIs & gRPC
- Distributed Event Streaming & Queuing (AWS SQS, Kafka, Redis Pub/Sub)
- Retrieval-Augmented Generation (RAG) & Vector Search
- High-Throughput Message Processing

**Databases & Storage**
- PostgreSQL (Amazon RDS)
- Amazon DynamoDB
- Redis
- MongoDB
- Time-series Databases

**Cloud & DevOps**
- Amazon Web Services (AWS: SQS, ECS, EKS, RDS, DynamoDB, Lambda)
- Google Cloud Platform (GCP)
- Docker & Kubernetes (CKA)
- Terraform
- CI/CD Pipelines (GitHub Actions)

**AI Engineering & Agent Orchestration**
- Agent Tooling: Claude Code, Antigravity, Codex
- Agent Orchestration: Skills, Workflows, and Outcome-Focused Prompts
- Runtime Isolation: Devcontainers for Sandboxed Agent Automation and Test Execution

## Professional Experience

### Senior Software Engineer | Bandwidth
*2022 - Present*

- Architect and maintain high-availability backend microservices in Go, Python, and Java on AWS (ECS, EKS, SQS, Lambda) serving millions of daily messaging transactions.
- Lead the technical design and implementation of automated Toll-Free message verification and compliance engines.
- Integrate artificial intelligence and retrieval-augmented generation (RAG) models to detect campaign drift in messaging traffic.
- Reduce system downtime by 80 percent through real-time telemetry, automated alerting, and resilient system design.
- Establish engineering standards, conduct code reviews, and mentor software engineers.

### Software Engineer | Bandwidth
*2020 - 2022*

- Developed Java Spring Boot HTTP applications and REST APIs supporting messaging services and customer management.
- Engineered and maintained an in-house workflow orchestration system to automate multi-step messaging pipelines.
- Built automated CI/CD pipelines, reducing deployment cycle times from hours to minutes.
- Optimized PostgreSQL database schema and indexing, improving query response times by 60 percent.
- Collaborated with cross-functional teams to deliver key product features on schedule.

## Featured Projects

### Society: Turn-Based 4X Strategy Game

**Technologies**: Rust, Godot 4, GDExtension, GDScript, Bincode, Serde

Developed a turn-based 4X strategy game engine with a deterministic simulation core and a Godot 4 presentation layer.

- **Deterministic Simulation Core**: Built an engine-agnostic pure-Rust state machine that processes mutations through a strict command and event pipeline.
- **Autonomous AI & Pathfinding**: Implemented bot AI decision logic and terrain-aware A* pathfinding on an axial hex grid.
- **Verification Tooling**: Created a headless command-line replay runner to guarantee deterministic state parity across test runs.

---

### Handbrake: Telecommunications Message Compliance Engine

**Technologies**: Python, Flask, OpenAI API, LangChain, Vector Database, Docker

Developed an AI-driven compliance engine to detect campaign drift in telecommunications traffic by comparing live message content against registered Toll-Free verification use cases.

- **Vector Search & RAG**: Query vectorized database of use cases to supply context to LLM prompts.
- **Accuracy & Reliability**: Achieved high verification confidence scores and eliminated manual audit overhead.
- **Recognition**: Awarded 2nd place out of 29 team submissions in Bandwidth Hackathon 2025.

---

### Distributed Task Queue System

**Technologies**: Go, Redis, PostgreSQL, Docker, Kubernetes

Built a high-performance distributed task execution engine designed for auto-scaling worker nodes based on queue depth.

- **Fault Tolerance**: Implemented exponential backoff retries and dead-letter queues.
- **Throughput**: Processed over 10 million jobs daily with sub-second execution latency.

---

### Real-Time Analytics Dashboard

**Technologies**: React, TypeScript, Node.js, WebSockets, Time-Series Storage

Created a streaming operational dashboard for real-time monitoring of telecommunications network metrics.

- **Live Streaming**: Leveraged WebSockets to render low-latency metric updates.
- **Incident Reduction**: Reduced mean time to detection for traffic anomalies from hours to minutes.

## Education & Certifications

**Bachelor of Science in Computer Science**
Graduated 2020

**Certifications**:
- AWS Certified Solutions Architect - Associate
- Certified Kubernetes Administrator (CKA)
- Google Cloud Professional Cloud Architect

## Contact

- **Email**: tarcherdev@gmail.com
- **LinkedIn**: [linkedin.com/in/troyharcher](https://www.linkedin.com/in/troyharcher/)
- **GitHub**: [github.com/TroyArcher](https://github.com/TroyArcher)