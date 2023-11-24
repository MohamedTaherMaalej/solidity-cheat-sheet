# Solidity Mappings Cheat Sheet

Mappings in Solidity are used to create key-value pairs, where each key is associated with a value. Mappings are a versatile data structure that can be used in various scenarios within smart contracts.

## 1. Declaration

Declare a mapping with the `mapping` keyword.

```solidity
mapping(address => uint) public balances;
```

## 2. Adding Key-Value Pairs

Assign values to keys in the mapping.

```solidity
function deposit() public payable {
    balances[msg.sender] += msg.value;
}
```

## 3. Accessing Values

Retrieve values associated with a specific key.

```solidity
uint public userBalance = balances[msg.sender];
```

## 4. Updating Values

Modify the values associated with a key.

```solidity
function withdraw(uint amount) public {
    require(balances[msg.sender] >= amount, "Insufficient balance");
    balances[msg.sender] -= amount;
    msg.sender.transfer(amount);
}
```

## 5. Mapping of Structs

Mappings can be used to create key-value pairs with structs.

```solidity
struct Person {
    string name;
    uint age;
}

mapping(address => Person) public people;

function addPerson(string memory name, uint age) public {
    people[msg.sender] = Person(name, age);
}
```

## 6. Iterating Over Mappings

Solidity does not natively support direct iteration over mappings, but you can maintain a separate array of keys for iteration.

```solidity
address[] public userAddresses;

function addUser(address userAddress) public {
    userAddresses.push(userAddress);
    // Add the user to the mapping as well
}

function getUserCount() public view returns (uint) {
    return userAddresses.length;
}
```

## 7. Mapping of Mappings

Mappings can also be used to create more complex data structures.

```solidity
mapping(address => mapping(uint => bool)) public userPermissions;

function grantPermission(uint permissionId) public {
    userPermissions[msg.sender][permissionId] = true;
}
```

## 8. Default Values

Mappings are initialized with default values (zero for numeric types, `false` for booleans, and an empty byte array for bytes).

```solidity
mapping(address => uint) public defaultValues;

function getValueOrDefault(address user) public view returns (uint) {
    return defaultValues[user]; // Returns 0 if the user is not in the mapping
}
```

Understanding how to use and manipulate mappings efficiently is crucial for organizing and managing data structures in your Solidity contracts. Experiment with different scenarios to deepen your understanding.

Refer to the official Solidity documentation for more details on mappings and their usage.

