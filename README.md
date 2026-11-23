# ChainPass – Decentralized Event Ticket Booking System

**A Blockchain-Based Event Booking Platform with Verifiable NFT Tickets**

---

## 1. Project Overview

ChainPass is a decentralized event ticket booking system designed to address the problem of trust, security and transparency in traditional digital ticketing platforms.

In conventional ticketing systems, users may face issues such as counterfeit tickets, duplicate ticket distribution, unauthorized resale and difficulty verifying ticket ownership.

ChainPass addresses these challenges by using blockchain technology and smart contracts to manage ticket creation, booking and ownership verification.

The system also incorporates Account Abstraction for a simplified transaction experience, Chainlink VRF for fair reward selection and The Graph for efficient blockchain data retrieval.

**Primary Objective:** To develop a secure, transparent and user-friendly event ticket booking system where ticket ownership and booking transactions can be independently verified.

---

## 2. Problem Statement

Traditional event ticket booking platforms have several limitations:

- **Ticket Fraud:** Digital tickets can be duplicated or counterfeited.
- **Ownership Verification:** Users have limited independent ways to verify the authenticity and ownership of tickets.
- **Centralized Control:** Ticket issuance and transaction records depend heavily on centralized platform infrastructure.
- **Transaction Transparency:** Users cannot independently verify all booking operations through a public, tamper-resistant record.
- **Web3 Usability:** Blockchain-based booking introduces additional complexity through wallet management and gas fees.

### Core Problem

How can we develop an event ticket booking system that provides verifiable ticket ownership, transparent booking transactions and a simplified user experience?

---

## 3. Motivation

The motivation behind ChainPass is to improve trust in digital event ticketing.

As online event booking becomes increasingly common, users need a reliable mechanism to verify that their tickets are authentic and that ownership records cannot be arbitrarily manipulated.

Blockchain provides an opportunity to address this issue through decentralized record-keeping and smart contract-based ticket issuance.

We chose this problem because it combines a practical real-world requirement with the application of Software Engineering principles and blockchain technology.

---

## 4. Proposed Approach

ChainPass follows a smart contract-based ticket management approach.

### Step 1: Event Creation
- Organizers create events by providing event details, ticket prices and booking information.
- Organizers stake ETH as part of the event creation mechanism.

### Step 2: Ticket Booking
- Users connect their wallets and select an event.
- A booking transaction is submitted through the Account Abstraction mechanism.
- The smart contract processes the booking and mints an ERC-721 NFT ticket.

### Step 3: Ownership Verification
- Each ticket is represented by a blockchain-based NFT.
- Ticket ownership can be verified through its on-chain token record.
- Smart contracts manage ticket issuance and ownership transfers.

### Step 4: Reward Distribution
- Chainlink VRF generates verifiable random numbers for selecting a cashback winner.
- This avoids relying on an organizer-controlled random selection process.

### Step 5: Data Retrieval
- The Graph indexes blockchain events.
- GraphQL queries retrieve the required event and ticket information for the frontend.

---

## 5. Why Did We Choose This Approach?

An important part of our development was selecting appropriate technologies based on the requirements of the system.

| Requirement | Selected Approach | Reason for Selection |
|---|---|---|
| Ticket ownership | ERC-721 NFTs | Provides unique, verifiable digital ticket ownership |
| Transaction management | Smart Contracts | Enables programmable and transparent booking operations |
| Gas fee complexity | ERC-4337 Account Abstraction | Supports sponsored transactions through a Paymaster |
| Random winner selection | Chainlink VRF | Provides verifiable randomness instead of organizer-controlled selection |
| Blockchain data retrieval | The Graph + GraphQL | Avoids repeatedly retrieving and processing all required data directly from blockchain RPC calls |

### Important Engineering Decisions

**1. Why NFT instead of a conventional database ticket?**

A conventional database stores ticket information under the control of the application backend. An ERC-721 NFT represents a uniquely identifiable blockchain asset whose ownership can be independently verified on-chain.

**2. Why Account Abstraction instead of conventional wallet transactions?**

Conventional blockchain transactions generally require users to hold ETH for gas fees. ERC-4337 allows UserOperations and sponsored transactions through a Paymaster, reducing this barrier for users.

**3. Why Chainlink VRF instead of ordinary random number generation?**

Randomness generated through ordinary application code or organizer-controlled logic can be manipulated. Chainlink VRF provides cryptographically verifiable randomness for reward selection.

**4. Why The Graph instead of directly querying blockchain RPC endpoints?**

Direct RPC queries are useful for blockchain interaction, but retrieving and filtering large amounts of historical event data repeatedly can be inefficient. The Graph indexes blockchain events and exposes structured GraphQL queries for the application.

---

## 6. Role of Software Engineering

Software Engineering principles were applied throughout the development of ChainPass.

- **Requirement Analysis:** Identifying the problems associated with conventional event ticket booking and defining system requirements.
- **System Design:** Designing the interaction between the frontend, wallet, smart contracts and blockchain indexing layer.
- **Modular Architecture:** Separating ticket management, event creation, transaction handling and data retrieval into distinct components.
- **Technology Selection:** Evaluating technologies based on security, functionality, usability and system requirements.
- **Integration:** Connecting smart contracts with the frontend, Account Abstraction infrastructure, Chainlink VRF and The Graph.
- **Reliability and Security Considerations:** Using smart contract-based ownership records and verifiable randomness to reduce dependence on centralized trust.

The objective was not simply to implement blockchain features, but to integrate different components into a coherent software system.

---

## 7. Outcomes and Significance

ChainPass demonstrates how blockchain technology can improve the reliability and transparency of event ticket booking.

The key outcomes are:

1. **Verifiable Ownership:** NFT-based tickets provide an independently verifiable record of ownership.
2. **Transparent Transactions:** Booking and ticket issuance operations are recorded on the blockchain.
3. **Improved Accessibility:** Account Abstraction with gas sponsorship reduces the need for users to manage gas fees themselves.
4. **Fair Reward Selection:** Chainlink VRF provides verifiable randomness for cashback distribution.
5. **Efficient Data Access:** The Graph and GraphQL provide an indexed data retrieval layer for event information.

These outcomes demonstrate the practical application of Software Engineering and decentralized technologies to a real-world booking problem.

---

## 8. Innovation and Uniqueness

The innovation in ChainPass lies in integrating multiple blockchain mechanisms into a single event ticket booking workflow.

Unlike a conventional ticket booking application, ChainPass combines:

- NFT-based ticket ownership and verification.
- Gas-sponsored transactions through ERC-4337 Account Abstraction.
- Verifiable reward selection through Chainlink VRF.
- Indexed blockchain data retrieval through The Graph.
- An organizer staking mechanism to introduce an additional accountability layer.

Rather than using blockchain merely to store ticket information, the system integrates it into the actual booking and ownership management process.

---

## 9. Technology Stack

| Component | Technology |
|---|---|
| Smart Contracts | Solidity |
| Blockchain Network | Ethereum Sepolia |
| Ticket Standard | ERC-721 |
| Account Abstraction | ERC-4337 |
| Bundler / Paymaster Infrastructure | Pimlico |
| Randomness | Chainlink VRF |
| Blockchain Indexing | The Graph |
| Query Language | GraphQL |
| Frontend | React |
| Wallet Integration | Wagmi |
| Programming Language | TypeScript |

---

## 10. Conclusion

ChainPass demonstrates an alternative approach to digital event ticket booking by combining decentralized ownership, transparent transaction processing and simplified blockchain interactions.

The project focuses on solving a specific real-world problem through appropriate technology selection, modular system design and integration of blockchain infrastructure.

**Our goal is to make event ticket booking more trustworthy without making the user experience unnecessarily complicated.**

---

## 11. Deployment

**Live Application:** https://esha-omega.vercel.app/

**Network:** Ethereum Sepolia Testnet

