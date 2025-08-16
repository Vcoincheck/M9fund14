# Phase 2 - SDK Feature Development

### **Description**

Design and build the abstraction layer of the voting system — separating independent logic components for easier maintenance and scalability, enabling integration in applications using the SDK (such as the demo app or other future dApps).

***

### &#x20;**Main Tasks**

* Design a standardized module diagram for the SDK, including:
  * **VoteCore:** Voting logic
  * **VoteStore:** Temporary and persistent data storage
  * **VoteProof:** Simulated proof logic module (ZK optional)
  * **VoteClient:** Application interaction functions
* Refactor any existing prototype logic into a modular structure.
* Develop SDK interfaces (.ts, .rs, or .json schema depending on the build environment).
* Package the SDK into a library (alpha version) for internal testing imports.
* Write basic unit tests for each module.
* Package auto-generated documentation (if available) and prepare a draft user guide.

<figure><img src="../../../.gitbook/assets/Milestone1 _ Mermaid Chart-2025-08-01-034344.png" alt=""><figcaption></figcaption></figure>

***

### &#x20;**Deliverables**

* `sdk-core` source code in a modular structure, with a README for integration guidance.
* SDK library package in module or CLI format (alpha release).
* Architecture diagram of the SDK layers.
* Preliminary unit tests for the modules.
* Documentation describing how to integrate the SDK from external applications.

***
