+++
title = "2kb.in"
paginate_by = 10
sort_by = "date"
+++

## The Architecture of Reliability

My name is Sanoj Kumar. For over two decades, my engineering journey has been defined by a single driving pursuit: building highly critical distributed systems that simply do not fail. Operating as a Principal Backend Architect and Fractional CTO, my technical toolkit is anchored by a dual mastery: twelve years of deep enterprise Java engineering combined with eight years scaling high-throughput, event-driven microservices in Go. But the real story is not just about the languages I write; it is about untangling legacy bottlenecks, resolving complex interoperability challenges, and architecting solutions designed for the long haul.

### The Shift to Independence & Global Scale
Eight years ago, I transitioned into independent consulting, a move that allowed me to take ownership of deep architectural challenges across diverse, global domains. 

During my most recent engagement at **Tathkarah Travels**, which I successfully wrapped up recently, I was tasked with dismantling a monolithic legacy Global Distribution System. I completely replaced the core from the ground up with a highly resilient platform of eighteen independent microservices written in Go, woven together by an asynchronous NATS messaging fabric and gRPC. Crucially, to support business operations while the core was being rewritten, I strategically deployed a highly customizable Java/Spring Boot framework to rapidly modernize the legacy back-office. This dual-track strategy allowed us to sustain massive real-time booking volumes for mobile-first clients and execute a seamless, zero-downtime enterprise migration under unstable network conditions.

During my work with **IXXO/Rockchain**, I ventured deep into decentralized data management. Taking technical ownership of the peer-to-peer networking layer, I optimized the existing Syncthing and Ethereum infrastructure to meet rigorous enterprise-grade requirements. By engineering and integrating Proof of Authority (PoA) and Proof of Concept (PoC) authorization logic, I enhanced the existing system's stability, delivering a production-ready infrastructure for unalterable digital asset tracking and secure enterprise file traceability.

### The Enterprise Foundations
Before branching out independently, my proving ground was the enterprise sector, where complex business requirements meet rigid legacy systems. 

At **SOD Technologies**, I served as Technical Lead, where I spearheaded OSGi-compliant Java plugin architectures and iDempiere Business Suite customizations for global clients. My work there was defined by solving high-stakes integration challenges; notably, I enabled seamless payroll processing for the Spices Board of India by deeply integrating Axis Bank and SBI payment gateways, while also architecting robust, real-time database synchronization and Tesseract-based OCR ingestion pipelines.

My passion for building foundational developer tools really took shape earlier in my career. At **Assyst International**, I engineered an automated scaffolding engine that extracted metadata directly from Intuit QuickBooks to programmatically generate custom mobile banking applications. Prior to that, as the sole original architect at **Hummingbird Computer Software**, I conceptualized and built "iBForte"—a custom Java-based RAD library designed to bypass the limitations of legacy Oracle D2K paradigms. These roles solidified my focus on automating workflows, accelerating development lifecycles, and creating robust, custom data grids. 

My foundational years at **Megahands** and **Global Engineering Systems LLC** further sharpened my ability to solve deep, cross-runtime interoperability challenges. Whether I was building bidirectional ActionScript-Java event layers for the UAE Yellow Pages, or writing complex J2EE workflow logic and custom programmatic PDF rendering pipelines for scientific peer-review platforms, I learned to make disparate systems communicate flawlessly.

### Beyond the Enterprise: The Edge and the Air
Today, my passion for resilient architecture extends beyond enterprise backends. I actively research and build personal sandbox projects focused on UAV robotics and real-time telemetry. 

Using Rust, MAVLink, the Zenoh protocol, and PX4 SITL, I explore how modern edge-networking and decentralized data distribution apply to real-world state synchronization and drone control. It is a hands-on environment that keeps me at the bleeding edge of distributed systems—where software logic meets physical hardware.