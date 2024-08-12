# CoNode: Decentralized Labor Market Protocol

## Overview

CoNode is a peer-to-peer protocol designed to create a decentralized labor market. It enables users to broadcast, discover, and accept job opportunities without relying on centralized platforms, fostering a more open and efficient job market.

## Core Components

1. **Node**: Individual participant in the CoNode network.
2. **Job**: Representation of a work opportunity.
3. **Network**: P2P infrastructure for communication.
4. **Blockchain**: For job verification and permanent storage.

## Architecture

CoNode is built on a modular architecture, with each component serving a specific purpose:

### 1. Node

- `node/labor_market_node.rs`: Defines the main `LaborMarketNode` struct and its implementation.

### 2. Job Management

- `job/job.rs`: Defines the Job struct and related operations.
- `job/job_store.rs`: Manages local storage and retrieval of jobs.

### 3. Networking

- `network/behaviour.rs`: Implements the libp2p `NetworkBehaviour` for CoNode.
- `network/gossip.rs`: Handles the gossip protocol for job propagation.
- `network/sync.rs`: Manages the initial sync process for new nodes.
- `network/peer.rs`: Defines peer-related structures and operations.

### 4. Cryptography

- `crypto/keypair.rs`: Manages cryptographic keypairs.
- `crypto/signature.rs`: Handles signing and verification of jobs.
- `crypto/encryption.rs`: Provides encryption/decryption utilities.

### 5. Blockchain Integration

- `blockchain/interface.rs`: Interfaces with the Starknet blockchain for job verification.

### 6. Storage

- `storage/key_storage.rs`: Securely stores cryptographic keys.
- `storage/job_storage.rs`: Manages persistent storage of jobs.

### 7. Configuration

- `config/config.rs`: Handles application configuration.

### 8. Utilities

- `utils/error.rs`: Defines custom error types.
- `utils/logging.rs`: Provides logging functionality.

## Key Features

1. **Decentralized Job Posting and Discovery**: Users can post and find jobs without a central authority.
2. **Secure Identity Management**: Utilizes cryptographic keys for user identification and job signing.
3. **Job Verification via Blockchain**: Ensures the authenticity and immutability of job postings.
4. **Efficient Network Synchronization**: Combines initial sync and gossip protocols for up-to-date job information.

## Technology Stack

- **Language**: Rust
- **P2P Networking**: libp2p
- **Smart Contracts**: Cairo (Starknet)
- **Key Storage**: OS-native secure storage (via keyring crate)
