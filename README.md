# Blockchain-Based Academic Certificate Issuance & Revocation

## Overview

This project implements a **blockchain-based system for issuing, revoking, and verifying academic certificates** using Ethereum smart contracts and Hardhat.

The goal is to provide:
- **Tamper-proof issuance**
- **Immutable revocation records**
- **On-chain timestamps**
- **Cryptographic verification**
- **Full auditability via blockchain event logs**

The system is designed for **Distributed Systems & Blockchain coursework**, focusing on correctness, traceability, and trust minimization.

---
## 🚀 How to Run the Project ( Demo)

This project uses **Hardhat**, **Node.js**, and a local Ethereum blockchain for demonstration and evaluation.

---

###  Prerequisites

Make sure the following are installed:

- **Node.js** (v18 recommended)
- **npm**
- **Git**

Check installation:

```bash
node -v
npm -v
git --version


npx hardhat node
Start Local Blockchain (Hardhat Node)

Run a local Ethereum node:

npx hardhat node


This will start a JSON-RPC server at:

http://127.0.0.1:8545

Issue a new certificate using its unique ID:

node scripts/issue.js CSC-2023-ALI


Expected output:

✅ Issued: CSC-2023-ALI

-----------------------------------------------
Issue another certificate:

node scripts/issue.js CSC-2023-Bardia

6️⃣ Verify Certificate (Public Verification)

Anyone can verify a certificate without authentication:

node scripts/verify.js CSC-2023-ALI
-----------------------------------

Output example:

Issued: true
Revoked: false
Issued At: 1768500485
Revoked At: 0

7️⃣ Revoke a Certificate
------------------------------------
Revoke an issued certificate:

node scripts/revoke.js CSC-2023-ALI


Expected output:

🚫 Revoked: CSC-2023-ALI

8️⃣ Verify Revoked Certificate
------------------------------------
Verify again after revocation:

node scripts/verify.js CSC-2023-ALI


Output example:

Issued: false
Revoked: true
Issued At: 1768500485
Revoked At: 1768500745

----------------------

node scripts/readLogs.js CSC-2023-ALI
CERT ID: CSC-2023-ALI
CERT HASH: 0x488b23dd529acdd64ece5402572cb46d01799e9bab8604a3d872c651cf41f264
────────────────────────────
🟢 ISSUED
 Block: 3
 Time : 2026-01-22T11:12:29.000Z
 Tx   : 0xb6d18b2f0318399874017d712aabaf695cebbd086ccc6347141ab9add0a7c6e0

🔴 REVOKED
 Block: 4
 Time : 2026-01-22T11:13:51.000Z
 Tx   : 0x0506c78b17035f04edf57b58ad8cd1d64322e2d98dd373263036f1fcdf6de856

