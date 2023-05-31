## Inheritance Contract

This Solidity contract enables the management of inheritance by allowing the owner to designate heirs and distribute funds to them after the owner's death.

### Contract Structure

The contract consists of a single `Inheritance` contract defined in Solidity version 0.8.0 or higher.

### State Variables

- `owner`: An `address` variable representing the owner of the inheritance contract. This address is payable, allowing funds to be transferred to it.
- `deceased`: A boolean variable indicating whether the owner has passed away.
- `creationTime`: A `uint` variable storing the timestamp when the contract was created.
- `lastUpdateTime`: A `uint` variable storing the timestamp of the last contract update.
- `inheritance`: A mapping that associates addresses (heirs) with the amount of inheritance they are entitled to receive.

### Functions

The contract provides the following functions to manage inheritance:

1. `setInheritance(address heir, uint amount)`: Allows the owner to set the inheritance amount for a specific heir. This function can only be called by the owner and requires a non-zero amount of inheritance.
2. `withdraw()`: Enables heirs to withdraw their designated inheritance after the owner's death. Only heirs can invoke this function, and it transfers the designated amount to their address.
3. `declareDeath()`: Allows the owner to declare their own death, marking the `deceased` variable as true. This function can only be called by the owner.
4. `getInheritance(address heir)`: Retrieves the inheritance amount designated for a specific heir. It takes the address of the heir as input and returns the corresponding inheritance amount.
5. `getBalance()`: Returns the current balance of the inheritance contract.

### Modifiers

The contract includes the following modifiers:

1. `onlyOwner`: Restricts the execution of a function to the contract's owner. It throws an error message if called by an address other than the owner.
2. `onlyAfterDeath`: Restricts the execution of a function to after the owner's death. It throws an error message if the owner is not declared deceased.

### License

The contract is licensed under the MIT License. Please refer to the SPDX-License-Identifier at the top of the code for more details.
