---
title: "Blog 2"
date: 2026-07-06
weight: 2
chapter: false
pre: " <b> 3.2. </b> "
---


# Building Secure, Verifiable Blockchain Key Management on AWS Nitro Enclaves at Turnkey

![Building Secure, Verifiable Blockchain Key Management](/images/turnkey-nitro-enclaves.png)

Recent private key breaches have made "Key Management" a major pain point for Web3/DeFi developers. This blog from the AWS Web3 Blog explores how Turnkey solves this problem by combining cryptography with AWS Nitro Enclaves hardware infrastructure to establish a truly secure, verifiable key management system.

## 1. Challenges in Current Key Management Architecture

The traditional transaction signing process forces a trade-off between security and operational efficiency:

- **DIY Infrastructure:** Requires significant cost and faces high compliance risks.
- **Third-Party Custodians:** Reduces direct control and lacks operational transparency.
- **General Software Infrastructure:** Raw keys risk exploitation through memory dumps or log files when the ecosystem is compromised.

## 2. AWS Nitro Enclaves Isolation Mechanism

Turnkey implements an Enclave-Native Key Management model, moving all sensitive operations—including key generation, signing, and policy execution—into AWS Nitro Enclaves:

- **Hardware Isolation:** The enclave environment has no persistent storage, no interactive access (no SSH), and no Internet connectivity.
- **Secure Communication:** Data is transmitted via internal VSOCK. Configuration keys are only decrypted in RAM at transaction signing time and deleted immediately. Neither Turnkey nor AWS administrators can access raw keys.

## 3. Cryptographic Data Initialization and Storage Process

The system uses a Hierarchical Deterministic (HD) Wallet model to manage derived key structures:

- **Seed Initialization:** Uses secure random number generation provided by the Nitro Security Module (NSM) hardware.
- **Symmetric Encryption:** The original seed chain is encrypted through the Quorum Key before being stored in the database.
- **Transaction Signing:** The ciphertext is loaded into the enclave, temporarily decrypted in RAM to perform cryptographic signing, then wiped clean. Raw keys are never written to disk storage.

## 4. State Separation Architecture and Data Flow

Turnkey's architecture is divided into two isolated partitions: the external management partition and the internal computing partition.

**External (AWS Cloud Infrastructure):**
When users send requests via API Gateway, EC2 servers (Coordinator) receive and process them. State data and encrypted raw keys are stored in Aurora Database. Background tasks such as Async Queue, Redis, Updater, Heartbeat, and Notifier only handle system synchronization and notifications. This partition has no knowledge of raw keys.

**Internal (AWS Nitro Enclave):**
EC2 servers route sensitive commands to the Enclave via internal gRPC/VSOCK. Within this isolated environment, processing flows through 5 steps:
- **TLS Fetcher:** Establishes secure network connections from inside.
- **Parser:** Extracts transaction metadata.
- **Policy Engine:** Checks whether transactions violate user rules (limits, blocklists, etc.).
- **Notarizer:** Signs transaction validity certificates after passing the policy engine.
- **Signer:** Retrieves encrypted keys from the database, temporarily decrypts in RAM to sign the transaction, then immediately wipes all traces.

## 5. Remote Mathematical Verification Mechanism

Turnkey shifts from a trust-based model to a verifiable model based on:
- **Remote Attestation:** AWS provides cryptographically signed attestation documents to verify that enclave code has not been altered or compromised.
- **Reproducible Builds:** The system runs on QuorumOS, a minimal operating system. Independent parties can rebuild the source code from scratch to verify system integrity.

---
**Summary:** Turnkey's solution leverages AWS Nitro Enclaves to establish a closed-loop key processing workflow in RAM with automatic memory release after use. The complete separation between state storage and isolated hardware execution environments protects digital assets even when virtual server infrastructure is compromised. Through remote attestation and reproducible builds, the system allows users to verify the integrity and transparency of the entire cryptographic process.

**Reference:** [Building secure, verifiable blockchain key management on AWS Nitro Enclaves at Turnkey](https://aws.amazon.com/blogs/web3/building-secure-verifiable-blockchain-key-management-on-aws-nitro-enclaves-at-turnkey/)

---
