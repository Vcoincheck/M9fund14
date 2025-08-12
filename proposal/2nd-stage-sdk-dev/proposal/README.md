# Proposal

### 🔎 **Problem: Lack of a standardized SDK for implementing commit–reveal voting on Midnight**

Building DAO applications with strong privacy is a core goal of the Midnight ecosystem. One of the most critical components of these DAO systems is the anonymous voting mechanism, often implemented using the commit–reveal voting model.

Although our team has developed a feasible prototype simulating voting logic and testing scenarios with Midnight’s testnet, a significant gap remains:

❌ There is no standardized SDK library for reuse across projects.\
❌ No clear module standards or API interfaces, making integration into dApps complex and inconsistent.\
❌ No official test harness to verify correctness and compatibility with changes in the Midnight stack (e.g., epoch model changes, ZK mechanisms).

This forces each development team to "start from scratch," rewriting voting logic and environment simulations, facing high risks when the Midnight testnet changes. This issue not only slows product development but also hinders the widespread adoption of private voting mechanisms within the Cardano & Midnight ecosystem.

#### 📌 **Summary of key issues:**

* No standardized modular SDK for commit–reveal voting on Midnight.
* Lack of clear abstraction layers and interfaces between voting logic and dApp environment.
* Difficulty reusing code from existing prototypes or dApps.
* No common technical guidelines or standards for new teams joining the ecosystem.

### 📘 Solution: Building a Standardized Modular SDK for Commit–Reveal Voting on Midnight

This proposal focuses on **productizing** the research outcomes from Proposal 1 by delivering a **developer-ready SDK** for private voting on Midnight.

While **Proposal 1 (Research & Prototype)** validated the technical feasibility of commit–reveal voting through a working prototype and internal simulation, it was never intended to be reused directly in production environments. The prototype was purpose-built for testing hypotheses, not for integration into other projects.

**Proposal 2 bridges this gap** by transforming the prototype logic into a **standardized, reusable SDK** that other development teams can plug into their DAO/dApp projects without rewriting core voting logic from scratch.

#### 🎯 Core Objectives

* **Standardize the technical interface** for commit–reveal voting logic on Midnight.
* **Modularize components** (logic, CLI tools, testing environment, documentation) to maximize maintainability and scalability.
* Provide an **official test harness** to validate correctness and compatibility against Midnight updates (e.g., epoch model changes, ZK feature updates).
* Deliver a **developer onboarding experience** with clear documentation, examples, and integration guidelines.

#### ⚙️ SDK Main Components

1. **vote-core (Voting Logic)**
   * Core functions for commit, reveal, and verification.
   * Neutral API design with no hard dependency on specific wallets or storage layers.
   * Configurable timing parameters (voting window, commit/reveal phases).
2. **vote-cli (Command-line & Automation)**
   * CLI for running, reproducing, and automating voting scenarios.
   * Easy configuration via YAML/JSON (voter lists, seed, ZK parameters).
3. **vote-test-env (Simulation & Testing)**
   * Simulates epochs, block times, and failure/recovery cases.
   * Supports stress testing with large-scale parallel scenarios.
4. **vote-docs (Technical Documentation)**
   * Covers system architecture, module integration, and API usage.
   * Includes risk analysis and fallback strategies for unstable testnet or missing ZK features.

***

✅ **Key Difference from Proposal 1:**

* **Proposal 1**: Experimental prototype to test feasibility → internal use, not modular, no standard API, no reusable test harness.
* **Proposal 2**: Developer-facing SDK with stable API, reusable modules, formal test harness, and integration documentation for ecosystem adoption.

***

#### 🛠️ Technical Approach & Design

**Maximum Modularization**\
The SDK components are packaged independently, allowing them to be replaced or extended as needed. For example, the commit/reveal logic can be upgraded to integrate Plonk or Noir once the Midnight stack becomes stable.

**Separation of the Abstraction Layer**\
The SDK provides an abstraction interface that does not directly depend on Midnight’s official SDK. This approach enables:

* Easy mocking and testing without requiring a live network.
* Faster adaptation to protocol changes in Midnight.
* Decoupling core voting logic from low-level blockchain dependencies.

📅 **Roadmap (4 Milestones)**

✅ **Milestone 1: SDK Architecture Standardization**\
**Description:**\
Extract logic from the prototype into reusable modules, designed according to library standards.

**Tasks:**

* Refactor `vote-core` into a library
* Define clear traits/interfaces
* Design API & Rust-standard error handling

**Deliverables:**

* SDK base structure
* API draft (Rustdoc)
* Architecture documentation

***

✅ **Milestone 2: SDK Feature Development**\
**Description:**\
Develop core submodules: commit, reveal, tally, epoch simulation.

**Tasks:**

* Implement `VoteSession`, `CommitProof`, `TallyEngine`
* Set up epoch/slot/lock-time simulation
* Write unit tests for each module

**Deliverables:**

* Completed `src/lib.rs`
* 90% test coverage
* Logs for each function usage

***

✅ **Milestone 3: Documentation & Sample Integration Kit**\
**Description:**\
Write technical documentation and create a simple SDK usage example (CLI/web mock).

**Tasks:**

* API documentation + JSON schema for input/output
* Code a demo sample app using the SDK
* Write integration guide

**Deliverables:**

* API Documentation in HTML format
* Sample App + CLI/Web integration guide
* 1 case study

***

✅ **Milestone 4: Public Release & Packaging**\
**Description:**\
Test, package the SDK, and release it as open source.

**Tasks:**

* Check license compliance, clean codebase
* Benchmark and optimize performance
* Release `v1.0.0` on GitHub

**Deliverables:**

* Released SDK crate
* Changelog + release notes
* Final report submitted to Catalyst

### BUDGET

| Milestone | Nội dung chính                | Chi phí (ADA) |
| --------- | ----------------------------- | ------------- |
| M1        | Chuẩn hóa kiến trúc SDK       | 18,000        |
| M2        | Phát triển tính năng SDK      | 27,000        |
| M3        | Tài liệu & tích hợp mẫu       | 21,500        |
| M4        | Release bản public & đóng gói | 23,500        |
| **Tổng**  |                               | **90,000**    |

### **Value for money**

This SDK delivers a cost-effective, production-grade foundation for integrating anonymous voting into DAO infrastructures on Cardano, powered by the Midnight privacy stack. By modularizing complex components such as commit–reveal voting, time-locked sessions, and zero-knowledge proof handling, the SDK drastically reduces technical overhead for ecosystem builders.

The project is fully open-source and designed for reusability, ensuring that other teams can build upon it without reinventing the wheel. Based on typical market development rates, it is estimated to save **30–50%** of development cost and time for future DAO-related applications.

The team behind the SDK consists of experienced Rust developers and privacy researchers with a proven track record in blockchain R\&D. The deliverables follow best practices in software engineering: clean code, robust test coverage, formal documentation, and production-ready packaging. This ensures long-term maintainability and real-world applicability across multiple use cases within the Cardano ecosystem.
