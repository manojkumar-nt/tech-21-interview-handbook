[← Back to Tech-21: Kubernetes Overview](./README.md) | [🏠 Series Catalog](../../README.md)

---

# Preface 

## The Tech-21 Philosophy

As cloud infrastructure matures and containerized deployments become universal across enterprise software engineering, Kubernetes has emerged as the definitive operating system of the modern cloud. Yet, in technical interviews for Senior, Staff, and Principal Platform, SRE, and Cloud Architects—as well as in high-stakes production outages—the differentiator is never trivia about command-line flags or copy-pasting YAML manifests. The true differentiator is **deep mechanical sympathy: understanding how the declarative control plane operates, how etcd guarantees Raft consensus, how the Kubelet coordinates container runtimes via CRI, how the Linux kernel enforces cgroups and network namespaces via CNI and eBPF, and how distributed controllers reconcile observed state against desired state**.

Most Kubernetes resources fall into two traps:
1. **The 900-page encyclopedia**: Comprehensive but unwieldy, burying operational realities beneath hundreds of pages of basic tutorial walkthroughs.
2. **The superficial YAML cheatsheet**: Surface-level syntax guides that offer zero intuition for what occurs under the hood when a pod is scheduled, when an OOM event triggers node eviction, or when a rolling update drops packets.

**Tech-21** bridges this divide. We discard introductory filler and generic platitudes to focus relentlessly on runtime mechanics, distributed systems theory, kernel primitives, and battle-tested production trade-offs.

---

## The 21-Question Curation Framework

This volume distills Kubernetes into **21 foundational questions**, organized across four progressive engineering tiers followed by two deep-dive reference appendices:

| Tier | Focus Area | Chapters | Core Architectural Competencies |
| :--- | :--- | :--- | :--- |
| **Tier 1** | **Foundations & Architecture** | Q01 – Q05 | Declarative state reconciliation, `kube-apiserver` admission pipelines, `kube-scheduler` filtering/scoring, `kube-controller-manager` lease locks, `etcd` Raft quorum & MVCC revisions, Kubelet PLEG mechanics, CRI containerd shims, and container lifecycle transitions (Init, PreStop, Probes). |
| **Tier 2** | **Workload Abstractions & Storage** | Q06 – Q10 | Guaranteed/Burstable/BestEffort QoS classes, Linux cgroup OOM killer scores, Deployment `RollingUpdate` hash invariants, StatefulSet stable ordinals & headless DNS, DaemonSets vs CronJobs, and StorageClass dynamic volume provisioning loops with PV/PVC binding mechanics. |
| **Tier 3** | **Networking, DNS & Traffic Routing** | Q11 – Q15 | Container Storage Interface (CSI) gRPC plugin architecture, VolumeSnapshots, IP-per-Pod CNI routing (veth pairs, VXLAN, BGP overlays), `kube-proxy` iptables vs IPVS connection tracking, CoreDNS search path amplification (`ndots:5`), and Ingress vs Modern Gateway API role-oriented hierarchies. |
| **Tier 4** | **Security, Governance & Autoscaling** | Q16 – Q21 | Least-privilege RBAC matrices, projected TokenRequest ServiceAccount tokens, Zero-Trust NetworkPolicy eBPF/conntrack filtering, Pod Security Standards (PSA/PSS), Validating Webhooks, HPA metrics server algorithms, KEDA event-driven autoscalers, Karpenter JIT node provisioning, and Custom Resource Definitions (CRDs) with Kubebuilder Operator controllers. |
| **Tier 5** | **Reference Appendices** | Q22 – Q23 | Comprehensive Kubernetes Troubleshooting Decision Matrix & Diagnostic Workflow (Appendix A), and Production-Grade Multi-Resource Blueprint Manifest Patterns (Appendix B). |

---

## Strict 5-Section Chapter Schema

To ensure rapid comprehension and permanent retention, every core chapter (Chapters 01 to 21) strictly adheres to the Tech-21 five-part anatomy:

1. **The Core Concept & Intuition**: Why the abstraction exists, what distributed systems challenge it resolves, and concrete technical mental models.
2. **Under the Hood**: Detailed internal execution mechanics, engine pipelines, memory/state layouts, horizontal architecture diagrams (`graph LR`), and structured comparison matrices.
3. **Clean Code in Action**: Production-ready, validated Kubernetes manifests and operational commands showcasing standard idiomatic implementations (`### A.`) and advanced enterprise resilience patterns (`### B.`).
4. **Common Pitfalls & Interview Traps**: Curated 2-column Markdown tables uncovering subtle configuration bugs, race conditions, silent packet drops, and classic interviewer traps.
5. **60-Second Memory Anchor**: A concentrated, punchy conceptual takeaway that permanently locks the mental model into memory.

---

## How to Use This Book

- **For Senior Platform & SRE Interviews**: Focus intently on Section 2 (*Under the Hood*) and Section 4 (*Common Pitfalls & Interview Traps*). Pay special attention to consensus failure modes, Kubelet PLEG stalls, `ndots:5` DNS latency penalties, and etcd compaction bottlenecks.
- **For Cloud & Software Architects**: Use the architectural diagrams and comparison tables to evaluate trade-offs between IPVS vs iptables, Ingress vs Gateway API, and Karpenter vs Cluster Autoscaler when designing resilient multi-tenant platforms.
- **For Production Incident Response**: Keep Appendix A and the Section 4 tables within arm's reach during on-call rotations to swiftly pinpoint and remediate CrashLoopBackOff, OOMKilled, volume attachment timeouts, and silent network policy drops.

Let us begin by dissecting the brain of the cluster: the Kubernetes Control Plane.

---

**Next**: [Question 01 →](./01-kubernetes-control-plane-architecture.md)
