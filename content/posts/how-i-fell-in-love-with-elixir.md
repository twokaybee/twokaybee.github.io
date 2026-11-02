+++
title = "How I Fell in Love with Elixir"
date = 2026-10-17
description = "From building Go microservices to discovering Elixir and Phoenix, a practical account of how the BEAM ecosystem changed the way I think about backend development."

[taxonomies]
tags = ["Elixir", "Phoenix", "Backend", "Distributed Systems", "Software Engineering"]
+++

I have spent a good part of my career building backend systems. Over the years, I have worked with Java, Go, distributed architectures, microservices, message brokers, and the usual collection of technologies that come with building enterprise applications.

Go has been one of my favourite tools for backend engineering. I like its simplicity, its performance, and the way it encourages developers to build straightforward systems without unnecessary complexity.

So, when I started working with Elixir, I wasn't looking for another language to fall in love with. I was looking for a way to get a job done.

What started as a practical requirement eventually became one of the most interesting experiences of my engineering career.

### It Started with a Real Project

My introduction to Elixir wasn't through a tutorial, a conference talk, or a weekend experiment. It came from an actual project.

I was working on a travel platform whose core backend was already built around Go microservices. The platform had accumulated a considerable amount of operational functionality over time, and there was a need for a separate back-office application to manage suppliers, tenants, currencies, exchange rates, promotions, booking configurations, payment gateways, and other operational data.

I decided to build that application using Elixir and Phoenix.

This was a separate piece of work from the Go platform. It needed to integrate with the existing services, communicate through NATS and Kafka, and keep operational data synchronized across different parts of the system.

I already understood the architectural problems. What I didn't know yet was how I would approach them in Elixir.

And that was where things got interesting.

### The First Surprise: Elixir Thinks Differently

Coming from Go, I was used to explicit control over concurrency, goroutines, channels, interfaces, and error handling.

Elixir introduced me to a different way of thinking.

Pattern matching quickly became one of the things I appreciated most. Instead of writing layers of conditional logic to inspect values and decide what to do next, I could express intent directly through function clauses and matching.

The functional programming model also took some adjustment. Immutability is not just a language feature you occasionally use. It influences how you structure data transformations, compose functions, and reason about application behaviour.

At first, some of these ideas felt unfamiliar. But after spending time with the language, I began to appreciate how much clarity they brought to application code.

Elixir encourages you to describe what should happen rather than constantly managing how every operation changes shared state.

That was a refreshing change.

### The BEAM: A Different Approach to Concurrency

The real turning point for me was understanding the BEAM.

Elixir runs on the Erlang virtual machine, which was designed for systems that need to remain responsive and available even when individual processes fail.

The lightweight process model is particularly interesting. These are not operating-system threads. They are isolated processes managed by the BEAM, communicating through message passing.

Coming from Go, I naturally compared this with goroutines and channels.

Both ecosystems provide excellent concurrency primitives, but they approach the problem differently. Go gives you goroutines and channels as building blocks. Elixir gives you lightweight isolated processes, message passing, and a runtime designed around supervision and fault tolerance.

The important part is not simply that you can run thousands of processes. It is how the runtime encourages you to isolate failures and design systems that can recover from them.

This led me to another important concept: **let it crash**.

It doesn't mean writing careless code or ignoring errors. It means recognizing that failures are inevitable and designing the system so that a failed process does not necessarily bring down everything around it.

Supervisors can monitor processes and restart them according to defined strategies. That changes the way you think about reliability.

Instead of trying to prevent every possible failure inside one large execution flow, you can isolate responsibilities and define how the system should recover.

For someone who has spent years thinking about distributed systems and production reliability, that was particularly appealing.

### Phoenix: More Than Just Another Web Framework

Then came Phoenix.

I have worked with plenty of web frameworks over the years, so I wasn't expecting the framework itself to be the reason I would enjoy Elixir.

But Phoenix fits naturally into the language's programming model.

Its controller and context structure provides a clean way to organize application responsibilities. Ecto brings a structured approach to data access and changesets. The functional approach encourages explicit data flow instead of hiding behaviour behind layers of mutable state.

For my back-office application, Phoenix gave me a productive foundation without forcing me into an unnecessarily complicated architecture.

I built operational modules, validations, database interactions, and integrations with the existing Go services. Ecto handled PostgreSQL persistence, while Zoi provided validation in the application layer.

The experience made me appreciate how well the pieces of the ecosystem fit together.

### Broadway and Oban: The Ecosystem Starts Making Sense

The project also gave me an opportunity to explore some of the tools that make Elixir particularly attractive for backend systems.

**Broadway** became part of the integration architecture. I configured pipelines to consume messages from NATS and Kafka, allowing the application to participate in the event-driven workflows already used by the Go platform.

What I liked was the way Broadway lets you structure message processing as a pipeline. It provides abstractions for concurrency, batching, acknowledgements, and handling failures without requiring you to build all those mechanisms yourself.

Then there was **Oban**.

One of the requirements involved enriching hotel information when the Go booking system encountered a `HOTEL_NOT_FOUND` event. The Elixir application would receive the event and perform the required hotel enrichment by calling the RezLive API.

This was a natural fit for background job processing.

Oban provides persistent jobs, retries, scheduling, and other useful capabilities without requiring a separate job-processing infrastructure for every application.

These weren't isolated experiments. They were pieces of an actual integration between two backend ecosystems.

And that is when I started seeing Elixir differently. It wasn't just an interesting functional language. It was a practical platform for building reliable backend applications.

### Go and Elixir: I Don't Think One Replaces the Other

I still enjoy Go. In fact, working with Elixir has made me appreciate Go even more.

They solve many of the same backend problems, but their philosophies are different.

Go is straightforward, explicit, and excellent for building services where you want predictable execution and simple deployment. Its concurrency model is easy to understand, and its ecosystem is mature for infrastructure, networking, and distributed services.

Elixir brings a different set of strengths. The BEAM runtime, lightweight processes, supervision trees, pattern matching, and functional programming model make it particularly compelling for applications with substantial concurrency, messaging, and fault-tolerance requirements.

I wouldn't choose one simply because it is fashionable.

For a service that needs a small deployment footprint, straightforward execution, and strong systems-level integration, Go is an excellent choice.

For applications that benefit from massive concurrency, process isolation, supervision, and an ecosystem built around fault-tolerant applications, Elixir deserves serious consideration.

And there is no reason a system cannot use both.

That is exactly what I did. The Go services continued to handle the core booking platform, while the Elixir application provided a separate operational back-office and participated in the event-driven workflows.

Different tools, different responsibilities, one system.

### The Takeaway: Sometimes the Best Technology Is the One That Changes Your Thinking

I started learning Elixir because a project required it. I continued because the language and its ecosystem made me rethink some of the assumptions I had carried from years of backend development.

Pattern matching made application logic more expressive. Immutability made data transformations easier to reason about. The BEAM introduced a different perspective on concurrency and fault tolerance. Phoenix, Broadway, and Oban showed how those ideas could come together in practical applications.

I am still learning the ecosystem, and I don't claim to have explored every corner of it. But I have gone beyond writing sample applications. I have used Elixir and Phoenix to build a real back-office, integrate it with Go services, process messages, and handle background work.

That practical experience is what made the difference.

I still love Go. But Elixir has earned a permanent place in my backend engineering toolkit.

And perhaps that is the best part of discovering a new technology: it doesn't always replace something you already love. Sometimes, it gives you another way to build better systems.