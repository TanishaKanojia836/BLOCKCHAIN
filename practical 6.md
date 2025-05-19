// SPDX-License-Identifier: MIT
pragma solidity ^0.8.0;

contract SplitEther {
    address payable public addr1;
    address payable public addr2;
    address payable public addr3;

    constructor(address payable _a1, address payable _a2, address payable _a3) {
        addr1 = _a1;
        addr2 = _a2;
        addr3 = _a3;
    }

    receive() external payable {
        uint share = msg.value / 3;
        addr1.transfer(share);
        addr2.transfer(share);
        addr3.transfer(msg.value - 2 * share); // handle remainder
    }
}

![image](https://github.com/user-attachments/assets/9e7fac4e-24c6-4b80-902f-fffb3e4a5b93)
![image](https://github.com/user-attachments/assets/6e9596c2-8f36-4d2a-a655-07b9e24e594a)
![image](https://github.com/user-attachments/assets/0fba0278-a44b-47ad-8c40-a7cde767fa2e)
