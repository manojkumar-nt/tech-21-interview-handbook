[← Back to Tech-21: Docker & Container Runtimes Overview](./README.md) | [🏠 Series Catalog](../../README.md)

---

# Preface 

## The Tech-21 Philosophy

As software engineers and DevOps architects building distributed microservices, cloud-native platforms, and scalable Kubernetes clusters, we operate in an era where containerization is the absolute foundation of modern infrastructure. Since Docker democratized Linux kernel virtualization in 2013, the container ecosystem has evolved from a single monolithic daemon (`dockerd`) into an industrial Open Container Initiative (OCI) standard powering global cloud infrastructure. Yet, in technical interviews, senior architecture reviews, and high-stakes production incidents, the differentiator is never mere syntax recall or basic CLI commands. It is **deep, foundational mastery of the underlying Linux kernel primitives—Namespaces, Control Groups (cgroups v2), OverlayFS union filesystems, OCI runtime bundles, signal propagation, and least-privilege security boundaries**.

Most container literature suffers from one of two extremes:
1. **The 600-page sysadmin manual**: Exhaustive, but bogged down with outdated setup tutorials and bloated command options that obscure architectural understanding.
2. **The superficial "Docker for Beginners" tutorial**: Surface-level commands (`docker run`, `docker build`) that treat containers as opaque black boxes, leaving engineers helpless when faced with production OOM kills, zombie PID 1 processes, port mapping NAT overhead, or container escape vulnerabilities.

**Tech-21** bridges this gap. It eliminates introductory filler, bypassing generic fluff ("In today's fast-paced cloud era...") to deliver immediate conceptual, mechanical, and architectural depth.

---

## The 21-Question Curation Framework

This volume distills Docker and container runtimes into **21 foundational questions**, organized across four progressive engineering tiers followed by two deep-dive reference appendices:

| Tier | Focus Area | Chapters | Core Architectural Competencies |
| :--- | :--- | :--- | :--- |
| **Tier 1** | **Foundations & Kernel Architecture** | Q01 – Q05 | Linux namespace resource isolation (`clone`, `unshare`, `setns`), cgroups v2 resource accounting (`cpu.max`, `memory.max`, OOM killer), OverlayFS Copy-on-Write layer composition, OCI specifications and low-level runtime execution with `runc`, and high-level runtime management via `containerd` and CRI-O. |
| **Tier 2** | **Core Abstractions & Storage/Networking** | Q06 – Q10 | Multi-stage Dockerfile layer optimization, minimal base image trade-offs (scratch, Alpine, Distroless), PID 1 Unix signal handling and zombie reaping, default bridge (`docker0`) virtual ethernet routing and `iptables` NAT, and advanced networking topologies (Macvlan, IPVlan, Overlay VXLAN). |
| **Tier 3** | **Storage, Composition & Modern Builders** | Q11 – Q15 | State management across Named Volumes, Bind Mounts, and `tmpfs`, multi-service orchestration with the Compose Specification, concurrent multi-arch builds with BuildKit and buildx, non-root user execution boundaries, and kernel privilege reduction via Linux Capabilities, Seccomp, and AppArmor. |
| **Tier 4** | **Enterprise Production, Security & Operations** | Q16 – Q21 | Daemonless and rootless container architectures (Rootless Docker, Podman), static vulnerability scanning and SBOM generation with Trivy, cryptographic signing and supply-chain verification via Sigstore Cosign, non-blocking 12-factor logging pipelines, healthchecks and restart policies, and distroless live debugging with `cdebug` and `dive`. |
| **Tier 5** | **Reference Appendices** | Q22 – Q23 | Complete Docker & Container CLI Cheatsheet (runtime inspection, network plumbing, kernel troubleshooting), and Enterprise Production Dockerfile Reference Patterns across Go, Node.js, Python, Java, and Rust. |

---

## Strict 5-Section Chapter Schema

To guarantee maximum signal and long-term retention, every core chapter (Chapters 01 to 21) strictly follows our 5-part anatomy:

1. **The Core Concept & Intuition**: Why the primitive or feature exists, what architectural bottleneck it resolves, and concrete technical mental models.
2. **Under the Hood**: Detailed runtime execution mechanics, memory and filesystem layouts, horizontal architectural diagrams (`graph LR`), and structured comparison matrices.
3. **Clean Code in Action**: Production-ready, modern configuration and code patterns featuring idiomatic implementations (`### A.`) and advanced resilient practices (`### B.`).
4. **Common Pitfalls & Interview Traps**: 2-column Markdown tables analyzing real-world production outages, security vulnerabilities, kernel panics, and interviewer curveballs.
5. **60-Second Memory Anchor**: A punchy, memorable mental model permanently locking the concept into memory.

---

## How to Use This Book

- **For Senior, Staff & SRE Technical Interviews**: Master one chapter daily or review each progressive tier systematically. Internalize the Section 2 comparison matrices and Section 4 pitfalls tables to excel in system design, platform engineering, and infrastructure internals rounds.
- **For Application Developers & Platform Engineers**: Gain immediate clarity on how containers actually execute on Linux kernels, optimize production image sizes from gigabytes to megabytes, eliminate CVE alerts, and implement non-root defense-in-depth.
- **For Production Troubleshooting & Diagnostics**: Keep this volume on hand when diagnosing mysterious OOM kills, container network timeouts, ungraceful process terminations, multi-arch cross-compilation errors, or locked volume permissions.

Let's begin with Question 1.

---

**Next**: [Question 01 →](./01-linux-namespaces-and-process-isolation.md)
