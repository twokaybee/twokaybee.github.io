+++
date = 2026-08-24
weight = 1
title = "Portfolio | Sanoj Kumar C P"
description = "Portfolio of a Staff Backend Engineer specializing in Go, Elixir and Distributed Systems"
+++

# Sanoj Kumar C P
## Staff Backend Engineer | Go & Elixir | Distributed Systems

I am a Staff Backend Engineer with 20 years of software engineering experience, specializing in backend architecture, distributed systems and enterprise platform modernization. My strongest recent experience is in Go, where I led the transformation of a legacy global travel booking platform into eighteen independently deployable microservices. I also independently designed and developed an operational back-office application using Elixir and Phoenix, integrating it with the existing Go platform.

My engineering experience spans microservices, event-driven architectures, asynchronous messaging, distributed workflows, financial integrations, database synchronization and third-party service integrations. I work across the complete engineering lifecycle, from architecture and technical planning to implementation, integration and production delivery.

Alongside my backend engineering work, I actively explore AI application and agent development across the Go and Elixir ecosystems. My current toolkit includes LangChainGo, CloudWeGo Eino, ReqLLM and Jido, with Ollama and locally hosted models for experimentation. I use tools such as Cursor and Claude Code to accelerate development while retaining responsibility for architecture, implementation decisions, code review and testing.

I also bring extensive experience in technical leadership, having led cross-functional teams involving backend and frontend developers, QA engineers, database administrators and DevOps engineers.

<p>&nbsp;</p>

---

<p>&nbsp;</p>

## Projects & Experience

### Tathkarah Travels
**Title:** Principal Architect & Fractional CTO (Global Booking Platform)

I led the architectural modernization of a legacy Global Distribution System into eighteen independently deployable Go microservices. The migration was executed in phases, allowing the existing booking platform to continue operating without downtime or data loss.

I designed and developed core backend services, shared libraries and middleware, introducing distributed workflow patterns including Saga, idempotency, retries and circuit breakers. I implemented asynchronous messaging using NATS and Kafka, with gRPC and Protocol Buffers for inter-service communication.

The platform integrated with global travel suppliers including Travelport/Galileo, RezLive and Juniper, as well as direct airline APIs. I also worked on payment integrations supporting MADA, KNET, cards and Apple Pay.

Another major responsibility was the development of a centralized management and configuration platform driven by a custom Go-based Business Process Management engine and finite state machine. Configuration and operational data were managed through MongoDB and Redis, allowing business operations to control workflows without hardcoding every change into the services.

My responsibilities also included architecture decisions, technical roadmaps, engineering standards, mentoring and coordinating technical delivery.

**Stack:** Go, Microservices, NATS, Kafka, gRPC, Protocol Buffers, MongoDB, PostgreSQL, Redis, Flutter, AWS

<p>&nbsp;</p>

---

<p>&nbsp;</p>

### Tathkarah Travels
**Title:** Elixir/Phoenix Backend Developer (Separate Contract)

I independently designed and developed an operational back-office application using Elixir and Phoenix, integrating it with the existing Go-based travel platform.

The application provides operational configuration modules covering suppliers, tenants, currencies, exchange rates, promotions, deals, booking configurations, payment gateways, service charges, airlines and airports.

I implemented two-way booking synchronization and configuration publishing between the Phoenix application and the Go platform using NATS and Go data pipelines. I also configured Broadway pipelines to handle NATS and Kafka messaging.

For background processing, I implemented Oban jobs to enrich missing hotel information by retrieving data from the RezLive API when the Go platform reported a HOTEL_NOT_FOUND event. The application uses PostgreSQL and Ecto for persistence, with Zoi for validation.

**Stack:** Elixir, Phoenix, Ecto, Broadway, Oban, Zoi, NATS, Kafka, PostgreSQL, MongoDB, Redis, RezLive API, Go

<p>&nbsp;</p>

---

<p>&nbsp;</p>

### Rockchain
**Title:** Technical Consultant (Decentralized Data Management Platform)

I contributed to a decentralized data management platform focused on digital asset tracking and secure peer-to-peer data exchange.

My primary work involved Go-based synchronization, discovery and registry services using Syncthing protocols. I worked on the services responsible for discovering decentralized nodes and coordinating data exchange between them. I also implemented Ethereum-based authorization logic and contributed to the supporting cloud infrastructure and secure desktop client integration.

**Stack:** Go, Syncthing, Ethereum, Node.js, Vue.js, Electron, Kubernetes, GCP

<p>&nbsp;</p>

---

<p>&nbsp;</p>

### SOD Technologies Pvt Ltd.
**Title:** Technical Lead (Enterprise ERP & Financial Integrations)

I led the customization and integration of the iDempiere Business Suite for enterprise clients. My work included integrating enterprise platforms with core banking systems such as Axis Bank and SBI, developing financial transaction workflows and building custom point-of-sale interfaces.

I also engineered data synchronization pipelines for distributed operations, including transactional data replication between remote locations and central systems. Additional work included automated document ingestion using Tesseract OCR.

I was responsible for technical architecture, integration design and coordinating engineering delivery.

**Stack:** Java, iDempiere, OSGi, PostgreSQL, RabbitMQ, ActiveMQ, Scriptella, Tesseract OCR

<p>&nbsp;</p>

---

<p>&nbsp;</p>

### Assyst International Pvt Ltd.
**Title:** Module Lead (Intuit Mobile Banking)

I worked on the FI Builder Engine for the Intuit mobile banking platform. I designed a metadata-driven application generation framework that used financial institution configurations to programmatically generate customized mobile web applications and financial service modules.

The work focused on automating application scaffolding and reducing repetitive development effort for financial institution deployments.

**Stack:** Java, Struts, XML, Intuit Tools, Mobile Banking

<p>&nbsp;</p>

---

<p>&nbsp;</p>

### Hummingbird Computer Software LLC
**Title:** Architect & Lead Software Engineer (Enterprise Application Frameworks)

I conceptualized and developed iBForte, a custom Java rapid application development framework designed to simplify enterprise application development and overcome limitations in legacy Oracle D2K environments.

I also served as Lead Systems Architect for an enterprise document management system, working on document processing, hierarchical storage, document locking and concurrency controls.

**Stack:** Java, Swing, RMI, RabbitMQ, Oracle DB, MySQL, Framework Development

<p>&nbsp;</p>

---

<p>&nbsp;</p>

### Early Career Engineering Roles (2005–2008)
**Title:** Lead Software Engineer (Megahands) & Senior Developer (ITECSOFT)

At Megahands Infotech, I developed workflow functionality for collaborative scientific manuscript editing and engineered a programmatic PDF rendering pipeline for generating publication-ready documents.

At ITECSOFT, I developed ERP, financial and contract management applications, including business workflows covering project budgets and financial reporting. I also worked on enterprise application development and Arabic-localized deployments for UAE clients.

**Stack:** Java, J2EE, Struts, VB6, Oracle DB, MySQL, XML, PDF Generation

<p>&nbsp;</p>

---

<p>&nbsp;</p>

### AI Application & Agent Engineering
**Title:** Independent Technical Exploration

I am actively exploring the engineering of AI-powered applications, LLM integrations and agent-based systems, with a focus on Go and Elixir rather than model training or traditional machine learning.

In Go, I work with LangChainGo and CloudWeGo Eino to understand tool calling, agent workflows, orchestration and integration of language models into backend applications.

In Elixir, I explore ReqLLM and Jido for LLM integration, structured interactions and agent-based application development. I also experiment with Ollama and locally hosted models to evaluate inference behaviour and build application workflows without relying entirely on hosted AI services.

My focus is on understanding the underlying frameworks and building practical tools that connect language models with real application logic and backend systems.

**Stack:** Go, Elixir, LangChainGo, CloudWeGo Eino, ReqLLM, Jido, Ollama