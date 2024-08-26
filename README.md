# Vora bridge

## Introduction
The **Vora Protocol** is a cross-chain bridge solution that incorporates Zero-Knowledge Proof (ZK) technology to enhance security, privacy, and efficiency in cross-chain asset or data transfers.

This repository contains the implementation of a simple yet robust cross-chain bridge protocol using zk-SNARKs to generate and verify proofs of asset locks and transfers across different blockchain networks.

## Features
- **Zero-Knowledge Proofs**: Ensures privacy and security by generating and verifying proofs without revealing transaction details.
- **Decentralization**: Reduces reliance on centralized validators, making the bridge more decentralized.
- **Efficiency**: Fast and efficient proof verification on the target chain with minimal computational overhead.

## Protocol Overview

### 1. Asset Locking on Source Chain
- A user initiates a cross-chain transfer by locking assets on the source chain.
- A zk-SNARK proof is generated that confirms the lock without exposing the asset details.

### 2. Proof Generation
- The locking contract on the source chain generates a zk-SNARK proof containing the state hash and encrypted asset details.
- This proof is then transmitted to the target chain's verification contract.

### 3. Proof Verification on Target Chain
- The target chain verifies the proof using zk-SNARKs, ensuring the validity of the state and locked assets.
- Upon successful verification, the appropriate assets are released or state updated on the target chain.

### 4. Asset Release or State Update on Target Chain
- The target chain contract releases the corresponding assets or updates the state, completing the cross-chain transaction.

### 5. State Update on Source Chain
- Once the transaction is confirmed on the target chain, the source chain updates its state to reflect the completed transfer.