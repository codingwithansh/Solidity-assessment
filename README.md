Project Title: This Solidity program is to create a token program that demonstrates functionality of the Solidity programming language. The purpose of this program is to serve as a starting point for those who are new to Solidity and want to get a feel for how it works.

Description: The contract will have public variables that store the details about your coin (Token Name, Token Abbrv., Total Supply) The contract will have a mapping of addresses to balances (address => uint) it will have a mint function that takes two parameters: an address and a value. The function then increases the total supply by that number and increases the balance of the address by that amount. This contract will have a burn function, which works the opposite of the mint function, as it will destroy tokens. It will take an address and value just like the mint functions. It will then deduct the value from the total supply and from the balance of the address. Lastly, the burn function should have conditionals to make sure the balance of account is greater than or equal to the amount that is supposed to be burned.

Getting Started: To run this program, you can use Remix, an online Solidity IDE. To get started, go to the Remix website at https://remix.ethereum.org/.

Once you are on the Remix website, create a new file by clicking on the "+" icon in the left-hand sidebar. Save the file with a .sol extension. (e.g., MyTokensol).Copy and paste the following code into the file:

```
// SPDX-License-Identifier: MIT
pragma solidity 0.8.18;

contract MyToken {
    // Public variables to store details about the coin
    string public constant TokenName = "MyToken";
    string public constant TokenAbbrv = "MTK";
    uint256 public TotalSupply;

    // Mapping to store balances of each address
    mapping(address => uint256) public balances;

    // Mint function to create new tokens
    function mint(address receiver, uint256 amount) public {
        require(amount > 0, "Amount must be greater than 0");
        balances[receiver] += amount;
        TotalSupply += amount;
    }

    // Burn function to destroy tokens
    function burn(uint256 amount) public {
        require(amount > 0, "Amount must be greater than 0");
        require(balances[msg.sender] >= amount, "Insufficient balance");
        balances[msg.sender] -= amount;
        TotalSupply -= amount;
    }
}
```

Clicking the "solidity" icon in the left sidebar will open the "Solidity Compiler" pane. Verify that you have chosen the appropriate compiler version (0.8.18). From the menu, choose "Compile MyToken.sol". Put the Agreement into Practice:

Click the Ethereum icon in the left sidebar to see the "Deploy & Run Transactions" tab. Select the workspace of your choice (e.g., "JavaScript VM" for a local blockchain within your browser). Click the "Deploy" button next to the MyToken contract. Participate with the Deployed Contract:

After deployment, the contract's features will be available under the "Deployed Contracts" area. The contract can be interacted with through the provided buttons and input areas. Examples of Coining Coins Conversations:

Find the mint function on the deployed contract interface. You can either provide an address or use the one that is automatically provided. mint. Click the transact button to mint tokens and send them to the specified address. Burning Tokens:

Use the balances mapping to verify your balance. Locate and utilise the burn function by navigating to the deployed contract interface. Click the transact button once the requested burn amount has been entered. Checking Balances and Total Supply:

Use the balances mapping to find the balance at any address. Use the TotalSupply variable to determine the total number of tokens available.


