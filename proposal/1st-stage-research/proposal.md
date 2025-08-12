# Proposal

#### ❓ Problem Statement

In current DAO systems, implementing a **transparent, secure, and privacy-preserving** voting process remains a major challenge. With Midnight – the new privacy-focused blockchain on Cardano – there is an opportunity to design a more secure voting mechanism. However:

* Midnight is still in the testnet phase, with SDKs lacking documentation and features.
* Existing DAO development tools are not yet compatible or ready for Midnight’s ZK model and smart contracts.
* Developing a complete product (e.g., a dApp) directly on an unstable platform carries high technical risks and can lead to wasted resources.

Therefore, there is a need for a **research and architecture experimentation phase** before moving on to full-scale implementation.

***

#### ✅ Proposal Objective

The main objective of this proposal is to build a **technical prototype** for a DAO voting system on Midnight, using the commit–reveal model, with an **open, modular architecture** detailed enough to serve as a technical foundation for a future SDK or demo application.

***

#### 💡 Proposed Solution

We propose implementing a **technical prototype**, which includes:

**1. Modular Architecture Design**

* Build separate components such as `vote-core` (logic), `vote-test-env` (network simulation), and `vote-cli` (command-line tool).
* Each module can be reused in the SDK or integrated into real-world applications.

**2. Simulated Voting Environment**

* Due to the current limitations of the Midnight testnet and SDK, the team will build a **mock layer** to test the commit–reveal voting process independently.

**3. Full Architecture Documentation**

* Draft detailed technical documentation, including flow logic, data structures, and evaluations of different privacy-preserving implementation approaches.
* This documentation will serve as a foundation for the SDK & demo app teams to continue development.

***

#### 🔧 Core Components

| Component       | Short Description                                                                   |
| --------------- | ----------------------------------------------------------------------------------- |
| `vote-core`     | Library handling commit, reveal, and ballot validity logic                          |
| `vote-test-env` | Simulated voting environment, including voter, signer, and mock network             |
| `vote-cli`      | Command-line tool for dev/testing, voter input, and running simulated voting rounds |
| `vote-docs`     | Documentation describing system architecture, technical assessments, and extensions |

***

#### 📆 Implementation Roadmap (6 months)

| Month | Main Tasks                                             |
| ----- | ------------------------------------------------------ |
| 1     | Initialize repo, define interfaces between modules     |
| 2     | Develop `vote-core` logic                              |
| 3     | Develop `vote-test-env`                                |
| 4     | Build `vote-cli` and integrate with test environment   |
| 5     | Draft technical documentation (`vote-docs`)            |
| 6     | Internal review, consolidate outputs, prepare handover |

***

#### 💰 Proposed Budget Allocation (Total: **86,139 ADA**)

| **Milestone**                                                      | **Description**                                                                                  | **Deliverables**                                                                                                                                                                                                                 | **Cost (ADA)** |
| ------------------------------------------------------------------ | ------------------------------------------------------------------------------------------------ | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | -------------- |
| **1. Architecture setup & module standardization**_(Month 1)_      | Establish the system foundation, define module boundaries, and standardize repository structure. | - System architecture diagram (architecture.md + diagram)- Repository with 4 main module directories (vote-core/, vote-cli/, vote-test-env/, vote-docs/)- Markdown specifications for modules and interfaces (/docs/interfaces/) | **21,150**     |
| **2. Develop vote-core & voting logic**_(Months 2–3)_              | Build the core component that manages the commit–reveal voting process.                          | - Completed vote-core library code- Test cases + coverage report (>85%)- Detailed documentation of the voting process (docs/vote-flow.md)                                                                                        | **25,420**     |
| **3. Simulation environment + CLI tools**_(Month 4)_               | Create a realistic voting simulation environment and develop an interactive CLI.                 | - Installable CLI package (vote-cli)- Local simulation environment (vote-test-env)- Demo script + README for end-to-end testing                                                                                                  | **20,620**     |
| **4. Technical documentation & final consolidation**_(Months 5–6)_ | Produce comprehensive technical documentation and complete internal QA.                          | - Complete technical documentation (vote-docs/)- Project handover-ready repo- Final report + future roadmap                                                                                                                      | **18,949**     |
| **Total**                                                          | —                                                                                                | —                                                                                                                                                                                                                                | **86,139**     |

***

#### ⚠️ Risks & Mitigation

| Risk                         | Mitigation Strategy                                                  |
| ---------------------------- | -------------------------------------------------------------------- |
| Midnight SDK changes         | Modular design, reduce dependencies, use mock layer when necessary   |
| Noir lacks required features | Prioritize simple commit–reveal, avoid complex zk-circuits           |
| Unstable testnet             | Create a mock network layer and fallback mechanism for offline tests |

***

#### 📦 Deliverables

* A library simulating the DAO voting process on Midnight.
* A CLI tool usable internally and in the next SDK phase.
* A standardized technical documentation package.
* A test environment for developers that does not require direct access to the testnet.
