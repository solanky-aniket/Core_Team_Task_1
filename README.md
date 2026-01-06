Core_Team_Task_1
Overview
This Solidity smart contract acts as a private digital vault where anyone can deposit Ether, but only the contract owner can withdraw funds.

 Ownership Logic
- The owner is defined as the Ethereum address that deploys the contract.
- This is set inside the constructor using `msg.sender`.
- The `withdraw()` function includes a `require` check to ensure only the owner can call it.

 Security Filters
- The owner cannot withdraw more Ether than the contract currently holds.
- This is implemented using:
  ```solidity
  require(_amount <= address(this).balance, "Insufficient contract balance");

Functions
deposit() – Allows anyone to send ETH to the contract.

getBalance() – Returns the total ETH stored in the contract.

withdraw(uint amount) – Allows only the owner to withdraw a specific amount of ETH.

Solidity Version
Solidity >=0.8.20
