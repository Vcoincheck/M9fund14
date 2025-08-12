# Problem

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
