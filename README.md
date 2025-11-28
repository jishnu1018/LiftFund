#  LIFTFUND — Decentralized Crowdfunding Platform

LIFTFUND is a decentralized crowdfunding platform built on Ethereum blockchain. It allows users to create fundraising campaigns, contribute with crypto donations, and track campaign performance — securely and transparently on-chain.

---


## 🚀 Features

- 🔐 Connect your MetaMask wallet to interact with the platform
- 🎨 Create and manage your own crowdfunding campaigns
- 💸 Donate to campaigns using ETH
- 📊 View all active campaigns and their details
- 📜 Access platform White Paper and About Us information
- 📑 Track real-time donations to each campaign  
- 🌐 Fully decentralized, running on Ethereum testnet (Sepolia)

---

## 🛠️ Tech Stack

- **Frontend**: React, Tailwind CSS  
- **Blockchain**: Solidity, Hardhat (Sepolia Testnet)  
- **Smart Contract Interaction**: ethers.js  
- **Deployment**: Hardhat Ignition  

---
## 📖 Pages
- **Home Page**: Campaign creation, active campaigns list, user-created campaigns

- **White Paper**: Learn about the platform's mission, benefits, and blockchain usage

- **About Us**: Background about the FundFlow platform


# 📦 Setup Instructions

### 1️⃣ Clone the Repository

```bash
git clone https://github.com/your-username/FundFlow.git
cd FundFlow
```

### 2️⃣ Install Dependencies
```bash
npm install
```
### 3️⃣ Run the Frontend
```bash

npm run dev
```
Note: Make sure MetaMask is installed in your browser and connected to the Sepolia Testnet.


# 🔐 Smart Contract Deployment

### 1️⃣ Install Hardhat and initialize:

```bash
npm install --save-dev hardhat
npx hardhat
```
Choose Create a basic sample project if prompted.

### 2️⃣ Install dependencies:

npm install --save-dev @nomicfoundation/hardhat-toolbox @nomicfoundation/hardhat-ignition dotenv

### 3️⃣ Write your contract inside contracts/

contracts/CrowdFunding.sol

4️⃣ Compile the contract:

```bash
npx hardhat compile
```
### 5️⃣ Deploy to Sepolia using Hardhat Ignition:

Create ignition/modules/CrowdFundingModule.js:

```bash
const { buildModule } = require("@nomicfoundation/hardhat-ignition/modules");

module.exports = buildModule("CrowdFundingModule", (m) => {
  const crowdFunding = m.contract("CrowdFunding");
  return { crowdFunding };
});
```
Then deploy:

```bash
npx hardhat ignition deploy ignition/modules/CrowdFundingModule.js --network sepolia
```
Copy the deployed contract address.


# 📄 Setting ABI & Contract Address in Frontend
### 1️⃣ After compilation, find the ABI in:

```bash
artifacts/contracts/CrowdFunding.sol/CrowdFunding.json
```
Copy the "abi" array.

### 2️⃣ Create src/abi/CrowdFunding.json in frontend:

```bash
{
  "abi": [
    // copied ABI content here
  ]
}
```

### 3️⃣ Set contract address in your context/provider:

```bash
const contractAddress = "YOUR_DEPLOYED_CONTRACT_ADDRESS";
```

