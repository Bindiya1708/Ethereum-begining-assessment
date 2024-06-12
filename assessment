// SPDX-License-Identifier: MIT
pragma solidity 0.8.26;

contract MyToken {

    // Public variables
    string public name = "MyToken";          
    string public symbol = "MTK";           
    uint256 public totalSupply = 0;          
    // Mapping to store balances
    mapping(address => uint256) public balances;

    // Mint function to create new tokens
    function mint(address _to, uint256 _amount) public {
        totalSupply += _amount;               
        balances[_to] += _amount;             
    }

    // Burn function to destroy tokens
    function burn(address _from, uint256 _amount) public {
        require(balances[_from] >= _amount, "Insufficient balance to burn"); 
        totalSupply -= _amount;              
        balances[_from] -= _amount;          
    }
}

