# Cerberus ETC Miner

A CPU-based Ethereum Classic (ETC) mining tool written in C++. This tool connects to a mining pool using the Stratum protocol and provides real-time mining statistics.

![6181300397235357465](https://github.com/user-attachments/assets/8a1e0cd8-f847-4833-aea7-b3463c00ccc3)

---

## Features
- **Multi-threaded CPU mining**: Utilizes all available CPU cores for efficient mining.
- **Stratum protocol support**: Connects to mining pools for job distribution and share submission.
- **Real-time statistics**: Displays hashrate, shares submitted, and elapsed time using `ncurses`.
- **Configurable settings**: Easily configure wallet address, worker name, and pool settings.

---

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

---

## Requirements
- **C++17 or higher**: The project uses modern C++ features.
- **Boost.Asio**: For networking (Stratum protocol communication).
- **OpenSSL**: For cryptographic hashing (Keccak-256).
- **nlohmann/json**: For JSON parsing (Stratum protocol messages).
- **ncurses**: For the terminal-based user interface.

---

## Installation

### 1. Install Dependencies

#### On Ubuntu/Debian
Run the following commands to install all required dependencies:

sudo apt update
sudo apt install build-essential cmake libboost-all-dev libssl-dev libncurses5-dev libncursesw5-dev nlohmann-json3-dev
g++ -o etc_miner src/cerberus_etc_miner.cpp -Iinclude -lboost_system -lssl -lcrypto -lncurses -lpthread
./etc_miner


### 2. On macOS

Install dependencies using Homebrew:


brew update
brew install cmake boost openssl ncurses

### 3. On Windows

Install MSYS2.

Open the MSYS2 terminal and install dependencies:


pacman -S mingw-w64-x86_64-gcc mingw-w64-x86_64-cmake mingw-w64-x86_64-boost mingw-w64-x86_64-openssl mingw-w64-x86_64-ncurses

