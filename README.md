# ETH-PROOF-Beginner

This Solidity program is a simple "My Token" contract program in solidity that demonstrates the basic features of a Token or currency like its "Name", "Total Supply" and "Abbreviation" as well as some functions such as "Mint" that can add on the token to a specific user or address and "Burn" is just the opposite of Mint. The purpose of this program is to give a basic understanding about contracts, tokens etc and the logic building for more such contracts.

## Description

This program is a simple contract written in Solidity, a programming language used for developing smart contracts on the Ethereum blockchain. The contract has two functions "Mint" and "Burn" that allow to add or remove tokens from a specific address or user. This program serves as a simple and straightforward introduction to Contracts, and can be used as a stepping stone for more complex projects in the future.

## Getting Started

### Executing program

To run this program, you can use Remix, an online Solidity IDE. To get started, go to the Remix website at https://remix.ethereum.org/.

Once you are on the Remix website, create a new file by clicking on the "+" icon in the left-hand sidebar. Save the file with a .sol extension (e.g., MyToken.sol). Copy and paste the following code into the file:
```solidity
pragma solidity 0.8.18;
import "hardhat/console.sol";
contract MyToken {

    // public variables here
    uint public totalSupply;
    string public tokenName = "NoobCoin";
    string public tokenAbbrv = "NBC";

    // mapping variable here
    mapping(address => uint) public addresses;

    // mint function
    function mint(address _addr, uint _val) public {
        totalSupply += _val;
        addresses[_addr] += _val;
    }

    // burn function
    function burn(address _addr, uint _val) public {
        if(addresses[_addr] >= _val){
            totalSupply -= _val;
            addresses[_addr] -= _val;
        }else{
            console.log("Not Enough Balance!!");
        }
       
    }
}
```


To compile the code, click on the "Solidity Compiler" tab in the left-hand sidebar. Make sure the "Compiler" option is set to "0.8.9" (or another compatible version), and then click on the "Compile MyToken.sol" button.

Once the code is compiled, you can deploy the contract by clicking on the "Deploy & Run Transactions" tab in the left-hand sidebar. Select the "MyToken" contract from the dropdown menu, and then click on the "Deploy" button.

Once the contract is deployed, you can interact with it by calling the Mint or Burn function. Click on the "MyToken" contract in the left-hand sidebar, and then click on the "Mint" function. Then, enter the address and amount of tokens. Finally, click on the "transact" button to execute the function and retrieve the "Balance" amount. The same can be performed with Burn but it will deduct the amount enterd from total balance of that address and if the amount > Balance then, it will show a error message on console. 

## Authors

Contributors names and contact info
- [@Harshdeep Singh](https://github.com/Sudo-Harsh-learner)
