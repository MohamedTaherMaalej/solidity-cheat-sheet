# Solidity Ether and Wei Cheat Sheet

In Solidity, Ether and Wei are units used to represent and interact with the cryptocurrency (ETH) within smart contracts. Understanding the conversion between Ether and Wei and how to send and receive them is crucial for effective smart contract development.

## 1. Ether and Wei Units

- **Ether (ETH):** The main unit of cryptocurrency in Ethereum.
- **Wei:** The smallest denomination of Ether.

```solidity
uint public oneEther = 1 ether;
uint public oneWei = 1 wei;
```

## 2. Sending Ether

Functions can receive Ether by marking them as `payable`. Users can send Ether when calling these functions.

```solidity
function receiveEther() public payable {
    // Contract balance is increased by the sent Ether
}
```

## 3. Sending Wei

Ether values are often represented in Wei. Use the `msg.value` variable to access the amount of Wei sent with a transaction.

```solidity
function receiveWei() public payable {
    uint sentWei = msg.value;
    // Process the sent Wei
}
```

## 4. Ether and Wei Conversion

You can convert between Ether and Wei using the conversion units.

```solidity
uint public oneEtherInWei = 1 ether;
uint public weiToEtherConversion = 1 wei / 1 ether;
```

## 5. Sending Ether to an Address

Use the `transfer` and `send` functions to send Ether to a specific address.

```solidity
address payable public recipient;

function sendEther() public {
    recipient.transfer(1 ether);
}
```

## 6. Checking Balance

Use the `balance` property to check the balance of an address in Wei.

```solidity
address public user;

function checkBalance() public view returns (uint) {
    return user.balance;
}
```

## 7. Ether and Wei Literals

Use literals to specify values in Ether or Wei.

```solidity
uint public oneEtherLiteral = 1 ether;
uint public oneWeiLiteral = 1 wei;
```

## 8. Gas Costs and Ether

Executing functions and transactions in Ethereum consumes gas, which is paid in Ether.

```solidity
function performTask() public {
    // Task logic
    // Gas cost is deducted from the contract's Ether balance
}
```

Understanding how to handle Ether and Wei within your smart contracts is crucial for managing financial transactions and interacting with the Ethereum network. Experiment with different scenarios to deepen your understanding.

Refer to the official Solidity documentation for more details on Ether and Wei and their usage.

