# Phase 1 - SDK Architecture Standardization

### 📍 Milestone 1: SDK Architecture Standardization

***

### &#x20;Objective

\
Build the core logic for a DAO voting system (voting prototype) from scratch, following a reusable and extensible architecture within an SDK.\
Create a robust foundation to support subsequent milestones without relying on outputs from other proposals.

### &#x20;Proposed Architecture

\
Main modules to implement: vote-core:

* Manages the voting lifecycle: create poll, submit vote, count votes.
* Supported poll types: binary vote (Yes/No), multiple choice.
* Rule configuration: voting period, quorum, minimum stake.

vote-types:

* Common interface for data definitions: Vote, Poll, Result, VoterStake.
* Allows extensibility with adapters, such as ZK adapter (Midnight) or non-ZK adapter.

vote-storage (Mock):

* Stores poll/vote state using JSON files or in-memory (mock storage).
* Separates logic from testnet environment (Midnight is not yet stable).

vote-simulate:

* Runs simulation scenarios: multiple users voting, vote counting, quorum validation, admin permissions.
* Supports configuration of voter count, token distribution, and testing edge cases.

<figure><img src="../../../.gitbook/assets/Milestone1 _ Mermaid Chart-2025-08-11-105943.png" alt=""><figcaption></figcaption></figure>

***

🛠 **Specific Tasks**

📦 **1. Codebase Structure Design**

* Initialize Git repo (private/public as preferred)
* Set up standard folder structure: `core/`, `types/`, `mock/`, `cli/`
* Configure basic CI (auto-formatting, unit test automation)

⚙️ **2. Vote-Core Logic Development**

* **PollManager**: Poll initialization function (with config)
* **VoteHandler**: Processes user votes and validates submissions
* **TallyEngine**: Calculates final results, checks quorum, win/lose conditions
* Add basic unit tests (Mocha/Jest or equivalent test framework)

🧪 **3. Simulation System Development**

* Develop `vote-simulate.js/ts` module:
  * Generate mock voter lists
  * Auto-distribute stakes
  * Execute batch voting
  * Output results and tracking logs
* Test scenarios:
  * Quorum met/not met
  * Late votes / duplicate votes
  * Poll expiration

🧾 **4. Technical Documentation**

* Write READMEs for each module
* Draft module architecture diagrams
* Explain supported config types
* Provide Markdown docs + inline code comments

***

#### 📤 Deliverables

| Output                       | Mô tả ngắn                                  |
| ---------------------------- | ------------------------------------------- |
| `vote-core` source code      | Core poll and vote management logic         |
| `vote-simulate` script       | Execute voting simulation with mock data    |
| `vote-types` interface       | Type definitions for SDK reuse              |
| `README + ARCH.md`           | System architecture technical documentation |
| `Unit tests` (≥80% coverage) | Ensure reliability and scalability          |

***

**🔄 Review & Testing Plan**

* **Week 3:** Architecture review + vote logic testing
* **Week 5:** Full simulation runs for 3 distinct scenarios
* **Week 6:** Documentation consolidation, prepare for SDK transition (Milestone 2)
