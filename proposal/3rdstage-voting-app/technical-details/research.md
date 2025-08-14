# Research

### **Technical Flow Description for ZK Commit–Reveal Voting dApp**

***

### **1. Start dApp**

* **Frontend Initialization**
  * Load dApp in browser (React/Vue/Svelte or similar).
  * Initialize **web3 provider** for Midnight blockchain.
  * Load configuration file (network endpoints, smart contract addresses, ZK circuit metadata).
  * Prepare state management store (Redux/Pinia/Zustand) to handle wallet state, proposal data, and voting session.
* **Security**
  * Enforce HTTPS & CSP (Content Security Policy).
  * Load Zero-Knowledge (ZK) proof WASM files from a trusted CDN or local bundle.
  * Initialize WebAssembly threads if supported for faster proof generation.

***

### **2. Connect Midnight Wallet**

* **Wallet Connection**
  * Request wallet provider (e.g., Midnight Wallet extension or injected API).
  * Request user's public key / DID (Decentralized Identifier).
  * Ensure wallet supports required ZK primitives (e.g., Groth16, Plonk).
* **Smart Contract Interaction**
  * Perform a `ping` call to verify network connectivity and correct chain ID.
* **Security**
  * User must approve connection via wallet popup.
  * Session-bound public key generated in wallet for temporary interactions.

***

### **3. ZK Authentication & Establish Session Key**

* **ZK Authentication**
  * The wallet signs a nonce provided by the backend or directly in smart contract memory.
  * Generate ZK proof that user owns a valid DAO membership NFT or voting rights token without revealing token ID.
    * Circuit Input: Merkle proof of membership, private key, DAO registry root.
    * Output: ZK proof + nullifier (prevents double registration).
* **Session Key Establishment**
  * Use **ECDH key exchange** between dApp and wallet for a symmetric session key.
  * Store key in browser memory (not localStorage) for ephemeral encryption of messages.

***

### **4. DAO Dashboard**

* **Data Fetch**
  * Query smart contract or indexer for:
    * Active proposals.
    * Proposal metadata IPFS hashes.
    * Current voting phase & deadlines.
  * Decrypt private messages (if proposal content is private) using session key.
* **Frontend UI**
  * Display:
    * Create Proposal button.
    * Active proposals list.
    * User's voting status.
  * Maintain websocket/subscription for live updates.

***

### **5. Create New Proposal → ZK Metadata & Deposit**

* **Proposal Creation**
  * User fills in title, description, options, metadata link (IPFS/Arweave).
  * Generate ZK proof of eligibility to create proposal (e.g., stake > threshold).
* **Deposit Handling**
  * User sends required token deposit via wallet to proposal registry contract.
* **On-chain Storage**
  * Smart contract emits `ProposalCreated` event with:
    * Proposal ID.
    * Metadata hash.
    * Proposer’s public key hash.
    * Voting start/end timestamps.

***

### **6. Proposal Listed**

* Event from blockchain confirms transaction.
* Proposal appears in dashboard after indexer sync.
* State updated in dApp store.

***

### **7. View Active Proposals**

* Fetch list of proposals from contract/indexer.
* Show:
  * Title, options, status, deadline.
  * ZK tally progress if available.
* If content encrypted, decrypt with DAO shared key.

***

### **8. Proposal Details**

* Fetch:
  * Metadata from IPFS.
  * Voting phase from contract.
  * Current vote counts (if tally phase).
* UI shows commit/reveal buttons depending on phase.

***

### **9. Commit–Reveal Voting (Main Voting Process)**

**Commit Phase**

1. **Generate ZK Proof of Voting Rights**
   * Inputs: DAO membership Merkle proof, voter private key, proposal ID.
   * Circuit ensures:
     * Voter is eligible.
     * Vote choice is hidden.
   * Output: Proof + nullifier (to prevent multiple commits).
2. **Submit Commit**
   * Create hash: `H(vote_choice || secret_salt)`.
   * On-chain transaction: store `(commit_hash, ZK_proof, nullifier)`.

***

**Reveal Phase**

1. **Submit Reveal**
   * Send `raw_vote_choice` + `secret_salt` to contract.
2. **ZK Verification & Commitment Check**
   * Smart contract recomputes `commit_hash` from revealed values.
   * If mismatch → reject.
   * Check nullifier not already used.

***

**Tally Phase**

1. **Aggregate Votes in ZK Tally Proof**
   * DAO tally authority or decentralized aggregator collects all reveals.
   * Runs ZK tally circuit:
     * Ensures only valid reveals counted.
     * Computes encrypted tally result.
2. **Generate Merkle Root & Publish Results**
   * Merkle root of votes stored on-chain.
   * ZK proof ensures correctness without revealing individual votes.

***

### **10. Wait Epoch Transition**

* This is the time between phases, defined by contract:
  * Commit → Reveal transition time.
  * Reveal → Tally transition time.
* dApp UI updates countdown timer in real-time.

***

### **11. Voting Results**

* Fetch tally proof from blockchain.
* Verify ZK proof client-side (optional).
* Display final results on UI.

***

### **12. Execute Proposal**

* If proposal passed:
  * Trigger contract execution (e.g., DAO fund transfer, parameter update).
  * Execution transaction signed by DAO multisig or automated governance executor.

***

### **13. Disconnect Wallet & Clear Session**

* Clear session key from memory.
* Close websocket connections.
* Reset dApp store state to initial.
