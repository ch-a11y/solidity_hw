# Smart Contract

Our new startup company has created an Ethereum-compatible blockchain to help on our finances, increase transparency and to automate accounting and auditing. We used the Solidity smart contract to complete this project.

First we created an `AssociateProfitSplitter` contract. In this contract we accept Ether into the contract and divide the Ether evenly among the associate level employees. This allows the Human Resources department to pay employees quickly and efficiently.

In our company's management level we created a `TieredProfitSplitter` that distributes different percentages of incoming Ether to the corporate officers at different tiers. In this contract the CEO gets paid 60%, CTO 25%, and Bob, the VP gets 15%.

We used [Remix IDE](https://remix.ethereum.org), Ganache (https://www.trufflesuite.com/ganache) and MetaMask to create, compile and deploy the contracts.


### To create `AssociateProfitSplitter` contract, we did the following: 

- Created the `public` variables, set payable to each employee's address;

- Created a constructor function that accepts ether;

- Created `balance` function to set to `public view returns(uint)';

- Created `deposit` function set to `public payable` to ensure only the owner can call the function;

- We used `msg.value` to account for any leftover wei and send it back to Human Resources.


### To create `TieredProfitSplitter` contract, we did the following:

- Calculated rudimentary percentages for different tiers of employees (CEO, CTO, and Bob).

- Calculated the number of points by dividing `msg.value` by `100`.

- Multiplied the points with a number representing a percentage, `points * 60, 25 or 15` which would output a number that is corresponding to the tiers of the `msg.value`.

- Transferred the `amount` to each employee, setting the `amount` to equal the `points` multiplied by their given percentage.

- Send the remainder to the employee with the highest percentage by subtracting `total` from `msg.value`.

We successfully deployed the contracts. Please see the attached screenshots.