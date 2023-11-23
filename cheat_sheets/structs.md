# Solidity Structs Cheat Sheet

Structs in Solidity allow you to define custom data structures with multiple fields. They are useful for organizing and representing complex data within your smart contracts.

## 1. Declaration and Initialization

Declare and initialize structs using the `struct` keyword.

```solidity
struct Person {
    string name;
    uint age;
}

Person public alice;
```

## 2. Instantiation

Create instances of structs and initialize their values.

```solidity
alice = Person("Alice", 30);
```

## 3. Accessing Struct Members

Access individual members of a struct using dot notation.

```solidity
string public aliceName = alice.name;
uint public aliceAge = alice.age;
```

## 4. Updating Struct Members

Modify the values of struct members.

```solidity
function updateAge(uint newAge) public {
    alice.age = newAge;
}
```

## 5. Array of Structs

Arrays can hold multiple instances of a struct.

```solidity
Person[] public people;

function addPerson(string memory name, uint age) public {
    people.push(Person(name, age));
}
```

## 6. Mapping of Structs

Use mappings to create key-value pairs with structs.

```solidity
mapping(address => Person) public personMap;

function addPerson(address key, string memory name, uint age) public {
    personMap[key] = Person(name, age);
}
```

## 7. Nested Structs

Structs can be nested within other structs.

```solidity
struct Address {
    string street;
    string city;
}

struct PersonWithAddress {
    string name;
    uint age;
    Address homeAddress;
}

PersonWithAddress public bob;
```

## 8. Modifiers with Structs

Use structs in combination with modifiers to enforce specific conditions.

```solidity
modifier validAge(uint age) {
    require(age >= 18, "Age must be 18 or older");
    _;
}

function updatePersonAge(uint newAge) public validAge(newAge) {
    alice.age = newAge;
}
```

## 9. Memory Considerations

Be mindful of gas costs when working with large arrays or structs.

Understanding how to use and manipulate structs efficiently is crucial for organizing and managing complex data structures in your Solidity contracts. Experiment with different scenarios to deepen your understanding.

Refer to the official Solidity documentation for more details on structs and their usage.
