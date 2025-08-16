# Roadmap

### &#x20;**Milestone 1 – Project Setup & SDK Design**

* Set up the GitHub repository and initial codebase structure.
* Define interfaces between **vote-core**, **vote-test-env**, and **vote-cli**.
* Design JSON schemas for key entities: **poll**, **voterSet**, **vote**, and **result**.
* Prepare the technical plan and break down tasks by module.

Timeline: 1st month

***

### &#x20;**Milestone 2 – Develop vote-core & test-env**

* Implement **core voting logic**: create polls, cast votes, tally results, and export final outcomes.
* Build the simulated testing environment (**vote-test-env**) using JSON datasets and voter list files.
* Write basic unit tests for each main function in the core module to ensure correctness.

Timeline: 2-3rd month

***

### &#x20;**Milestone 3 – Build CLI Tool & Draft Documentation**

* Develop the **vote-cli** using Node.js CLI (or Rust CLI) to allow:
  * Creating polls
  * Casting votes
  * Viewing results
* Integrate **vote-core** with CLI and test-env for end-to-end functionality.
* Draft technical documentation: project structure, module diagrams, and usage guides.

TImeline: 4-5th month

***

### &#x20;**Milestone 4 – Internal Review & Finalization**

* Refactor and optimize the codebase; test edge cases and uncommon scenarios.
* Compile all documentation: **vote-docs**, **handover.md**, JSON schemas, and lessons learned.
* Prepare a clean, production-ready package for handover to the Demo App development team.

Timeline: 6th month
