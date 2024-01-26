# DegenToken 

## Overview

DegenToken is a Solidity smart contract that implements a simple ERC20 token with additional functionalities such as minting, burning, transferring tokens, and redeeming T-Shirts using tokens. The contract is deployed on the Ethereum blockchain and utilizes OpenZeppelin library for ERC20 implementation.

## Contract Features

### ERC20 Token

DegenToken implements the ERC20 standard functionalities including:
- Transfer tokens between addresses
- Approve and transferFrom mechanism
- Check balance of an address
- Total supply tracking

### Ownable

The contract inherits from Ownable, allowing the owner to perform certain privileged actions like minting tokens, modifying T-Shirt quantities, and adding T-Shirt types.

### ERC20Burnable

DegenToken extends ERC20Burnable, providing the ability to burn tokens, reducing the total supply.

### T-Shirt Redemption

Users can redeem T-Shirts by spending tokens. Each T-Shirt type has a defined cost and inventory. Users can exchange tokens for T-Shirts by specifying the type and quantity. The contract checks for the user's token balance, verifies the availability of the requested T-Shirt type and quantity, burns the required tokens, and updates the user's T-Shirt balance and T-Shirt inventory accordingly.

## Functions

### `mint(address recipientAddress, uint256 tokenAmount)`

Mints new tokens and assigns them to the specified recipient address. Only the contract owner can call this function.

### `burn_(uint256 tokenAmount)`

Allows users to burn their own tokens. Requires a sufficient balance. Emits a `LogMessage` event upon successful token burn.

### `transfer_(address recipientAddress, uint256 tokenAmount)`

Allows users to transfer tokens to another address. Requires a sufficient balance.

### `redeemTShirt(string memory tshirtType, uint256 quantity)`

Allows users to redeem T-Shirts using tokens. Users specify the T-Shirt type and quantity they wish to redeem. Requires a sufficient token balance and available T-Shirt inventory. Burns the corresponding tokens and updates the user's T-Shirt balance and inventory accordingly.

### `getUserTokenBalance()`

Returns the token balance of the caller.

### `addTShirtQuantity(string memory tshirtType, uint256 quantity)`

Allows the owner to add inventory for a specific T-Shirt type.

### `modifyTShirtQuantity(string memory tshirtType, uint256 newQuantity)`

Allows the owner to modify the inventory quantity of a specific T-Shirt type.

## License

This project is licensed under the MIT License. See the `LICENSE` file for details.

## Author

mdmuzammil000007@gmail.com
