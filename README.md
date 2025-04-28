# CryptoDevs NFT Collection

## Overview
**CryptoDevs** is a limited edition NFT collection built on the Ethereum blockchain.  
The project uses two smart contracts:
- `CryptoDevs.sol`: An ERC721 NFT contract with whitelist functionality.
- `Whitelist.sol`: A simple contract to manage and restrict the number of addresses eligible for whitelist minting.

This project is built using Solidity and OpenZeppelin smart contracts to ensure security and standard compliance.

---

## Features
- **Whitelist-based minting**:  
  Whitelisted users can mint a free NFT (one per address).
- **Public minting**:  
  Non-whitelisted users can mint by paying a fixed price (0.01 ETH).
- **Limited supply**:  
  A maximum of 20 NFTs can ever be minted.
- **Ownership privileges**:  
  Contract owner can withdraw all collected Ether from the smart contract.
- **Gas-efficient**:  
  Designed to protect reserved whitelist slots and optimize minting logic.

---

## Smart Contracts

### 1. Whitelist.sol
- Manages whitelisted addresses.
- Limits the number of whitelisted users based on a maximum cap set during deployment.
- Allows users to self-whitelist if slots are available.

### 2. CryptoDevs.sol
- ERC721 NFT smart contract (using OpenZeppelin’s `ERC721Enumerable` and `Ownable`).
- Integrates with the deployed `Whitelist` contract to manage minting eligibility.
- Handles minting payments for public users.
- Provides a secure withdrawal function for the owner.

---

## Installation and Deployment

1. **Clone the repository**
   ```bash
   git clone https://github.com/your-username/your-repo-name.git
   cd your-repo-name
   ```

2. **Install Foundry**
   Foundry is a blazing fast, portable, and modular toolkit for Ethereum application development written in Rust.
   ```bash
   curl -L https://foundry.paradigm.xyz | bash
   foundryup
   ```

3. **Compile Contracts**
   ```bash
   forge build
   ```

4. **Deploy Whitelist Contract**
   Deploy the `Whitelist` contract first and note its deployed address.

5. **Deploy CryptoDevs Contract**
   Use the deployed `Whitelist` contract address in the constructor of `CryptoDevs`.

---

## Project Structure

```
/contracts
    ├── CryptoDevs.sol
    └── Whitelist.sol
/script
    ├── Deploy.s.sol (deployment scripts)
/test
    ├── CryptoDevs.t.sol
    └── Whitelist.t.sol
foundry.toml
README.md
```

---

## Technologies Used
- [Solidity](https://soliditylang.org/)
- [OpenZeppelin Contracts](https://docs.openzeppelin.com/contracts/)
- [Foundry](https://foundry.paradigm.xyz/)
- [Ethereum Blockchain](https://ethereum.org/)

---

## Future Improvements
- Add a metadata URI base (`_baseTokenURI`) to support NFT images and attributes.
- Add "Reveal" feature (hidden NFTs before reveal).
- Enable batch minting.
- Implement whitelist and public sale phases separately.
- Add pausable functionality for emergency stops.

---

## License
This project is licensed under the [MIT License](LICENSE).

---

## Acknowledgments
- [OpenZeppelin](https://github.com/OpenZeppelin/openzeppelin-contracts) for secure and audited smart contract libraries.
- [Foundry](https://foundry.paradigm.xyz/) for fast Solidity development tools.

---

## Contact
For any questions or collaboration requests, feel free to reach out! 🚀
