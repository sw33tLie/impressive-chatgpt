# Input

Write a solidity code vulnerable to reentrancy attacks. Then fix it to make it secure.

# Answer

Here is a simple example of a Solidity contract that is vulnerable to reentrancy attacks:

```
pragma solidity ^0.5.0;

contract ReentrancyAttack {
    uint public balance;

    function deposit() public {
        balance += 1;
    }

    function withdraw(uint amount) public {
        require(amount <= balance);
        balance -= amount;
    }
}

```

This contract allows users to deposit and withdraw funds, but it does not properly check for reentrancy attacks. An attacker could call the `withdraw` function, and then call the `deposit` function repeatedly before the `withdraw` function finishes executing. This would allow the attacker to withdraw more funds than they have deposited.

To fix this issue, the contract can use a mutex to prevent reentrancy attacks. A mutex is a mechanism that allows only one execution thread to access a critical section of code at a time. In this case, the critical section is the `withdraw` function, which updates the contract's balance.

Here is an updated version of the contract that uses a mutex to prevent reentrancy attacks:

```
pragma solidity ^0.5.0;

contract ReentrancyAttack {
    uint public balance;
    bool public mutex;

    function deposit() public {
        balance += 1;
    }

    function withdraw(uint amount) public {
        require(amount <= balance);
        require(!mutex); // Acquire the mutex
        mutex = true;

        balance -= amount;

        mutex = false; // Release the mutex
    }
}

```

In this updated version of the contract, the `withdraw` function acquires the mutex before updating the balance, and releases the mutex after updating the balance. This prevents other execution threads from accessing the critical section of code, and ensures that the `withdraw` function is not interrupted by other calls to the `deposit` function.