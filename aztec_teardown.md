# Aztec Teardown

## 1. Problem Definition
Ethereum transactions are publicly visible.  
Every transfer links sender, receiver, amount, and timestamp.  
This exposes financial activity, balances, and sensitive transaction patterns.  

**Aztec solves this problem** by providing on-chain transaction privacy using zero knowledge proofs, allowing users to transfer tokens without revealing amounts or participants publicly.  
Unlike mixers, Aztec works **natively on-chain**, preserving privacy while remaining composable with other DeFi protocols.


## 2. How Privacy is Achieved and Trust Assumptions
Aztec uses **zk-SNARKs** and rollup technology to provide **confidential transactions** on Ethereum.  

**Mechanics:**  
- Users deposit tokens into **Aztec shielded pools**  
- Transactions generate **zero knowledge proofs** that verify correctness without revealing amounts or participants  
- Funds are transferred or swapped while remaining confidential on-chain  
- Rollups batch multiple transactions into a single proof, reducing gas costs while preserving privacy  

**Trust assumptions include:**  
- zk-SNARK circuits must be implemented correctly  
- Trusted setup (if applicable) must remain uncompromised  
- Smart contracts must be secure and verified  
- Users must follow privacy-preserving behavior (e.g., avoid linking shielded addresses externally)  
- Relayers, sequencers, or coordinators should not leak metadata  

**Key takeaway:**  
Privacy in Aztec is **protocol-enforced**, but security depends on correct cryptography, contract integrity, and proper usage by participants.


## 3. Limitations and Tradeoffs
- **Complexity and UX:** Users must interact with shielded pools and manage privacy-aware wallets  
- **Gas and fees:** Shielded transactions are more expensive than regular transfers, even with rollups  
- **Liquidity dependency:** Privacy guarantees improve with higher pool participation; small pools reduce anonymity  
- **Partial privacy:** Metadata outside Aztec (timing, network observation, off-chain interactions) can still leak information  
- **Compatibility limits:** Not all DeFi protocols fully support Aztec shielded tokens, limiting composability  
- **Trust assumptions:** Trusted setup for zk-SNARKs (if used) and contract correctness are critical


## 4. Common User Misconceptions
- **“Full privacy everywhere”** – false; privacy is limited to shielded pools and on-chain interactions  
- **“Transactions are untraceable”** – false; metadata outside Aztec can still leak information  
- **“Any wallet can interact safely”** – false; only privacy-aware wallets prevent accidental linking  
- **“No trust required”** – false; smart contracts, zk circuits, and relayers must function correctly  
- **“Completely gas-free privacy”** – false; shielded transactions are still more expensive than public transfers


## 5. User Suitability
**Recommended for:**  
- Users who need on-chain transaction privacy without relying on mixers  
- Users willing to manage shielded wallets and privacy-aware behavior  
- Builders integrating privacy into DeFi protocols  

**Not recommended for:**  
- Users expecting complete anonymity outside Aztec  
- Users unwilling to handle extra UX complexity or higher gas costs  
- Users relying on unsupported DeFi protocols for shielded interactions