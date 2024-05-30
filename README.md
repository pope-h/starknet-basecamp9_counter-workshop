# Starknet Counter Contract

This project implements a Counter smart contract on Starknet with an integrated Kill Switch and Ownable component from OpenZeppelin. The contract allows for incrementing a counter while checking the status of a kill switch and ensuring only the owner can perform certain actions.

## Features

- **Counter Functionality**: Increment and retrieve the counter value.
- **Kill Switch Integration**: Check the status of a kill switch before allowing counter increments.
- **Ownable Component**: Use OpenZeppelin's Ownable component to restrict access to certain functions to the contract owner.

## Prerequisites

- [Node.js](https://nodejs.org/) and npm installed
- [Starknet wallet](https://chrome.google.com/webstore/detail/argent-x/dlcobpjiigpikoobohmabehhmhfoodbb) (Argent X or Braavos)
- [Faucet](https://faucet.goerli.starknet.io/) funding for the Starknet testnet

## Installation

1. **Clone the repository**:
    ```bash
    git clone https://github.com/yourusername/starknet-counter-contract.git
    cd starknet-counter-contract
    ```

2. **Install dependencies**:
    ```bash
    npm install
    ```

## Configuration

1. **Create and Fund a Wallet**:
    - Create a wallet on the Starknet testnet using the Argent X or Braavos browser extension.
    - Fund the wallet using the Starknet faucet.

2. **Set Up Environment Variables**:
    - Create a `.env` file in the project's root folder:
    ```bash
    touch .env
    ```

    - Add the following variables to the `.env` file:
    ```
    DEPLOYER_PRIVATE_KEY=<YOUR_FUNDED_TESTNET_WALLET_PRIVATE_KEY>
    DEPLOYER_ADDRESS=<YOUR_FUNDED_TESTNET_WALLET_PUBLIC_ADDRESS>
    RPC_ENDPOINT=https://starknet-sepolia.public.blastapi.io/rpc/v0_7
    ```

## Deployment

1. **Run the Deployment Script**:
    ```bash
    npm run deploy
    ```

    Follow the instructions from the terminal. If the script finishes successfully, your smart contract will be deployed on the Starknet testnet.

## Contract Address

The deployed contract address on Starknet testnet is: 
- [Contract Address](https://sepolia.starkscan.co/contract/0x652bfa300f6a582517546fb442732fb8e115832eeb476664f5ae8138a64211e)
```
0x652bfa300f6a582517546fb442732fb8e115832eeb476664f5ae8138a64211e
```

## Usage

### Contract Interface

The `Counter` contract exposes the following methods:

- `get_counter() -> u32`: Returns the current counter value.
- `increase_counter()`: Increments the counter if the kill switch is not active.

### Ownership Functions

Using the Ownable component, the following methods are also available:

- `owner() -> ContractAddress`: Returns the current owner of the contract.
- `transfer_ownership(new_owner: ContractAddress)`: Transfers ownership to a new address.
- `renounce_ownership()`: Renounces ownership of the contract.

## Testing

Run the test suite to verify the contract's functionality:

```bash
snforge test
```

## Contributing

Feel free to submit issues or pull requests if you find any bugs or have suggestions for improvements.

## License

This project is licensed under the MIT License.