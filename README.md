# GahlotTarvydas
## GaTy
### Gahlot Tarvydas - An architecture for time-aware, natively concurrent queue based programs with a deterministic, fail-safe execution runtime

This repository contains design discussions and ideas around my (**Arpit Gahlot**) take on **Paul Tarvydas**'s ideas on a programming paradigm that is closer in design to plug-and-play hardware, based on standardized interfaces.

**GaTy** is a software architecture designed around an asynchronous first design where elapsed time and event chronology plays an essential role in thinking about execution of a program. I'm designing something that uses fail-safe queues with a fire-and-forget design rather than a stack-oriented design.

With **GaTy**, I also intend to understand how programming can be done by using diagrams-based interfaces. I'm motivated by Paul's ideas of moving away from pure Gutenberg paradigm (programs being typed by using characters on a keyboard) to a higher order system design, where blocks can be configured and connected in an easy to understand interface.

### **GaTy** is an effort to understand if I can achieve the following:
1. Can a program be designed by configuring and connecting blocks, similar to engineering blueprints, or computer networking, without learning and typing a specific syntax in ASCII?
2. Can a single program be designed in a way that it is modular and scalable, similar to modern day microservices?
3. Can a language runtime be designed with features that are typically available at the kernel level - such as a process scheduler that can orchestrate directly on hardware?
4. Instead of thinking about a program as an execution stack based on some data, and a series of fucntions that must be run one after another, can I instead think of each computation as some resource, with its own queue, and any data must be written to this queue, and the output is written to another queue?
5. Can errors be treated as a fail-safe, non-mutating queue—where, if a resource fails to process certain data, that data is written unchanged to an error queue, optionally accompanied by stack traces or messages—which can then be piped to a buffer, file, cache, network, or external device?
6. Can a resource be scaled independently under load by the language runtime itself—for example, if it is invoked too frequently, can the runtime automatically spawn a copy on another processor core, with its own queue, and load-balance across these copies?
7. Is the Linux kernel’s concept of a ring buffer a suitable paradigm for sharing the same data across multiple resources within a single program?
8. Can such a program be designed to have predictable execution time, while providing a clear chronology and traceable data paths as data moves through various queues and resources?

> [!NOTE]
> This is not an implementation of Parts Based Programming. This repository contains my own independent take on similar ideas. To explore Paul's ideas, visit:
> 
> [Paul's YouTube](https://www.youtube.com/@programmingsimplicity2980)
> 
> [Paul's Github](https://github.com/guitarvydas/pbp-kit)
