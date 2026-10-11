[← Back to Tech-21: Node.js Core Concepts Overview](./README.md) | [🏠 Series Catalog](../../README.md)

---

# Preface 

## The Tech-21 Philosophy

As software engineers building scalable backend services and distributed systems, we are constantly navigating rapid updates across runtimes, frameworks, toolchains, and package ecosystems. Yet when debugging production memory leaks, untangling asynchronous deadlocks, optimizing high-throughput I/O pipelines, or facing principal engineering interviews, the differentiator is never syntax trivia—it is **deep conceptual mastery of runtime fundamentals**.

Most technical books fall into one of two extremes:
1. **The 700-page encyclopedia**: Exhaustive, but overwhelming when you need a crisp, high-signal refresher.
2. **The superficial cheatsheet**: Short, but lacking the "under the hood" execution models and architectural insights that make knowledge stick.

**Tech-21** was born to bridge this gap.

---

### The 21-Question Rule

Each edition in the **Tech-21** series distills an entire technology into **21 foundational questions**. Every single question in this book is structured to build an enduring mental model:

1. **The Core Concept & Intuition** — Why does this feature exist, and what architectural problem does it solve?
2. **Under the Hood** — How V8, Libuv, C++ bindings, memory allocators, and kernel I/O subsystems actually execute code.
3. **Clean Code in Action** — Modern, production-ready, idiomatically sound code patterns.
4. **Common Pitfalls & Interview Traps** — Edge cases, memory leaks, event loop blockers, and anti-patterns that trip up engineers.
5. **The 60-Second Memory Anchor** — A punchy mental anchor to lock the concept permanently into memory.

---

### How to Use This Book

- **For Technical Interview Preparation**: Read one chapter per day for 21 days, or power through the 4 progressive tiers over a focused weekend.
- **For Senior Engineers & Architects**: Deepen your intuition on thread pool saturation, backpressure dynamics, garbage collection pauses, and execution context propagation.
- **For Production Troubleshooting**: Bookmark specific chapters to diagnose stream leaks, unhandled rejections, worker thread overhead, or event loop lag.

Let's dive into Question 1.

---

**Next**: [Question 01 →](./01-nodejs-architecture.md)
