# DevOps Fundamentals – Introduction

Before learning any DevOps tools (Terraform, Docker, Kubernetes, CI/CD), it is important to understand **what DevOps is, why it exists, and how it works in real companies**.

This document explains DevOps **from first principles**, not from tools.

---

## Objective

By the end of this session, trainees will understand:
* What DevOps really means.
* Why DevOps was needed.
* Problems with traditional software delivery.
* How DevOps improves the SDLC.
* What DevOps engineers actually do.
* How tools fit into the DevOps lifecycle.

---

## What is DevOps?

**DevOps = Development + Operations**

DevOps is a **set of practices, culture, and automation** that helps teams:
* Build software faster.
* Deploy more frequently.
* Reduce failures.
* Improve collaboration between teams.

> [!IMPORTANT]
> **DevOps is NOT:**
> * A single tool
> * Just CI/CD
> * Only automation scripts
>
> **DevOps IS:**
> * A culture of collaboration
> * Automation of repetitive work
> * Faster and safer software delivery

---

## Why DevOps Was Needed (The Problem)

### Traditional Model (Before DevOps)
In the legacy model, developers and operations teams were "siloed."
* **Developers** write code.
* **Operations** teams manage servers.
* Both teams work separately.



**The Flow:** `Developer` → `Code` → `Handover` → `Ops` → `Manual Deployment` → `Issues`

### Problems with This Model
* Manual server setup and deployments.
* Slow release cycles.
* **Environment Mismatch:** The "it works on my machine" problem.
* High failure rate and a "blame culture."

---

## Software Development Life Cycle (SDLC)

Every application follows this cycle:
**Plan** → **Code** → **Build** → **Test** → **Release** → **Deploy** → **Operate** → **Monitor**



### Stage Breakdown
* **Plan & Code:** Requirements, design, and writing the source.
* **Build & Test:** Packaging the app and detecting bugs.
* **Release & Deploy:** Preparing and pushing software to production.
* **Operate & Monitor:** Keeping the app running and observing performance.

---

## How DevOps Improves SDLC

DevOps introduces **automation** and **continuous feedback**.

* **Traditional:** Big releases → Big failures.
* **DevOps:** Small releases → Faster feedback → High stability.

---

## Core Principles of DevOps

* **Collaboration:** Shared responsibility between Dev and Ops.
* **Automation:** Removing manual steps to reduce human error.
* **Continuous Improvement:** Learning from failures to refine processes.
* **Infrastructure as Code (IaC):** Managing infrastructure like software (version-controlled).
* **Observability:** Using logs and metrics for faster issue detection.

---

## DevOps Toolchain (High-Level Overview)

| Area | Purpose | Examples |
| :--- | :--- | :--- |
| **Version Control** | Track code changes | Git, GitHub |
| **CI/CD** | Automate build & deployment | Jenkins, GitHub Actions |
| **IaC** | Automate infrastructure | Terraform, Ansible |
| **Containers** | Package applications | Docker |
| **Orchestration** | Run containers at scale | Kubernetes |
| **Monitoring** | Observe system health | Prometheus, Grafana |

---

## Traditional vs. DevOps Flow

### Traditional Flow
`Code` → `Manual Build` → `Manual Deploy` → `Downtime`

### DevOps Flow
`Code` → `Version Control` → `Automated Pipeline` → `Reliable Deployment`

---

## Real-World DevOps Flow (Simplified)

1.  Developer pushes code to **Version Control**.
2.  The change triggers an **Automated Pipeline**.
3.  The application is **Built and Tested**.
4.  Infrastructure is **Provisioned Automatically**.
5.  The application is **Deployed**.
6.  The system is **Monitored** for health.

---

## Role of a DevOps Engineer

A DevOps engineer acts as an **enabler**. Their goal is to:
* Automate infrastructure and deployments.
* Improve system reliability.
* Reduce manual "toil."
* Improve developer productivity.

---

## What You Will Learn After This

With the foundation set, the roadmap ahead includes:
1.  **Infrastructure Automation** (Terraform)
2.  **Application Packaging** (Docker)
3.  **Container Orchestration** (Kubernetes)
4.  **End-to-End Pipelines** (CI/CD)

---

## Key Takeaway

> *"DevOps is about **how** we build and deliver software, not just the tools we use."*

---

**With this foundation, you are ready to start learning DevOps tools confidently.**
