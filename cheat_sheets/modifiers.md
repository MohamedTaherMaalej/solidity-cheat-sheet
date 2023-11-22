# Solidity Modifiers Cheat Sheet

Modifiers in Solidity are used to modify the behavior of functions. They enable you to enforce conditions before or after the execution of a function. Understanding how to use and create modifiers is essential for writing secure and efficient smart contracts.

## 1. Custom Modifiers

Define custom modifiers using the `modifier` keyword.

```solidity
modifier onlyOwner() {
    require(msg.sender == owner, "Not the owner");
    _; // This underscore represents the actual function body
}
```

### Example:

```solidity
function changeOwner(address newOwner) public onlyOwner {
    owner = newOwner;
}
```

## 2. Preconditions and Postconditions

Modifiers are often used to set preconditions (requirements that must be met) and postconditions (actions to be performed after execution).

### Example:

```solidity
modifier minimumValue(uint minValue) {
    require(msg.value >= minValue, "Value below minimum");
    _;
}

function deposit() public payable minimumValue(1 ether) {
    // Perform deposit logic
}
```

## 3. Reentrancy Guard

Modifiers can be used to prevent reentrancy attacks by using a reentrancy guard.

### Example:

```solidity
bool private reentrancyGuard;

modifier nonReentrant() {
    require(!reentrancyGuard, "Reentrant call");
    reentrancyGuard = true;
    _;
    reentrancyGuard = false;
}

function withdraw(uint amount) public nonReentrant {
    // Withdrawal logic
}
```

## 4. Access Control

Modifiers can be used for access control, restricting the execution of functions to certain roles.

### Example:

```solidity
address public owner;

modifier onlyOwner() {
    require(msg.sender == owner, "Not the owner");
    _;
}

function changeOwner(address newOwner) public onlyOwner {
    owner = newOwner;
}
```

## 5. Gas Limit

Modifiers can be used to check and limit the gas consumption of functions.

### Example:

```solidity
modifier limitGas() {
    require(gasleft() >= 200000, "Insufficient gas");
    _;
}

function performTask() public limitGas {
    // Task logic
}
```

Understanding and using modifiers effectively can significantly enhance the security and efficiency of your Solidity smart contracts. Experiment with different scenarios to deepen your understanding.

Refer to the official Solidity documentation for more details on modifiers and their usage.

