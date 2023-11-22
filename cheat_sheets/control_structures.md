# Solidity Control Structures Cheat Sheet

Control structures in Solidity allow you to dictate the flow of execution within your smart contracts. Understanding these structures is crucial for effective programming.

## 1. If Statements

Conditional statements allow you to execute code based on a specified condition.

```solidity
if (condition) {
    // Code to execute if condition is true
} else {
    // Code to execute if condition is false
}
```

Example:

```solidity
if (balance > 100) {
    withdrawAmount = 50;
} else {
    withdrawAmount = 0;
}
```

## 2. Loops

Loops are used to execute a set of statements repeatedly.

### For Loop

```solidity
for (uint i = 0; i < 5; i++) {
    // Code to execute in each iteration
}
```

Example:

```solidity
for (uint i = 0; i < investors.length; i++) {
    distributeDividends(investors[i]);
}
```

### While Loop

```solidity
while (condition) {
    // Code to execute while the condition is true
}
```

Example:

```solidity
uint total = 0;
while (total < 1000) {
    total += getRandomNumber();
}
```

## 3. Switch Statements

Switch statements allow you to perform different actions based on different conditions.

```solidity
uint choice = 2;

switch (choice) {
    case 1:
        // Code to execute if choice is 1
        break;
    case 2:
        // Code to execute if choice is 2
        break;
    default:
        // Code to execute if choice doesn't match any case
}
```

Example:

```solidity
uint day = 3;

switch (day) {
    case 1:
        today = "Monday";
        break;
    case 2:
        today = "Tuesday";
        break;
    // ... (continue for other days)
    default:
        today = "Unknown day";
}
```

Understanding and using these control structures effectively will enhance the logic and flexibility of your Solidity smart contracts. Experiment with different scenarios to deepen your understanding.

Refer to the official Solidity documentation for more details on control structures and their usage.
