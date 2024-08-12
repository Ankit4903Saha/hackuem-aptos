# NFT Wallet Module

This module provides basic functionality for managing non-fungible tokens (NFTs) on the Aptos blockchain. It includes operations for minting, burning, depositing, withdrawing, and transferring NFTs. Additionally, it supports balance checks and ensures proper balance management.

## Overview

The `nft-addr` module implements the following features:

- **Minting**: Create new NFTs with a specified value.
- **Burning**: Remove NFTs from existence.
- **Balance Management**: Create and manage balances for addresses.
- **Depositing & Withdrawing**: Transfer NFTs between balances and manage balances of individual accounts.
- **Transferring**: Move NFTs from one address to another.

## Installation and Setup

1. **Clone the Repository**

   ```bash
   git clone https://github.com/your-repo/nft-wallet-module.git
   cd nft-wallet-module
   ```

2. **Set Up Dependencies**

   Ensure you have the Aptos CLI and Move CLI installed. The `nft-wallet-module` relies on the Aptos framework for core functionalities.

   ```bash
   aptos move repo init
   ```

   Update the `Cargo.toml` with the Aptos framework dependency:

   ```toml
   [dependencies.AptosFramework]
   git = "https://github.com/aptos-labs/aptos-core.git"
   rev = "mainnet"
   subdir = "aptos-move/framework/aptos-framework"
   ```

3. **Build the Module**

   Use the Move CLI to compile the module:

   ```bash
   move build
   ```

## Usage

### Functions

- **mint(val: u64) -> NFT**  
  Create a new NFT with the specified value.

- **burn(coin: NFT)**  
  Remove the specified NFT.

- **create_balancce(acc: &signer)**  
  Initialize a balance for the given address.

- **balance_exists(acc_addr: address) -> bool**  
  Check if a balance exists for the given address.

- **balance(owner: address) -> u64**  
  Retrieve the balance of NFTs for the given address.

- **deposit(acc_addr: address, token: NFT)**  
  Deposit an NFT into the balance of the specified address.

- **withdraw(acc: address, value: u64) -> NFT**  
  Withdraw a specified amount of NFTs from the balance of the address.

- **transfer(from: &signer, to: address, amount: u64)**  
  Transfer NFTs from one address to another.

### Testing

The module includes a test function to verify its operations. To run the tests, use:

```bash
move test
```

The test case `test_use_some_coins` performs the following actions:

1. Mints 10 NFTs.
2. Creates a balance for an address.
3. Deposits 10 NFTs into the balance.
4. Withdraws 5 NFTs.
5. Burns the withdrawn NFTs.


## Configuration

The module's addresses and dependencies are configured in the `Cargo.toml` file:

```toml
[addresses]
nft-addr = '0x0dc80a9f9c33215a41a19b15635659ea6380734df94b3ea5d6ecbe0910fc2cc8'
```

