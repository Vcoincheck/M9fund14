# Phase 3 - Documentation & Sample Integration Kit

**Description**\
Develop a command-line tool (`vote-cli`) to interact with the existing voting logic system, while also connecting directly to `vote-test-env`. This tool will help the development, testing, and SDK maintenance teams use the system more easily — even in scenarios where Midnight’s testnet is not yet stable.

***

**📌 Main Tasks**

**Design CLI structure**

* Identify the main command groups: `create-poll`, `cast-vote`, `tally`, `export-result`
* Define input/output schemas compatible with `vote-core`

**Develop `vote-cli`**

* Implement the tool in Rust or TypeScript, depending on the SDK context for Midnight
* Integrate directly with `vote-core` through bindings or internal imports
* Allow configuration of mock voters, stakes, and voting parameters via JSON file

**Connect to test environment**

* Enable two-way communication between `vote-cli` and `vote-test-env`
* Run simulated voting scenarios: valid vote, double-vote, expired vote, incorrect stake tally, etc.

**Logging & result export**

* Output a full voting process log to `.json` or `.csv` file
* Allow exporting results in Merkle root format or as a serialized object

**User documentation**

* Write CLI documentation: syntax, usage examples, basic troubleshooting

<figure><img src="../../../.gitbook/assets/Milestone1 _ Mermaid Chart-2025-08-01-034709.png" alt=""><figcaption></figcaption></figure>

***

**📤 Deliverables**

* `vote-cli` source code with an easily extensible structure
* Sample configuration files: `poll.json`, `voterSet.json`
* Full integration with `vote-test-env`
* Logging and offline vote result export system
* CLI user guide for testers and developers

***

**🧩 Technical Notes**

* The CLI is independent of the real Midnight testnet (can run locally)
* Designed for easy future integration with the SDK (as proposed in Proposal #2)
* Modular CLI structure to support straightforward wrapping into a web UI if needed
