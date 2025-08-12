# Proposal

**Project Name:** Anonymous DAO Voting dApp\
**Platform:** Midnight (ZK Layer on Cardano)\
**Goal:** Deliver a practical, privacy-first DAO voting solution with complete anonymity and zero identity traceability, designed to set a usable standard for the future DAO ecosystem.\
**Type:** Frontend dApp Demonstration \
**Open Source:** Yes — the dApp source code will be released publicly on GitHub under the MIT license

***

### 🔍 **Problem Statement**

In most DAOs today, voting is public, making it vulnerable to community pressure, intimidation, and “trend voting” behavior.\
Moreover, no existing voting tool truly incorporates **zero-knowledge (ZK) privacy** at the end-user level.

**Current Challenges:**

* DAO voting platforms are primarily designed for public blockchains (EVM, Cardano native)
* Lack of genuine anonymity — wallet addresses and voting actions remain traceable
* Publicly exposed voting data can negatively influence long-term governance decisions
* No standardized UI/UX for secure, privacy-preserving voting

**Identified Needs:**

* An **end-to-end anonymous voting** mechanism
* A clear, intuitive interface accessible to non-technical users
* Role-based support for core DAO participants (proposal creators, voters, observers)

***

### 🧩 **Proposed Solution**

We propose building a dedicated anonymous voting frontend dApp for DAOs, fully leveraging ZK-privacy on Midnight.

**Key Features:**

* Clean, modern, and responsive user interface
* DAO and proposal creation workflows
* Voting via commit–reveal or ZK-SNARK mechanisms
* Result display without exposing individual votes
* User authentication without wallet address disclosure

**Primary Roles Supported:**

* **Project Initiator:** Creates DAOs and opens voting sessions
* **Proposal Creator:** Submits proposals to the DAO
* **Voter:** Casts votes anonymously
* **Observer:** Monitors and verifies the voting process

***

### 🧠 **Technical Scope**

* Integrate with the existing ZK Voting SDK (developed in Proposal 2)
* No backend development — frontend communicates directly with SDK via middleware
* UI/UX stack: TailwindCSS, optimized animations, responsive design
* Core application pages:
  * Homepage
  * DAO Dashboard
  * Proposal View
  * Voting Page (Commit/Reveal)
  * Results Summary
  * Profile (ZK identity-based)

***

### 📆 **Timeline & Milestones**

#### **Milestone 1 – Research & UI/UX Design**

**Duration:** Month 1

**Description:**\
Lay the groundwork for the voting dApp by researching anonymous DAO voting flows and Midnight limitations. Define system roles and design the full UI/UX experience.

**Main Tasks:**

* Research ZK voting patterns and DAO flows on Midnight
* Define project roles: proposal, voter, project team
* Design end-to-end user journey (commit–reveal–tally)
* Create wireframes, user flows, and component tree
* Evaluate and select UI technologies
* Draft visual identity and animation principles

**Deliverables:**

* UX wireframes & voting flow mockups
* Component structure documentation
* Tech stack & architecture plan
* DAO voting system research brief

***

#### ✅ **Milestone 2 – Commit Phase Development**

**Duration:** Month 2–3

**Description:**\
Develop the Commit phase of the app, including the user interface, vote session handling, and commitment logic (with placeholder cryptography).

**Main Tasks:**

* Build responsive Commit interface (select proposal, commit vote)
* Implement local session state tracking (slot, lock-time UI)
* Integrate basic ZK proof generation for commit
* Handle front-end validations & edge cases
* Style with transitions & user feedback animations
* Unit test UI states and UX logic

**Deliverables:**

* Commit interface fully functional
* Proof-of-concept ZK commit logic
* Internal test logs
* Voting session controller with commit lock visuals

***

#### ✅ **Milestone 3 – Reveal & Tally Implementation**

**Duration:** Month 4–5

**Description:**\
Complete the core voting experience. Implement the Reveal step, simulate DAO voting lifecycle (epoch/slot/tally), and collect early user feedback.

**Main Tasks:**

* Implement Reveal UI and verification logic
* Build final Tally view and result display
* Simulate voting lifecycle (start, commit, reveal, close)
* Conduct small-group feedback sessions (community testers)
* Optimize interaction speed and mobile performance
* Prepare demo session for stakeholders

**Deliverables:**

* Fully working Reveal & Tally stages
* Vote lifecycle simulation (slot-based UI)
* Feedback collection report
* Performance improvement log
* Private testnet preview

***

#### ✅ **Milestone 4 – Public Demo Launch & Documentation**

**Duration:** Month 6

**Description:**\
Prepare a public release with clean documentation, a demo campaign, and open-source delivery. Ensure Catalyst visibility and future adoption by other projects.

**Main Tasks:**

* Final bugfix and UX polish
* Write full developer & user documentation
* Publish GitHub repository with open license
* Produce a demo video showcasing anonymous voting
* Release web demo version for live feedback
* Compile Catalyst report and future improvement roadmap

**Deliverables:**

* Open-source repo (frontend + demo logic)
* Demo video with narrative explanation
* Deployment to testnet or mock environment
* Final documentation (dev + user)
* Project closing report for Catalyst

***

### 💰 **Budget Breakdown** (Total: **89,201 ADA**)

* **Design & Frontend Development:** 31,300 ADA
* **Midnight SDK Integration (function calls, ZK commit/reveal handling):** 12,600 ADA
* **Privacy R\&D and ZK Logic Testing (UI test cases, simulations):** 15,100 ADA
* **UI Polish & Animation Performance Optimization:** 7,600 ADA
* **Community Feedback & Iteration Sessions:** 6,300 ADA
* **Project Management & Catalyst Reporting:** 3,800 ADA
* **Marketing & Public Demo Video:** 12,501 ADA
* **Total:** **89,201 ADA**

***

### 👥 **Team**

* **Project Manager / UI Architect:** Over 5 years of experience in blockchain and DAO systems (Cardano & Ethereum)
* **Frontend Developer (Rust/WASM + React):** Proven track record in building cross-chain dApps
* **ZK Research Specialist:** Supports R\&D, test case creation, and privacy logic validation
* **Design & Animation Lead:** Expert in Figma, Tailwind UI, and production-ready animation design
