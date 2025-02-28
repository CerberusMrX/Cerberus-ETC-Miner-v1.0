# Cerberus-ETC-Miner-v1.0
# Cerberus ETC Miner

A CPU-based Ethereum Classic (ETC) mining tool written in C++. This tool connects to a mining pool using the Stratum protocol and provides real-time mining statistics.

## Features
- Multi-threaded CPU mining.
- Stratum protocol support.
- Real-time statistics display using `ncurses`.
- Configurable wallet address, worker name, and pool settings.

## Algorithms
### Ethash
Ethash is the proof-of-work algorithm used by Ethereum Classic (ETC). It is designed to be ASIC-resistant and memory-hard, making it suitable for GPU and CPU mining. The algorithm consists of two main components:
1. **DAG (Directed Acyclic Graph)**: A large dataset generated from the blockchain's history. Miners use the DAG to perform memory-intensive computations.
2. **Hashimoto**: A mining algorithm that combines cryptographic hashing with blockchain data to ensure fairness and security.

### Keccak-256
Keccak-256 is the cryptographic hash function used in Ethash. It is part of the SHA-3 family and is used to:
- Generate the DAG.
- Compute hashes during mining.
- Verify block headers and transactions.

### Stratum Protocol
The Stratum protocol is used for communication between miners and mining pools. It provides:
- Job distribution from the pool to the miner.
- Submission of shares (valid hashes) from the miner to the pool.
- Real-time updates on mining difficulty and new blocks.

## Requirements
- C++17 or higher.
- Boost.Asio (for networking).
- OpenSSL (for cryptographic hashing).
- nlohmann/json (for JSON parsing).
- ncurses (for the terminal UI).
