GalaxyCoin Token Smart Contract
This repository contains the Solidity code for the GalaxyCoin (GLX) token. GalaxyCoin is an ERC-20 compatible token with basic mint and burn functionalities.

Overview
This smart contract defines a simple ERC-20 token with the following features:

Token Name: GalaxyCoin
Token Symbol: GLX
Minting: Ability to increase the total supply and assign tokens to a specified address.
Burning: Ability to decrease the total supply and deduct tokens from a specified address.
Contract Details
Public Variables
tokenName: The name of the token (GalaxyCoin).
tokenAbbrv: The abbreviation or symbol of the token (GLX).
totalSupply: The total supply of tokens in circulation.
Mappings
balances: A mapping that stores the balance of each address.
Functions
mint
The mint function allows increasing the total supply of the token and assigning the minted tokens to a specific address.

solidity
Copy code
function mint(address _address, uint _value) public {
    totalSupply += _value;
    balances[_address] += _value;
}
Parameters:

_address: The address to which the minted tokens will be assigned.
_value: The number of tokens to mint.
Effects:

Increases the totalSupply by _value.
Increases the balance of _address by _value.
burn
The burn function allows decreasing the total supply of the token and deducting the burned tokens from a specific address.

solidity
Copy code
function burn(address _address, uint _value) public {
    if (balances[_address] >= _value) {
        totalSupply -= _value;
        balances[_address] -= _value;
    }
}
Parameters:

_address: The address from which the tokens will be burned.
_value: The number of tokens to burn.
Effects:

Decreases the totalSupply by _value.
Decreases the balance of _address by _value.
Note: The burn function checks if the address has enough tokens to burn before performing the operation.

Usage
To use this contract, you can deploy it to an Ethereum network using your preferred method (Remix, Truffle, Hardhat, etc.). Once deployed, you can interact with the mint and burn functions to manage the token supply.

Example
To mint 100 GLX tokens to an address 0x123..., call the mint function:

solidity
Copy code
mint(0x123..., 100);
To burn 50 GLX tokens from the same address, call the burn function:

solidity
Copy code
burn(0x123..., 50);
License
This project is licensed under the MIT License. See the LICENSE file for details.





