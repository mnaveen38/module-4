# Token 

This repository contains a Solidity smart contract named `Token` that extends the ERC20 token standard and includes additional functionality for managing ownership, minting, burning, and redeeming devices using the token.

## Overview

### ERC20 Token
The `Token` contract is an ERC20-compliant token with the name "degen" and symbol "dgn." It has a total initial supply of 100 tokens, minted to the contract deployer's address.

### Ownership
The contract includes the `Ownable` module, ensuring that certain functions can only be executed by the contract owner.

### Device Redemption and Conversion
The contract introduces functionality to redeem and convert devices using the tokens. Devices are represented by their names, each having an associated fare and weight. Users can redeem devices by burning the required tokens, and device weights are adjusted accordingly. Conversely, users can convert tokens to devices, increasing the device weights.

## Functionality

### 1. Mint Tokens
The owner can mint additional tokens to a specified account using the `mintTokens` function.

### 2. Burn Tokens
Token holders can burn their own tokens using the `burnTokens` function, provided they have sufficient funds.

### 3. Transfer Tokens
Token holders can transfer tokens to another address using the `transferTokens` function, ensuring they have enough tokens for the transfer.

### 4. Redeem Device
Users can redeem devices by burning the required tokens. The function `redeemDevice` checks the user's token balance, verifies the device's availability, and adjusts the device weights accordingly.

### 5. Convert to Devices
Token holders can convert their tokens to devices using the `convertToDevices` function. The function checks the user's token balance, and upon successful conversion, it increases the associated device's weight.

## Device Configuration

The contract initializes with default configurations for four devices: Television, Speaker, GamingConsole, and Refrigerator. Each device has a fare and weight assigned during contract deployment.

## Events

The contract emits two events:
1. `LogMessage`: Logs generic messages for various operations.
2. `GadgetsConverted`: Signals the successful conversion of tokens to devices, providing details such as the user's address, device name, and quantity.

## Usage

To use the contract, deploy it to a compatible Ethereum Virtual Machine (EVM) and interact with it through supported Ethereum wallets or decentralized applications.

## Testing

The contract can be tested using Ethereum development frameworks such as Truffle or Hardhat. Tests should cover various scenarios, including minting, burning, transferring, redeeming devices, and converting tokens to devices.

## License

This smart contract is licensed under the MIT License. See the provided `LICENSE` file for details.
