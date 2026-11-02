+++
title = "2kb.in"
paginate_by = 10
sort_by = "date"
+++

## The Architecture of Reliability

My name is Sanoj Kumar. For over two decades, my engineering journey has been driven by a fascination with building reliable software, solving difficult backend problems, and making complex systems work together. Today, I position myself as a Staff Backend Engineer specializing in Go, Elixir, and distributed systems. My strongest recent experience is in Go, where I have spent eight years designing and modernizing enterprise backend platforms. Along the way, I have worked with event-driven architectures, asynchronous messaging, distributed workflows, financial systems, and large-scale third-party integrations. For me, the real engineering challenge has never been just choosing a language. It has been understanding the problem, finding the right architecture, and building something that can evolve without losing reliability.

### The Shift to Independence & Global Scale

Eight years ago, I moved into independent consulting, taking on deeper architectural responsibilities and working across complex systems in the travel technology domain.

During my engagement with **Tathkarah Travels**, I led the modernization of a legacy Global Distribution System into eighteen independently deployable microservices written in Go. This involved breaking down established booking workflows, designing core backend services and shared libraries, and introducing patterns such as Saga, idempotency, retries, and circuit breakers. I built asynchronous communication and event-driven workflows using NATS and Kafka, with gRPC and Protocol Buffers for inter-service communication. The platform integrated with global travel suppliers, airlines, and payment gateways.

This was not simply a rewrite. It was a phased modernization of a live business platform, where existing booking operations had to continue while the new architecture evolved alongside them.

Alongside that work, I took on a separate contract to design and develop an operational back-office application using **Elixir and Phoenix**. It integrated directly with the existing Go platform, providing operational configuration, booking synchronization, and event-driven workflows. Using NATS, Kafka, Broadway, and Oban, I connected the Phoenix application with Go services and background processing pipelines. The application also included hotel data enrichment through the RezLive API. It was an opportunity to apply Elixir's strengths to a real operational system while working across two different backend ecosystems.

My earlier engagement with **Rockchain** took me into decentralized data management. Working primarily with Go, I contributed to peer-to-peer synchronization, discovery, and registry services built around Syncthing protocols. I also implemented Ethereum-based authorization logic and contributed to the supporting infrastructure for secure decentralized data exchange.

### The Enterprise Foundations

Before moving into independent consulting, my proving ground was enterprise software, where complex business requirements meet established systems and demanding integration challenges.

At **SOD Technologies**, I served as Technical Lead, working on the iDempiere Business Suite and enterprise ERP customizations. I led integrations between business platforms and core banking systems, including Axis Bank and SBI, and worked on financial transaction processing, point-of-sale systems, database synchronization, and OCR-based document ingestion. These projects strengthened my understanding of financial workflows, data integrity, and the importance of reliable integrations.

At **Assyst International**, I worked on the FI Builder Engine for Intuit mobile banking, developing a metadata-driven framework that generated customized mobile web applications and financial service modules.

Earlier, at **Hummingbird Computer Software**, I conceptualized and built iBForte, a Java-based rapid application development framework. I also worked on the architecture of an enterprise document management system, addressing document processing, locking, and concurrency.

My foundational years at **Megahands** and **ITECSOFT** involved enterprise ERP, financial and contract management applications, database-driven systems, and programmatic PDF generation. These experiences gave me a broad understanding of software engineering, from business workflows and data models to application architecture and system integration.

### Beyond Traditional Backend Engineering: AI Agents & Distributed Systems

My interest in backend engineering continues to evolve alongside the emergence of AI-powered applications. Rather than approaching AI purely from a machine learning perspective, I am particularly interested in the engineering challenges of building applications, agents, and tools around language models.

I actively explore this space across both Go and Elixir. In Go, I work with **LangChainGo** and **CloudWeGo Eino**, exploring tool calling, agent workflows, orchestration, and the integration of language models into backend services. In the Elixir ecosystem, I explore **ReqLLM** and **Jido**, working with LLM integrations, structured tool interactions, and agent-based application design.

My local development environment includes **Ollama** and locally hosted models, allowing me to experiment with model behaviour, inference performance, and application workflows without depending entirely on hosted AI services. I also use development tools such as Cursor and Claude Code to accelerate implementation, while keeping architecture decisions, code review, and testing firmly within my engineering workflow.

Alongside these explorations, I continue to investigate distributed systems beyond conventional backend platforms through personal experiments involving UAV robotics, real-time telemetry, and edge networking. Technologies such as MAVLink, Zenoh, and PX4 SITL offer a different perspective on communication, state synchronization, and coordination between software and physical systems.

Whether I am modernizing an enterprise platform, building distributed services in Go, exploring Elixir, or developing AI-powered tools and agents, my underlying interest remains the same: understanding complex systems and engineering reliable solutions around them.