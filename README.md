# ETH Proof Beginner EVM Course Project
This Solidity program contract provides basic functionalities to mint new tokens and burn existing ones, 
following the specified requirements.
It includes the following features:
1. Public Variables to store token details such as name, abbreviation, and total supply.
2. A mapping to track balances of different addresses.
3. Functions to mint and burn tokens, updating the total supply and balances accordingly.

## Description
This repository contains a Solidity smart contract for creating custom tokens on the Ethereum blockchain. The program was
created and compiled on Remix, an online Solidity IDE. https://remix.ethereum.org/.


## Getting Started
### Executing program
To run this code, follow these steps:
1. Go to https://remix.ethereum.org/.
2. Import EthAss.sol file.
3. Run and Debug the code.

```

// SPDX-License-Identifier: MIT
pragma solidity 0.8.26;

contract EtherAss {
    // public variables
    string public tkName="Hello";
    string public tkAbbrv ="META";
    uint public totalSupply=0;

    // mapping variable
    mapping(address => uint) public balances;

    // mint function
    function mint(address _address, uint _value) public {
        totalSupply += _value;
        balances[_address] += _value;
    }

    // burn function
    function burn(address _address, uint _value) public {
        require(balances[_address] >= _value, "Insufficient balance");
        totalSupply -= _value;
        balances[_address] -= _value;
    }
}
```

## Authors
Siddhartha Chaurasia

## License
This project is licensed under the MIT License.