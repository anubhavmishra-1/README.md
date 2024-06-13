# CREATING A TOKEN

This Solidity program is a program that demonstrates the creation of a token in the Solidity programming language. The purpose of this program is to create a token and store the values in the token.

## Description

This program is a contract written in Solidity, a programming language used for developing smart contracts on the Ethereum blockchain. The contract has multiple functions for mapping variables, minting and burning values.

## Getting Started

### Executing program


  // SPDX-License-Identifier: MIT
  pragma solidity 0.8.18;
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

After the code has been compiled, you may proceed to deploy the contract by navigating to the "Deploy & Run Transactions" tab located in the left-hand sidebar. Select the "newToken" contract from the dropdown menu, and then click the "Deploy" button.

Upon successful deployment of the contract, you will be able to interact with it by invoking the various functions available.
