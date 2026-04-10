 # Codex Skills

  A curated collection of hand-authored Codex skills for stronger task routing,
  cleaner execution, and more consistent outputs.

  ## Included Skills

  ### Engineering
  - `debug` — Root-cause debugging with disciplined tracing and validation
  - `fix-bug` — End-to-end bug repair for a reported broken path
  - `front-end-engineer` — Production frontend implementation, fixes, and UI
  polish
  - `simplify` — Safe behavior-preserving complexity reduction and refactoring

  ### Product And Delivery
  - `product-manager` — Turn rough product ideas into launchable plans
  - `develop-team` — Coordinate broad end-to-end product delivery across roles
  - `mvp-develop-team` — Run a tightly scoped 48-hour MVP delivery workflow
  - `homework-helper` — Infer the real repo task and complete it end to end

  ### Decision Support
  - `discuss` — Structured multi-agent debate, critique, and synthesis
  - `researcher` — Research-grade ML analysis, model choice, and experiment
  design

  ## Repository Structure

  ```text
  skills/
    debug/
    develop-team/
    discuss/
    fix-bug/
    front-end-engineer/
    homework-helper/
    mvp-develop-team/
    product-manager/
    researcher/
    simplify/

  Each skill folder contains:

  - SKILL.md — Skill trigger description and operating instructions
  - agents/openai.yaml — UI-facing metadata such as display name and default
    prompt

  ## Design Goals

  These skills were refined to be more Codex-friendly by emphasizing:

  - sharper trigger descriptions
  - lower-context instruction bodies
  - stronger execution guardrails
  - clearer deliverable formats
  - more consistent agent metadata

  ## Notes

  These skills are intended for local Codex-style environments that discover
  skills from a skills/ directory structure.
