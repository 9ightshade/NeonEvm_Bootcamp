# 🚀 Neon EVM Dev Bootcamp: Mintable ERC-20-for-SPL Token Deployment

This project demonstrates how to deploy a **Mintable ERC-20-for-SPL Token** on **Neon EVM** (an Ethereum-compatible environment on **Solana**) and how to interact with Solana using composability features directly from Solidity smart contracts.

---

## 📖 Overview

- Deploy an **ERC-20-for-SPL Mintable Token** via Neon’s pre-deployed **Factory Contract**.
- Interact with Solana by creating token accounts and transferring tokens using composability helper contracts.
- Use familiar Ethereum tools: **Solidity**, **Hardhat**, **ethers.js** while leveraging Solana’s speed and low fees.

---

## 🔧 Environment Setup

### 1⃣⃣ MetaMask Configuration (Neon Devnet)

- **RPC URL:** `https://devnet.neonevm.org`
- **Chain ID:** `245022926`
- **Currency Symbol:** `NEON`
- **Explorer:** [https://neon-devnet.blockscout.com/](https://neon-devnet.blockscout.com/)

### 2⃣⃣ Faucets

- **Get NEON:** [https://neonfaucet.org](https://neonfaucet.org)
- **Get SOL:** [https://faucet.solana.com](https://faucet.solana.com)

### 3⃣⃣ Install Project Dependencies

```bash
npm install --save-dev @nomicfoundation/hardhat-toolbox
npm install --save @solana/web3.js @solana/spl-token bs58 dotenv
```

### 4⃣⃣ Configure `hardhat.config.js`:

```js
networks: {
  neondevnet: {
    url: "https://devnet.neonevm.org",
    chainId: 245022926,
    accounts: [process.env.PRIVATE_KEY_OWNER],
  },
}
```

---

## 🚀 Deployment Instructions

### 1⃣⃣ Clone the Repository

```bash
git clone git@github.com:neonlabsorg/neon-tutorials.git
cd neon-tutorials
git checkout -b dev-bootcamp-video
npm install
cp .env.example .env
```

### 2⃣⃣ Configure `.env`:

```ini
PRIVATE_KEY_OWNER=your_metamask_private_key
PRIVATE_KEY_SOLANA=your_solana_private_key_base58
USER1_KEY=any_dummy_key
```

✅ Make sure you have funded your wallets with NEON and SOL tokens.

### 3⃣⃣ Run Deployment Script:

```bash
npx hardhat run scripts/TestCallSolana/TestDevBootcamp.js --network neondevnet
```

---

## ✅ Deployment Results (Sample Output)

| **Component**            | **Address / PublicKey**                                                                    |
| ------------------------ | ------------------------------------------------------------------------------------------ |
| ERC-20-for-SPL Token     | `0x2c57FcCB2666EFd47645D8D91a77d3AEd20Af997`                                               |
| SPL Token Mint Address   | `0xdfa82188f199407ec1a471260cc768d37d8f74318ef249bf9176bdc9af483b35`                       |
| Helper Contract Deployed | `0xDFF2413cA71c335525c69615B0E396bc6A499731`                                               |
| Contract Public Key      | `BzY5xsuM1WwwfJpCmD8DfiszhXHeagt3vZDXu4W8AgJH`                                             |
| Sender ATA (Solana)      | `5ayFVWCbSxz6AYuk6opaH1HCcvDq2HpHYKTM3wKm3HxJ`                                             |
| Recipient ATA (Solana)   | `4mTq4EwkSf7AVGXmgaFqEA6VT85qQom8Mjjtt9xWfrb8`                                             |
| Solana Transaction       | `3UQ7cjusvnA6GNCsgQ3yYv9A4bZZ9JRc8SEBojyvS2VXQCRpyqtMfY5q1waL2Ui74kk5DybTwtxVXoAz9fvGeYnd` |

---

## 🔄 Key Transactions:

### 1. ERC-20-for-SPL Approval

- Transaction Hash:\
  `0x19268fe552d5c4b00ab647b9ca6c509e566ee358a6a2345c2b52aa1e3c18e30e`
- To: `0x2c57FcCB2666EFd47645D8D91a77d3AEd20Af997`

### 2. Composability Transfer (TestDevBootcamp)

- Transaction Hash:\
  `0x5edc3aaf3bd913c4f4b48a7ddb4ff18e6fdb133d03e7b4e1680395393778c805`
- To: `0xDFF2413cA71c335525c69615B0E396bc6A499731`

✅ Both transactions were executed on **Neon Devnet** (`chainId: 245022926`).

---

## 📝 What This Demonstrates

1. **ERC-20-for-SPL Deployment:**\
   A new SPL token was minted and wrapped with an ERC-20 interface, all without needing to write a full token contract.

2. **Solana Token Accounts Creation:**\
   Associated Token Accounts (ATAs) were automatically created for sender and recipient on Solana.

3. **Cross-Chain Token Transfer:**\
   A composability request was successfully sent from Neon EVM (Solidity) to Solana using the precompile `ICallSolana`.

---

## 🔗 Resources

- 🌐 [Neon EVM Website](https://neonevm.org)
- 📘 [Composability Whitepaper](https://neonevm.org/blog/unveiling-composability-whitepaper-a-unified-framework-for-ethereum–solana-interaction)
- 🛠 [Blockscout Explorer](https://neon-devnet.blockscout.com/)
- 💧 [NEON Faucet](https://neonfaucet.org)
- 💧 [SOL Faucet](https://faucet.solana.com)

---

✅ With **Neon EVM**, you can deploy Ethereum-native smart contracts and seamlessly interact with the Solana ecosystem—opening up new possibilities for multi-chain dApps.

