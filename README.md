# Deadly Token (DT) ERC20 Token Deployment

This Solidity Smart Contract, `MyToken`, is a blockchain-based application designed to provide a secure and transparent way for users to manage their ERC20 tokens, mint new tokens, burn tokens, and transfer tokens. This README provides an overview of the contract's functionalities and instructions for setting up and using the contract

## Description

The `MyToken` Solidity Smart Contract serves as the backbone of a decentralized application (dApp) that allows users to interact with Ethereum blockchain features. It includes the following key functionalities:

* **Mint Tokens:** The contract owner can mint new tokens.
* **Burn Tokens:** Users can burn their tokens, reducing the total supply.
* **Transfer Tokens:** Users can transfer tokens to other Ethereum addresses.
* The contract utilizes Solidity's features such as events, error handling with require and revert statements, and access control through owner verification. These features ensure the contract's reliability, security, and user-friendliness.

## Getting 

### Prerequisites

To use this smart contract, you need to have the following:

* A web browser with MetaMask installed
* Access to Remix IDE (https://remix.ethereum.org/)

### Running the Contract on Remix IDE

1. **Open Remix IDE:**
   Go to [Remix IDE](https://remix.ethereum.org/).

2. **Create a New File:**
   Create a new file in Remix IDE and name it `MyToken.sol`.

3. **Copy the Contract Code:**
   Copy and paste the following Solidity code into the `MyToken.sol` file:
   ```
   // SPDX-License-Identifier: MIT
   pragma solidity ^0.8.20;

   import "@openzeppelin/contracts/token/ERC20/ERC20.sol";
   import "@openzeppelin/contracts/token/ERC20/extensions/ERC20Burnable.sol";
   import "@openzeppelin/contracts/access/Ownable.sol";

   contract MyToken is ERC20("Deadly Token", "DT"), ERC20Burnable, Ownable(msg.sender) {

       function mint(address to, uint256 amount) public onlyOwner {
           _mint(to, amount * 10**2);
       }

       function burn(uint256 amount) public override {
           _burn(msg.sender, amount);
       }

       function transfer(address to, uint256 amount) public {
           _transfer(msg.sender, to, amount);
       }

   }
   ```

## Compile the Contract

1. Go to the "Solidity Compiler" tab on the left panel.
2. Select the compiler version `0.8.20`.
3. Click on the "Compile MyToken.sol" button.

## Deploy the Contract

1. Go to the "Deploy & Run Transactions" tab on the left panel.
2. Select "Injected Web3" as the environment to connect to MetaMask.
3. Make sure you are connected to the desired Ethereum network (e.g., Ropsten, Rinkeby, or a local blockchain).
4. Click on the "Deploy" button next to `MyToken`.

## Interact with the Contract

1. After deploying, you will see the deployed contract under "Deployed Contracts".
2. You can interact with the contract using the available functions (e.g., `mint`, `burn`, `transfer`).

## Help

If you encounter any issues or have questions about using the smart contract, please contact [preetjawla6@gmail.com].

## Authors

- Preet Jawla
  - [preetjawla6@gmail.com]

## License

This project is licensed under the MIT License - see the `LICENSE.md` file for details.


