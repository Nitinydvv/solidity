// SPDX-License-Identifier: MIT
pragma solidity 0.8.18;

contract CreateToken {
    // Public state variables to store the token name, symbol, and total supply
    string public tokenName;
    string public tokenSymbol;
    uint256 public tokenTotalSupply;

    // Mapping to keep track of each address's balance
    mapping(address => uint256) public addressBalances;

    // Constructor to initialize the token with a name, symbol, and initial supply
    constructor(string memory _name, string memory _symbol, uint256 _initialSupply) {
        tokenName = _name;
        tokenSymbol = _symbol;
        tokenTotalSupply = _initialSupply;
        addressBalances[msg.sender] = _initialSupply; // Assign the entire initial supply to the deployer
    }

    // Function to mint new tokens, increasing the total supply and the balance of the recipient address
    function mint(address _recipient, uint256 _amount) public {
        tokenTotalSupply += _amount;
        addressBalances[_recipient] += _amount;
    }

    // Function to burn tokens, decreasing the total supply and the balance of the specified address
    function burn(address _account, uint256 _amount) public {
        require(addressBalances[_account] >= _amount, "Not enough balance to burn");
        tokenTotalSupply -= _amount;
        addressBalances[_account] -= _amount;
    }
}
