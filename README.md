# DevOps Foundations

> **Module 0 of the DevOps Masterclass.** Start here. This is the *"why"* before all the *"how"*.

Before you touch a single tool, you need to understand what DevOps actually is, why it exists, and how every tool in this course fits into one bigger picture. Two short lessons give you that foundation.

## What problem does this module solve?

People often jump straight into Docker or Kubernetes and end up as copy-paste engineers who cannot debug because they never learned *what the tools are for*. This module fixes that: it teaches the software lifecycle and the DevOps culture first, so every later tool has a place to live in your mental model.

```mermaid
flowchart LR
    Plan["Plan"] --> Code["Code"] --> Build["Build"] --> Test["Test"]
    Test --> Release["Release"] --> Deploy["Deploy"] --> Operate["Operate"] --> Monitor["Monitor"]
    Monitor -.feedback.-> Plan
```

## Interactive demos

Open these in any browser (download the repo and open the file):
- [DevOps Lifecycle](animations/devops-lifecycle.html) - watch the continuous loop come alive.
- [Waterfall vs Agile](animations/sdlc-models.html) - compare the two delivery models side by side.

## Lessons

| Day | Topic | What you will learn |
|---|---|---|
| [Day 1](day1-what-is-devops/notes.md) | **What is DevOps?** | Culture, why it exists, CALMS, the toolchain, and how it all connects |
| [Day 2](day2-sdlc/notes.md) | **Software Development Life Cycle** | All SDLC stages and models (Waterfall, Agile, Spiral, V-Model), and how DevOps improves each |

## Learning outcomes

By the end of this module you will be able to:
- Explain DevOps to a non-technical person in one sentence.
- Name the stages of the software lifecycle and what each produces.
- Describe the CALMS principles and why small frequent releases are safer.
- Map every tool in this course to the lifecycle stage it serves.

## How to use this module

Read Day 1, then Day 2, in order. Open the animations when a concept feels abstract. There is nothing to install yet - this module is about understanding, not tooling.

Start with [Day 1 - What is DevOps?](day1-what-is-devops/notes.md). When you finish, move on to the [Git module](../learn-git).
