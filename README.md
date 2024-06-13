# CREATING A TOKEN

This Solidity program shows how to create a token using the Solidity programming language. This program's goal is to generate a token and store the values inside of it.

## Description

Written in Solidity, a programming language for creating Ethereum blockchain smart contracts, this application is a contract. The contract contains several functions for minting, burning, and mapping variables.


## Getting Started

### Executing program

We can use Remix to run this code, an online Solidity IDE.

```javascript
// SPDX-License-Identifier: MIT
pragma solidity >=0.8.2 <0.9.0;

/*
       REQUIREMENTS
    1. Your contract will have public variables that store the details about your coin (Token Name, Token Abbrv., Total Supply)
    2. Your contract will have a mapping of addresses to balances (address => uint)
    3. You will have a mint function that takes two parameters: an address and a value. 
       The function then increases the total supply by that number and increases the balance 
       of the “sender” address by that amount
    4. Your contract will have a burn function, which works the opposite of the mint function, as it will destroy tokens. 
       It will take an address and value just like the mint functions. It will then deduct the value from the total supply 
       and from the balance of the “sender”.
    5. Lastly, your burn function should have conditionals to make sure the balance of "sender" is greater than or equal 
       to the amount that is supposed to be burned.
*/

contract MyToken {

    string public name = "University";
    string public symbol = "Branch";
    uint256 public TotalSupply = 20;

    mapping(address => uint256) public balanceOf;

  
    function mint(address _to, uint256 _value) public {
        TotalSupply += _value;
        balanceOf[_to] += _value;
    }

    function burn(address _from, uint256 _value) public {
        if(balanceOf[_from] >= _value) {
        TotalSupply -= _value;
        balanceOf[_from] -= _value;
    }
}
}
```
Once the code has compiled, select the "Deploy & Run Transactions" tab from the sidebar on the left to start deploying the contract. Click "Deploy" after selecting the "newToken" contract from the dropdown menu.

Once the contract has been successfully deployed, you can communicate with it by using any of its accessible functions.

