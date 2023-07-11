# Checks Contract

The `Checks` contract is a Solidity smart contract that allows users to transfer funds to a specific address while enforcing certain checks and limits. It provides functions to get the balance of an address and transfer funds to another address.

## License

The contract is licensed under the MIT License. Please see the [LICENSE](LICENSE) file for more details.

## Prerequisites

- Solidity compiler version 0.8.0 or compatible.

## Getting Started

Follow the steps below to get started with the `Checks` contract:

1. Install the Solidity compiler if you haven't already. You can find installation instructions on the [Solidity website](https://soliditylang.org/).

2. Clone or download the project repository.

3. Open the `Checks.sol` file in a Solidity development environment.

4. Compile the contract using the Solidity compiler. Ensure that the compiler version is set to at least 0.8.0.

5. Deploy the contract to a compatible Ethereum network of your choice, such as the Ethereum Mainnet, Ropsten, or a local development network.

## Contract Overview

The `Checks` contract includes the following functions and properties:

### `limit`

A public `uint` variable representing the transfer limit set to 10 ether. This specifies the maximum amount that can be transferred in a single transaction.

### `getBalance(address _address)`

A public view function that returns the balance of the specified address `_address`. It retrieves the balance using the `balance` property of the address.

### `InsufficientFunds()`

An error definition used when the sender's account balance is insufficient to perform the transfer.

### `SingleTransferLimitExceeded(uint256 amount, uint256 limit)`

An error definition used when the transfer amount exceeds the single transfer limit.

### `transfer(address payable _receiver, uint256 _amount)`

A public payable function used to transfer funds to the specified `_receiver` address. It takes an additional parameter `_amount` representing the amount of funds to transfer.

The function enforces the following checks:

- It verifies that the sender has provided sufficient funds by comparing `msg.value` (the amount sent with the transaction) with `_amount`.
- If the transfer amount exceeds the limit, it reverts the transaction with the `SingleTransferLimitExceeded` error.
- It uses the `call` function to transfer the specified `_amount` to the `_receiver` address. If the transfer fails, it reverts the transaction with the error message "Transfer failed".

## Usage

To use the `Checks` contract, follow these guidelines:

1. Deploy the contract to an Ethereum network of your choice.

2. Set the desired transfer limit by updating the `limit` variable in the deployed contract. By default, it is set to 10 ether.

3. Call the `transfer` function, providing the `_receiver` address and the `_amount` of funds to transfer. Ensure that you send at least the specified `_amount` of funds with the transaction.

4. If the transfer is successful, the funds will be transferred to the specified `_receiver` address. If any checks fail, the transaction will be reverted with an appropriate error message.

## Contributing

Contributions to the `Checks` contract are welcome. If you encounter any issues or have suggestions for improvements, please submit an issue or a pull request in the project repository.

## Disclaimer

This contract is provided as-is without any warranties or guarantees. Use it at your own risk.

## Contact

For any inquiries or questions, please contact [21BCS1573@cuchd.in].

