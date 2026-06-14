# Day 1 - What is DevOps?

> **Goal of today:** understand what DevOps really is, why it exists, and how all the tools you are about to learn fit together. This is the *"why"* before all the *"how"*.

Before learning any DevOps tools (Git, Docker, Kubernetes, Terraform, CI/CD), it is important to understand **what DevOps is, why it exists, and how it works in real companies**. This lesson explains DevOps **from first principles**, not from tools.

> **Interactive demo:** open [`../animations/devops-lifecycle.html`](../animations/devops-lifecycle.html) in any browser to watch the DevOps lifecycle loop come alive.

---

## Learning Objectives

By the end of this session, you will understand:
- What DevOps really means.
- Why DevOps was needed.
- Problems with traditional software delivery.
- How DevOps improves the SDLC.
- What DevOps engineers actually do.
- How tools fit into the DevOps lifecycle.

---

## 1 What is DevOps?

**DevOps = Development + Operations**

DevOps is a **set of practices, culture, and automation** that helps teams:
- Build software faster.
- Deploy more frequently.
- Reduce failures.
- Improve collaboration between teams.

> [!IMPORTANT]
> **DevOps is NOT:**
> - A single tool
> - Just CI/CD
> - Only automation scripts
> - A job title you buy with one certificate
>
> **DevOps IS:**
> - A culture of collaboration
> - Automation of repetitive work
> - Faster and safer software delivery
> - Shared ownership of the product, from code to production

### A one-line definition you can remember

> *"DevOps is the practice of shrinking the distance - and the time - between a developer writing code and a user safely benefiting from it."*

---

## 2 Why DevOps Was Needed (The Problem)

### Traditional Model (Before DevOps)

In the legacy model, developers and operations teams were **"siloed"** - they worked in separate walls, with separate goals.

- **Developers** are rewarded for *change* (ship new features).
- **Operations** are rewarded for *stability* (don't let anything break).

These two goals pull in opposite directions. That tension is the root cause of most pre-DevOps pain.

```mermaid
flowchart LR
    Dev["Developer<br/>writes code"] --> Code["Code + manual<br/>install steps"]
    Code --> Wall["The Wall of<br/>Confusion"]
    Wall --> Ops["Operations<br/>deploys manually"]
    Ops --> Issue["Breaks in prod<br/>'works on my machine'"]
    Issue --> Blame["Blame culture"]
    style Wall fill:#ffcccc,stroke:#c00
    style Issue fill:#ffe0b3,stroke:#e67e22
    style Blame fill:#ffcccc,stroke:#c00
```

### Problems with This Model
- Manual server setup and deployments lead to slow and error-prone work.
- Slow release cycles (months between releases).
- **Environment Mismatch:** the *"it works on my machine"* problem.
- Low visibility - no one owns the full picture.
- High failure rate and a **"blame culture."**

---

## 3 Software Development Life Cycle (SDLC)

Every application follows this cycle:

```mermaid
flowchart LR
    Plan["Plan"] --> Code["Code"] --> Build["Build"] --> Test["Test"]
    Test --> Release["Release"] --> Deploy["Deploy"] --> Operate["Operate"] --> Monitor["Monitor"]
    Monitor -.feedback.-> Plan
    style Plan fill:#e3f2fd,stroke:#1976d2
    style Monitor fill:#e8f5e9,stroke:#388e3c
```

### Stage Breakdown
- **Plan & Code:** Requirements, design, and writing the source.
- **Build & Test:** Packaging the app and detecting bugs early.
- **Release & Deploy:** Preparing and pushing software to production.
- **Operate & Monitor:** Keeping the app running and observing performance.

> **Deep dive:** the full SDLC guide - every stage, every model (Waterfall, Agile, Spiral, V-Model) - is tomorrow's lesson: [Day 2 - SDLC](../day2-sdlc/notes.md).

---

## 4 How DevOps Improves SDLC

DevOps introduces **automation** and **continuous feedback** at every stage.

| | Traditional | DevOps |
|---|---|---|
| **Release size** | Big, risky "big bang" | Small, frequent |
| **Feedback** | Late (after release) | Continuous |
| **Failure impact** | Large blast radius | Small, easy to roll back |
| **Recovery** | Slow (hours/days) | Fast (minutes) |

> **Key insight:** Small releases lead to faster feedback and higher stability. Counter-intuitively, **shipping *more often* makes software *safer*, not riskier**, because each change is tiny and easy to reverse.

---

## 5 Core Principles of DevOps (CALMS)

The industry remembers DevOps culture with the acronym **CALMS**:

| Letter | Principle | Meaning |
|:---:|---|---|
| **C** | **Culture** | Shared responsibility between Dev and Ops - "you build it, you run it." |
| **A** | **Automation** | Remove manual steps to reduce human error and toil. |
| **L** | **Lean** | Deliver in small batches; eliminate waste and waiting. |
| **M** | **Measurement** | You can't improve what you don't measure (metrics, logs, traces). |
| **S** | **Sharing** | Open knowledge, tools, and feedback across teams. |

Two more foundational ideas you will use constantly:
- **Infrastructure as Code (IaC):** Manage servers and networks like software - version-controlled, reviewable, repeatable.
- **Observability:** Use logs, metrics, and traces for fast issue detection.

---

## 6 DevOps Toolchain (High-Level Overview)

You don't learn tools randomly - each tool solves a **specific stage** of the lifecycle. This is the map for the rest of this course:

| Area | Purpose | Examples | This Course |
|:--- |:--- |:--- |:---|
| **Version Control** | Track code changes | Git, GitHub | `learn-git` |
| **IaC** | Automate infrastructure | Terraform, Ansible | `learn-terraform` |
| **Containers** | Package applications | Docker | `learn-docker` |
| **Orchestration** | Run containers at scale | Kubernetes | `learn-k8s` |
| **CI/CD** | Automate build & deployment | GitHub Actions, Jenkins | `learn-cicd` |
| **Monitoring** | Observe system health | Prometheus, Grafana | *(applied throughout)* |

```mermaid
flowchart LR
    subgraph Plan_Code["PLAN / CODE"]
        Git["Git + GitHub"]
    end
    subgraph Provision["PROVISION"]
        TF["Terraform"]
    end
    subgraph Build_Test["BUILD / TEST"]
        CI["GitHub Actions"]
        Docker["Docker"]
    end
    subgraph Run["RUN / SCALE"]
        K8s["Kubernetes"]
    end
    subgraph Operate_Monitor["OPERATE / MONITOR"]
        Mon["Prometheus + Grafana"]
    end
    Git --> TF --> CI --> Docker --> K8s --> Mon
    Mon -.feedback.-> Git
```

---

## 7 Traditional vs. DevOps Flow

```mermaid
flowchart TB
    subgraph Traditional["Traditional Flow"]
        direction LR
        T1[Code] --> T2[Manual Build] --> T3[Manual Deploy] --> T4["Downtime"]
    end
    subgraph DevOps["DevOps Flow"]
        direction LR
        D1[Code] --> D2[Version Control] --> D3[Automated Pipeline] --> D4["Reliable Deployment"]
    end
    style T4 fill:#ffcccc,stroke:#c00
    style D4 fill:#c8e6c9,stroke:#2e7d32
```

---

## 8 Real-World DevOps Flow (Simplified)

1. Developer pushes code to **Version Control** (Git/GitHub).
2. The change triggers an **Automated Pipeline** (CI/CD).
3. The application is **Built and Tested** automatically.
4. The app is **packaged** into a container image (Docker).
5. **Infrastructure is provisioned** as code (Terraform).
6. The container is **deployed and scaled** (Kubernetes).
7. The system is **Monitored** for health (Prometheus/Grafana).
8. **Feedback** from monitoring informs the next change.

> This exact flow is what you will build, piece by piece, across the rest of this course.

---

## 9 Role of a DevOps Engineer

A DevOps engineer is an **enabler**, not a gatekeeper. Their goal is to:
- Automate infrastructure and deployments.
- Improve system reliability and uptime.
- Reduce manual **"toil."**
- Improve **developer productivity** (make the right way the easy way).
- Build **guardrails**, not gates - let teams move fast *safely*.

> **Common misconception:** "DevOps engineer" is not just "the person who runs the pipeline." The best ones build *platforms and culture* so that every developer can ship safely without asking permission.

---

## 10 What You Will Learn After This

With the foundation set, the roadmap ahead:

```mermaid
flowchart LR
    A["1 Git<br/>Version Control"] --> B["2 Terraform<br/>Infra as Code"]
    B --> C["3 Docker<br/>Containers"]
    C --> D["4 Kubernetes<br/>Orchestration"]
    D --> E["5 CI/CD<br/>Pipelines"]
    style A fill:#f9d5e5
    style B fill:#f9f3d5
    style C fill:#d5e8f9
    style D fill:#d5f9e8
    style E fill:#e8d5f9
```

| # | Topic | Folder | What it gives you |
|:-:|---|---|---|
| 1 | **Version Control** | `learn-git` | Track, branch, and collaborate on code |
| 2 | **Infrastructure Automation** | `learn-terraform` | Create cloud infra with code |
| 3 | **Application Packaging** | `learn-docker` | "Build once, run anywhere" containers |
| 4 | **Container Orchestration** | `learn-k8s` | Run containers reliably at scale |
| 5 | **End-to-End Pipelines** | `learn-cicd` | Tie it all together automatically |

---

## Common Mistakes

1. **Thinking DevOps is a tool you install.** It is a culture and a set of practices first; the tools only support it.
2. **Believing DevOps is only the pipeline.** The pipeline is one piece; collaboration, monitoring, and shared ownership matter just as much.
3. **Assuming more releases means more risk.** The opposite is true - small frequent releases are safer than rare big ones.
4. **Skipping the "why."** Learning tools without understanding the lifecycle they serve leads to copy-paste engineers who cannot debug.

---

## Quick Self-Check

Before moving on, make sure you can answer these out loud:
1. What two words make up "DevOps," and why were they in conflict before?
2. Name the 8 stages of the SDLC in order.
3. What does CALMS stand for?
4. Why does releasing *more often* make software *safer*?
5. Which tool in the course solves which lifecycle stage?

---

## Summary

- DevOps = Development + Operations: a culture of collaboration plus automation.
- It exists to fix the slow, error-prone, siloed traditional model.
- CALMS captures its principles: Culture, Automation, Lean, Measurement, Sharing.
- Every tool in this course maps to a stage of the software lifecycle.

> *"DevOps is about **how** we build and deliver software, not just the tools we use."* The tools change; the principles do not.

**Next up ->** [Day 2 - Software Development Life Cycle (SDLC)](../day2-sdlc/notes.md)
