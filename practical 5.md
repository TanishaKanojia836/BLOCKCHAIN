// SPDX-License-Identifier: MIT
pragma solidity ^0.8.0;

contract SimpleAuction {
    address public highestBidder;
    uint public highestBid;

    function bid() public payable {
        require(msg.value > highestBid, "Bid too low");

        if (highestBid != 0) {
            payable(highestBidder).transfer(highestBid);
        }

        highestBidder = msg.sender;
        highestBid = msg.value;
    }
}

![image](https://github.com/user-attachments/assets/0a11e2a3-ecf3-483a-9067-e64fd4a84cf1)
![image](https://github.com/user-attachments/assets/80407269-cd55-4076-beb2-9e2ead72bad3)
![image](https://github.com/user-attachments/assets/748f6a85-cd62-4848-a84c-a345900a086d)
