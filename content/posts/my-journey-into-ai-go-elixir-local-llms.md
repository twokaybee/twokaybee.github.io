+++
title = "My Journey into AI: Building with Go, Elixir, and Local LLMs"
date = 2026-11-03
description = "Exploring AI application development through Go and Elixir, from local LLMs and tool calling to agent frameworks, orchestration, and building practical applications."

[taxonomies]
tags = ["AI", "Go", "Elixir", "LLMs", "Ollama", "AI Agents", "Backend", "Jido", "ReqLLM", "LangChainGo", "Eino"]
+++

AI is everywhere these days. Every other week, there is a new model, a new framework, a new agent, or a new announcement promising to change the way we build software.

It is an exciting space, but also an incredibly noisy one.

As someone who has spent around twenty years building backend systems, I wasn't particularly interested in jumping into AI just because it was becoming fashionable. I wanted to understand how it could be used to build actual applications.

I wasn't looking to train models, implement neural networks from scratch, or become a machine learning researcher. My interest was much closer to what I have always done: building software, designing APIs, integrating services, handling workflows, and making systems work reliably.

What if I could bring those same engineering principles into AI-powered applications?

That question started my journey.

### I Didn't Want to Start with Python

A lot of AI development material revolves around Python. It has an enormous ecosystem, and there are very good reasons for that. But Go and Elixir are the languages I enjoy working with, and I wanted to explore what was possible within those ecosystems.

I wasn't interested in abandoning the technologies I already knew just to follow the most popular path.

I wanted to understand the fundamentals first: how an application communicates with a language model, how prompts and structured responses work, how tool calling is implemented, and how an agent decides what to do next.

These are application engineering problems as much as they are AI problems.

And I wanted to solve them using the languages I already knew.

### The First Step: Running Models Locally

Before getting into frameworks and agents, I wanted to run language models on my own machine.

That led me to **Ollama**.

Being able to download a model, run it locally, and communicate with it through an API was a good starting point. I didn't need a cloud subscription or an external API key for every experiment. I could test prompts, inspect responses, experiment with different models, and understand the interaction between an application and an LLM.

I started experimenting with smaller models, including Qwen 2.5 3B, and later installed Gemma 3 4B.

Of course, local inference comes with its own limitations. Smaller models can be inconsistent, response quality varies, and hardware resources matter. My machine doesn't have a dedicated NVIDIA GPU, so inference speed is part of the experiment too.

But that is precisely why I wanted to try it locally.

I wanted to understand the entire path, from sending a request to receiving a response, rather than treating the model as some remote black box.

### Elixir: ReqLLM and Jido

Since I was already spending time with Elixir and Phoenix, it made sense to explore AI development in that ecosystem first.

Two libraries caught my attention: **ReqLLM** and **Jido**.

ReqLLM provides a common interface for interacting with language models. It makes it easier to work with different providers and models without tying application code too closely to one particular API.

That is useful because I don't want my application architecture to depend on a single model provider. I want the freedom to experiment, compare models, and change providers without rewriting the entire application.

Then there is Jido, which takes the exploration further into agent-based application development.

The interesting part about agents isn't simply sending a prompt to a model and displaying the response. It is giving an application the ability to work through tasks, use tools, maintain state, and coordinate actions.

That brings us back to familiar backend engineering concerns.

How do we define responsibilities? How do we validate inputs? What happens when a tool fails? How do we control execution? How do we prevent an agent from doing something it shouldn't?

These are not entirely new problems. They are familiar engineering problems appearing in a different context.

### Go: LangChainGo and Eino

Naturally, I wanted to explore the Go ecosystem as well.

Go has always been my preferred language for backend services, and I was curious to see how much of the emerging AI application ecosystem was available without leaving it.

I started looking at **LangChainGo**.

It provides abstractions for common LLM application patterns, including model integrations, prompts, chains, and tools. It offers a useful way to explore how these building blocks fit together.

I also started exploring **CloudWeGo Eino**.

Eino is particularly interesting because of its focus on composing AI applications using reusable components and graph-based workflows. Rather than treating an AI application as one long prompt, it provides building blocks for connecting different stages of execution.

I wanted to understand both approaches, not just learn the APIs.

My plan was to start by implementing tool calling manually, then use LangChainGo to understand what a framework provides, and finally explore how the same application could be expressed using Eino.

I find that approach much more useful than starting with a framework and accepting its abstractions without understanding what happens underneath.

### Tool Calling: Where Things Start Getting Interesting

For me, tool calling is one of the most interesting parts of AI application development.

A language model by itself generates responses. It doesn't automatically know how to query your database, call an external API, create a booking, or execute a business operation.

Tool calling provides a bridge between the model and the application.

You expose a set of tools with descriptions and input schemas. The model can decide when a tool is relevant and request that it be called. Your application validates the request, executes the actual function, and returns the result to the model.

The distinction is important.

The model does not directly execute your business logic. The application remains responsible for deciding what is allowed, validating arguments, handling failures, and controlling side effects.

That is where I think experienced backend engineers have an interesting advantage.

We already understand APIs, contracts, validation, authorization, transactions, retries, and failure handling. Those concepts don't disappear when we introduce an LLM. If anything, they become more important.

An agent that can call tools is only as reliable as the application around it.

### MiseCart: Turning the Exploration into an Application

I didn't want this journey to remain a collection of isolated experiments.

That is where **MiseCart** came in.

MiseCart is a small Elixir/Phoenix project exploring the idea of turning recipe requests into structured ingredients and eventually a shopping cart.

The idea is straightforward: a user describes what they want to cook, and the application uses an LLM to help turn that request into something the application can work with.

But even a seemingly simple recipe application introduces interesting engineering questions.

How do you get predictable structured output from a model? How do you validate the ingredients? How do you handle missing information? How do you distinguish between a conversational response and data that needs to be processed by the application?

And perhaps most importantly, how do you avoid trusting every response returned by the model?

This is where the traditional backend engineering mindset becomes useful again.

The model can help interpret a request, but the application must own its data, rules, and business logic.

MiseCart is an exploration rather than a commercial product, but it gives me a practical place to experiment with local models, ReqLLM, Phoenix, and the application patterns that sit between an LLM and a real system.

### AI Frameworks Are Useful, But I Still Want to Understand the Internals

One thing I have noticed while exploring this ecosystem is how quickly abstractions are introduced.

There are frameworks for prompts, chains, agents, graphs, memory, tools, and orchestration. They can save a considerable amount of development time.

But I don't want to become dependent on abstractions I don't understand.

I want to know what happens when a model requests a tool. I want to understand how the conversation history is assembled, how tool results are fed back into the model, how structured output is handled, and what happens when the model produces something unexpected.

I also want to understand the differences between a simple LLM integration, a workflow, and an agent.

They are not interchangeable concepts.

A workflow follows an application-defined sequence of steps. An agent has some degree of autonomy in deciding which actions to take. Both have their place, and not every problem needs an agent.

Sometimes a well-designed function and a straightforward API are still the better solution.

### Go or Elixir for AI Applications?

I don't think there is a single answer.

Go gives me a familiar environment for building services, integrating external systems, and implementing explicit application workflows. LangChainGo and Eino make it possible to explore AI application patterns without stepping outside the Go ecosystem.

Elixir brings a different set of strengths. Its concurrency model, process isolation, supervision, and message-passing architecture make it an interesting environment for applications involving multiple concurrent tasks and long-running workflows. ReqLLM and Jido provide useful foundations for exploring LLM integrations and agent-based applications.

I particularly like the idea of combining these technologies where it makes architectural sense.

A system doesn't need to be written in one language from end to end. Go and Elixir can coexist, communicate through APIs and messaging, and each handle responsibilities that suit their strengths.

That is not a new idea for me. It is the same architectural flexibility I have used in distributed systems for years.

### The Takeaway: I'm Interested in Building with AI, Not Just Talking About It

I am still exploring this space. There is a lot to learn, and the ecosystem changes quickly.

But I have a fairly clear idea of where my interest lies.

I want to build AI-powered applications, tools, and agents using Go and Elixir. I want to understand the underlying mechanics, experiment with local models, explore different orchestration approaches, and integrate these capabilities into practical software.

I use tools such as Cursor and Claude Code to accelerate development, but I still want to understand the code being written, review the architecture, and test the resulting behaviour.

AI-assisted development should make an engineer more productive, not remove the need for engineering judgement.

After twenty years of building software, I find this new area genuinely exciting. Not because AI replaces everything we have done before, but because it gives us another set of capabilities to build with.

And I would much rather spend my time building something useful with it than chasing every new announcement.

The journey is still underway. I'm enjoying it.