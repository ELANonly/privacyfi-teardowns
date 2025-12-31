# Tornado Cash Teardown

## Problem Definition
Ethereum transactions are permanently public.  
Every transfer links sender, receiver, amount, and timestamp.  
Once an address is connected to a real identity, that connection cannot be undone.  
Users cannot receive funds privately after interacting publicly, separate identities for personal, work, DAO, or trading purposes, or reset privacy after a single exposure.  

Tornado Cash addresses this problem by breaking the direct on chain link between deposits and withdrawals. It allows users to move funds without carrying a permanent publicly traceable link.



## How Privacy Works and Trust Assumptions
Tornado Cash breaks the on chain link between deposits and withdrawals, not the visibility of activity itself.  

Users deposit fixed amounts into shared pools and generate cryptographic secrets. Withdrawals are proven via zero knowledge proofs, without revealing which deposit they correspond to. Privacy emerges from the anonymity set formed by all deposits in the pool.  

Privacy depends on several assumptions:  
- Smart contracts and zero knowledge circuits must be correct  
- The trusted setup must not be compromised  
- Users must follow privacy preserving behavior, avoiding address reuse and immediate withdrawals  
- External infrastructure like relayers or RPC providers must not leak metadata  
- Pools must have sufficient participation to maintain anonymity



## Limitations and Tradeoffs
-  Privacy depends on pool size and activity  
- Fixed denominations reduce flexibility  
- Timing patterns can leak links between deposits and withdrawals  
- UX requires managing secrets, generating new addresses, and sometimes waiting for large pools  
- Regulatory restrictions may limit usability  
- Does not hide balances or interactions outside the pool



## Common User Misconceptions
- “Full anonymity forever” – false  
- “Funds are untraceable” – false  
- “Any withdrawal is immediately safe” – false  
- “Guarantees legal safety” – false  
- “Behavior does not matter” – false  

Privacy depends on pool size, user behavior, and external context. Misunderstandings are common and overestimations are frequent.



## Who Should and Should Not Use Tornado Cash
**Recommended for:**  
- Users who understand privacy principles and follow best practices  
- People separating financial identities, e.g., personal, work, DAO, trading  
- Users willing to accept some UX friction for unlinkability  

**Not recommended for:**  
- Users expecting total anonymity or convenience  
- Users who reuse addresses, reveal metadata, or behave carelessly  
- Users in high regulatory risk jurisdictions  

Tornado Cash is powerful for unlinking transactions, but effectiveness depends on user sophistication, behavior, and context.
