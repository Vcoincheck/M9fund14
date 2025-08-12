# Roadmap

## Milestones

**✅ Milestone 1: Architecture setup & module standardization (Month 1)**

**Description:** Establish the system foundation, define module boundaries, and standardize repo structure.\
**Main Tasks:**

* Create repositories for `vote-core`, `vote-cli`, `vote-test-env`, and `vote-docs`.
* Design overall architecture and communication interfaces between components.
* Define data standards (commit hash, timestamp, vote payload...).
* Create detailed plans for each module (specifications, deadlines, priorities).

**Deliverables:**

* System architecture diagram (`architecture.md + diagram`)
* Repository containing 4 main module directories (`vote-core/`, `vote-cli/`, etc.)
* Markdown specifications for modules and interfaces (`/docs/interfaces/`)

***

**✅ Milestone 2: Develop `vote-core` & voting logic (Months 2–3)**

**Description:** Build the core component that manages the commit–reveal voting process.\
**Main Tasks:**

* Implement library for commit, reveal, and verification.
* Simulate verification of ballot data and voting states.
* Set up unit tests to ensure stable logic operation.
* Optimize `vote-core` for integration with CLI and test environment.

**Deliverables:**

* Completed `vote-core` library code
* Test cases + coverage report (>85%)
* Detailed documentation of the voting process (`docs/vote-flow.md`)

***

**✅ Milestone 3: Simulation environment + CLI tools (Month 4)**

**Description:** Create a realistic voting simulation environment and develop an interactive CLI.\
**Main Tasks:**

* Build `vote-test-env`: mock blocks, simulated epochs, mock accounts.
* Develop `vote-cli` commands: `commit`, `reveal`, `verify`, `result`.
* Integrate CLI with `vote-core` and run multiple voting scenarios.
* Validate end-to-end system consistency.

**Deliverables:**

* Installable CLI package (`vote-cli`)
* Local simulation environment (`vote-test-env`)
* Demo script + README for end-to-end testing

***

**✅ Milestone 4: Technical documentation & final consolidation (Months 5–6)**

**Description:** Produce comprehensive technical documentation and complete internal QA.\
**Main Tasks:**

* Write `vote-docs`: CLI guide, system description, technical explanation.
* Consolidate test results and package deliverables for the SDK team.
* Review entire repo and complete quality checklist.
* Prepare final project report for public release.

**Deliverables:**

* Complete technical documentation (`vote-docs/`)
* Project handover-ready repo
* Final report + future roadmap



### **Implementation Plan (6 Months)**

| Month | Key Activities                                                                                                                                                                                                                                                                                                                                                                                 | Deliverables                                                                                                                                             |
| ----- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **1** | <p><strong>System Initialization – <code>vote-prototype</code> repo</strong><br>• Set up repo structure for <code>vote-core</code>, <code>vote-cli</code>, <code>vote-test-env</code>, <code>vote-docs</code>.<br>• Define module interfaces and data standards.<br>• Create architecture diagram and modular data flow model.<br>• Define basic voting parameters (commit–reveal, no ZK).</p> | <p>• System architecture diagram (<code>architecture.md</code> + diagram)<br>• Repo with 4 module directories<br>• Interface specification documents</p> |
| **2** | <p><strong>Develop <code>vote-core</code> (Phase 1)</strong><br>• Implement commit, reveal, and verification logic.<br>• Create vote payload, hashed commitment, and simulated proof structures.<br>• Write unit tests for core functions.<br>• Prepare <code>vote-core</code> for integration.</p>                                                                                            | <p>• <code>vote-core</code> library code (v0.1)<br>• Unit test coverage ≥85%<br>• <code>docs/vote-flow.md</code></p>                                     |
| **3** | <p><strong>Develop <code>vote-core</code> (Phase 2)</strong><br>• Complete voting logic and verification.<br>• Optimize core library for reuse.<br>• Update documentation.<br>• Prepare for simulation integration.</p>                                                                                                                                                                        | <p>• Final <code>vote-core</code> (v1.0)<br>• Updated API documentation<br>• Test result reports</p>                                                     |
| **4** | <p><strong>Build <code>vote-test-env</code> + CLI</strong><br>• Mock block/epoch/account data.<br>• Develop CLI commands: <code>commit</code>, <code>reveal</code>, <code>verify</code>, <code>result</code>.<br>• Integrate with <code>vote-core</code>.<br>• Run end-to-end scenarios.</p>                                                                                                   | <p>• Installable CLI tool<br>• Local simulation environment<br>• Demo script + README</p>                                                                |
| **5** | <p><strong>Technical Documentation – <code>vote-docs</code></strong><br>• Document architecture, modules, and CLI usage.<br>• Compare commit–reveal vs ZK approaches.<br>• Outline SDK integration path.<br>• Developer guide + API docs.</p>                                                                                                                                                  | <p>• Complete <code>vote-docs</code> directory<br>• SDK integration guide<br>• Config &#x26; test instructions</p>                                       |
| **6** | <p><strong>Review &#x26; Output Consolidation</strong><br>• Internal QA testing.<br>• Finalize deliverables and prepare handover.<br>• Summarize lessons learned.<br>• Prepare final Catalyst report.</p>                                                                                                                                                                                      | <p>• Final reviewed repository<br>• Project report<br>• Roadmap for next phase</p>                                                                       |
