# Solidity Functions Cheat Sheet

Functions are a fundamental part of Solidity smart contracts, defining the behavior and logic of the contract. Understanding how to declare, call, and use functions is essential for writing effective contracts.

## 1. Function Declaration

Declare functions using the `function` keyword, specifying the visibility, return type (if any), and parameters.

```solidity
function functionName(parameterType parameterName) visibility returns (returnType) {
    // Function body
}
```

### Example:

```solidity
function deposit(uint amount) public {
    balances[msg.sender] += amount;
}
```

## 2. Function Visibility

Functions can have different visibility levels:

- `public`: Accessible from any context.
- `external`: Only accessible externally (cannot be called internally).
- `internal`: Accessible from the current contract and any derived contracts.
- `private`: Accessible only within the current contract.

### Example:

```solidity
function withdraw(uint amount) external {
    require(balances[msg.sender] >= amount, "Insufficient balance");
    balances[msg.sender] -= amount;
    msg.sender.transfer(amount);
}
```

## 3. Return Values

Functions can return values using the `returns` keyword.

### Example:

```solidity
function getBalance() public view returns (uint) {
    return balances[msg.sender];
}
```

## 4. Function Modifiers

Modifiers are used to modify the behavior of functions. They are defined with the `modifier` keyword.

### Example:

```solidity
modifier onlyOwner() {
    require(msg.sender == owner, "Not the owner");
    _;
}

function changeOwner(address newOwner) public onlyOwner {
    owner = newOwner;
}
```

## 5. Function Overloading

Solidity supports function overloading, allowing multiple functions with the same name but different parameter lists.

### Example:

```solidity
function calculate(uint a, uint b) public pure returns (uint) {
    return a + b;
}

function calculate(uint a, uint b, uint c) public pure returns (uint) {
    return a + b + c;
}
```

## 6. Payable Functions

Functions can receive Ether by using the `payable` modifier.

### Example:

```solidity
function receiveEther() public payable {
    balances[msg.sender] += msg.value;
}
```

Understanding these aspects of functions is crucial for creating modular and secure smart contracts in Solidity. Refer to the official Solidity documentation for more details and advanced features.
