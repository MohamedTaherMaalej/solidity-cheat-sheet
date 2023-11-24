# Solidity Events Cheat Sheet

Events in Solidity are a powerful mechanism for communicating and logging important occurrences within a smart contract. They enable external applications to listen and react to specific changes in the contract state.

## 1. Declaration

Declare an event using the `event` keyword.

```solidity
event Transfer(address indexed from, address indexed to, uint value);
```

## 2. Event Emission

Emit an event within a function to log a specific occurrence.

```solidity
function transfer(address to, uint value) public {
    // Transfer logic
    emit Transfer(msg.sender, to, value);
}
```

## 3. Indexing

You can index parameters in an event, which allows for more efficient filtering and searching.

```solidity
event Purchase(address indexed buyer, uint indexed productId, uint quantity);
```

## 4. Event Parameters

Events can have multiple parameters, allowing you to log various pieces of information.

```solidity
event Payment(address payer, uint amount, string description);
```

## 5. Log Data

Log additional data when emitting an event.

```solidity
function purchase(uint productId, uint quantity) public {
    // Purchase logic
    emit Purchase(msg.sender, productId, quantity);
}
```

## 6. Event Subscription

External applications, including web frontends, can subscribe to events and react accordingly.

```javascript
// JavaScript example using web3.js
contractInstance.events.Transfer({ filter: { to: myAddress } })
    .on('data', function(event){
        console.log(event); // Log the event details
    })
    .on('error', console.error);
```

## 7. Event Modifiers

Use event modifiers to provide additional context or information.

```solidity
modifier onlyOwner() {
    require(msg.sender == owner, "Not the owner");
    _;
    emit OwnershipTransferred(owner, newOwner);
}

function transferOwnership(address newOwner) public onlyOwner {
    owner = newOwner;
}
```

## 8. Event Order

Events are emitted and processed after a transaction is mined, ensuring a deterministic order.

```solidity
function performMultipleActions() public {
    // Perform multiple actions
    emit Action1();
    // More actions
    emit Action2();
}
```

Understanding how to use events effectively is crucial for providing transparency and allowing external systems to react to changes in your Solidity smart contracts. Experiment with different scenarios to deepen your understanding.

Refer to the official Solidity documentation for more details on events and their usage.
