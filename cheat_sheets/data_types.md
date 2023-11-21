# Solidity Data Types Cheat Sheet

Solidity supports various data types that are essential for smart contract development. Understanding these data types is crucial for effective Solidity programming.

## 1. Integers

Solidity provides both signed and unsigned integers. The size can be specified in multiples of 8 bits.

- `uint`: Unsigned integer (default is `uint256`).
- `int`: Signed integer (default is `int256`).

```solidity
uint256 public unsignedInteger;
int256 public signedInteger;
```

## 2. Addresses

Addresses are used to store Ethereum addresses. They can represent both externally-owned accounts and smart contracts.

- `address`: Holds a 20-byte Ethereum address.

```solidity
address public owner;
address[] public investors;
```

## 3. Booleans

Boolean values represent true or false conditions.

- `bool`: Boolean data type.

```solidity
bool public isActive;
```

## 4. Strings

Strings are sequences of characters.

- `string`: Dynamic string.

```solidity
string public greeting = "Hello, Solidity!";
```

## 5. Arrays

Solidity supports both fixed-size and dynamic arrays.

- `fixedArray`: Fixed-size array.
- `dynamicArray`: Dynamic array.

```solidity
uint[3] public fixedArray;
uint[] public dynamicArray;
```

## 6. Structs

Structs allow you to define custom data structures.

```solidity
struct Person {
    string name;
    uint age;
}

Person public alice;
```

## 7. Mappings

Mappings are key-value pairs.

```solidity
mapping(address => uint) public balances;
```

## 8. Enums

Enums are user-defined types consisting of a set of named values.

```solidity
enum State { Created, Locked, Inactive }
State public state;
```

## 9. Bytes

Bytes data type is used for raw byte data.

- `bytes`: Dynamic byte array.
- `bytesN`: Fixed-size byte array (1 <= N <= 32).

```solidity
bytes public dynamicBytes;
bytes32 public fixedBytes;
```

## 10. Address Literals

Solidity supports address literals.

```solidity
address public contractAddress = address(0x123abc...);
```

Understanding and using these data types appropriately is essential for writing secure and efficient smart contracts in Solidity. Refer to the official Solidity documentation for more details on data types and their usage.


