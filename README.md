
---

# OTP Authentication System using Blockchain Technology

## 🔐 Overview

This project is a **decentralized One-Time Password (OTP) authentication system** that leverages blockchain technology for secure, tamper-proof, and transparent user authentication. It eliminates centralized storage vulnerabilities by storing OTP hashes on a blockchain network (e.g., Ethereum or a private chain) and verifying OTPs through smart contracts.

## 🚀 Features

* ✅ OTP generation and verification
* 🔗 Blockchain-based OTP hash storage
* 🔐 Immutable verification with smart contracts
* 🌐 Web frontend (React/Flutter/dApp) for user interface
* ⚙️ Backend (Node.js/Python/Go) for OTP generation and transaction signing
* 📜 Solidity smart contract for OTP validation

## 🧠 Tech Stack

| Layer           | Technology                   |
| --------------- | ---------------------------- |
| Blockchain      | Ethereum / Ganache / Hardhat |
| Smart Contracts | Solidity                     | 
| Backend         | Node.js / Python             |
| Web3            | Web3.js / Ethers.js          |
| Wallet          | MetaMask / WalletConnect     |

---

## 🛠️ Installation & Setup

### 1. Clone the Repository

```bash
git clone https://github.com/yourusername/otp-blockchain-auth.git
cd otp-blockchain-auth
```

### 2. Install Dependencies

#### Backend

```bash
cd backend
npm install
```

#### Smart Contract

```bash
cd smart-contract
npm install
npx hardhat compile
```

#### Frontend

```bash
cd frontend
npm install
```

---

## 🧪 Usage

### 1. Start Local Blockchain

```bash
cd smart-contract
npx hardhat node
```

### 2. Deploy Smart Contract

```bash
npx hardhat run scripts/deploy.js --network localhost
```

### 3. Run Backend Server

```bash
cd backend
node server.js
```

### 4. Start Frontend

```bash
cd frontend
npm start
```

---

## ⚙️ How It Works

1. **OTP Generation:** A temporary OTP is generated on the backend.
2. **Hashing:** OTP is hashed and stored on the blockchain via a smart contract.
3. **User Entry:** User enters the OTP in the frontend.
4. **Verification:** Frontend hashes the OTP and calls the smart contract to verify it against the stored hash.
5. **Result:** Smart contract returns true/false based on match.

---

## 📄 Smart Contract Example

```solidity
// SPDX-License-Identifier: MIT
pragma solidity ^0.8.0;

contract OTPAuth {
    address public owner;
    mapping(address => bytes32) public otpHashes;

    constructor() {
        owner = msg.sender;
    }

    function storeOTP(address user, bytes32 otpHash) public {
        require(msg.sender == owner, "Only owner can store OTP");
        otpHashes[user] = otpHash;
    }

    function verifyOTP(address user, string memory otp) public view returns (bool) {
        return keccak256(abi.encodePacked(otp)) == otpHashes[user];
    }
}
```
---

## 🛡️ Security

* OTP never stored in plaintext
* OTP hash is immutable on-chain
* Only admin can write OTP hashes to the contract

---

![WhatsApp Image 2025-06-09 at 16 26 32_fa46ad0c](https://github.com/user-attachments/assets/cf915edd-1f96-4887-8b8d-44ad5a341d45)

![WhatsApp Image 2025-06-09 at 16 26 31_5773291a](https://github.com/user-attachments/assets/dd7f5b3f-95f1-4baf-bc33-13c0c7844307)

![WhatsApp Image 2025-06-09 at 16 26 32_3c486303](https://github.com/user-attachments/assets/82a6f438-3e26-4404-ae66-d55bae23deb5)



