# MY TOKEN
This project is a Solidity smart contract implementation for creating a custom token on the Ethereum blockchain. It provides functionalities to mint new tokens, transfer tokens between addresses, and burn tokens.

## DESCRIPTION

The Create a Token project allows users to deploy a custom ERC20 token on the Ethereum blockchain. It's suitable for various use cases such as creating utility tokens, security tokens, or governance tokens for decentralized applications (dApps). The smart contract provides methods for minting new tokens, transferring tokens between addresses, and burning tokens.

## GETTING STARTED
To run this program, you can use Remix, an online Solidity IDE. To get started, go to the Remix website at https://remix.ethereum.org/.
### EXECUTING PROGRAM
1. Open Remix in your web browser.
2. Create a new file by clicking on the "+" icon in the left-hand sidebar.
3. Save the file with a .sol extension (e.g., MyToken.sol).
4. Copy and paste the Solidity code below above into the file.
5. Compile the contract by clicking on the "Solidity Compiler" tab in the sidebar, then clicking on "Compile" at the top of the page.
6. Deploy the contract by clicking on the "Deploy & Run Transactions" tab in the sidebar, then selecting the contract and clicking on "Deploy".
7. Interact with the contract by calling the `mint` and `burn` functions with appropriate parameters.

```Solidity
// SPDX-License-Identifier: MIT
pragma solidity 0.8.26;

contract MyToken {

    // Public variables
    string public name = "MyToken";          // Token Name
    string public symbol = "MTK";            // Token Abbreviation
    uint256 public totalSupply = 0;          // Total Supply initially set to 0

    // Mapping to store balances
    mapping(address => uint256) public balances;

    // Mint function to create new tokens
    function mint(address _to, uint256 _amount) public {
        totalSupply += _amount;               // Increase total supply
        balances[_to] += _amount;             // Increase balance of the recipient address
    }

    // Burn function to destroy tokens
    function burn(address _from, uint256 _amount) public {
        require(balances[_from] >= _amount, "Insufficient balance to burn"); // Ensure sufficient balance
        totalSupply -= _amount;               // Decrease total supply
        balances[_from] -= _amount;           // Decrease balance of the sender address
    }
}
```

## LICENSE
This project is licensed under the MIT License - see the LICENSE.md file for details
