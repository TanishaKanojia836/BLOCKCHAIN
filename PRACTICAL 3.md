// SPDX-License-Identifier: MIT
pragma solidity ^0.8.0;

contract OwnerRestricted {
    address public owner;
    string private secretMessage;
    
    constructor() {
        owner = msg.sender;
    }
    
    modifier onlyOwner() {
        require(msg.sender == owner, "Only owner can call this");
        _;
    }
    
    function setSecretMessage(string memory _message) public onlyOwner {
        secretMessage = _message;
    }
    
    function getSecretMessage() public view onlyOwner returns (string memory) {
        return secretMessage;
    }
}
![image](https://github.com/user-attachments/assets/9ac39c93-f4a6-43d9-a511-1e135c656a4e)
![image](https://github.com/user-attachments/assets/f85abb11-87fe-4629-887c-b9d1e0305a8b)
![image](https://github.com/user-attachments/assets/38677f03-81aa-4abb-b124-df081f59af48)
![image](https://github.com/user-attachments/assets/a3f957f6-310e-44f8-b84d-9aed93172696)


