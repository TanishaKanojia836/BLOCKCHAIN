// SPDX-License-Identifier: MIT
pragma solidity ^0.8.0;

contract TopDonors {
    struct Donor {
        address donorAddress;
        uint amount;
    }
    
    Donor[3] public topDonors;
    
    function donate() public payable {
        require(msg.value > 0, "Donation amount must be greater than 0");
        
        // Check if donor already exists in top 3
        for(uint i = 0; i < 3; i++) {
            if(topDonors[i].donorAddress == msg.sender) {
                topDonors[i].amount += msg.value;
                sortDonors();
                return;
            }
        }
        
        // If new donor has more than the smallest in top 3
        if(msg.value > topDonors[2].amount) {
            topDonors[2] = Donor(msg.sender, msg.value);
            sortDonors();
        }
    }
    
    function sortDonors() private {
        for(uint i = 1; i < 3; i++) {
            for(uint j = 0; j < i; j++) {
                if(topDonors[i].amount > topDonors[j].amount) {
                    Donor memory temp = topDonors[i];
                    topDonors[i] = topDonors[j];
                    topDonors[j] = temp;
                }
            }
        }
    }
}

![image](https://github.com/user-attachments/assets/b3b4267f-d746-4c7b-a84e-db12255b511d)
![image](https://github.com/user-attachments/assets/c06dc8d4-0831-4082-bf0d-06ed9848cded)
![image](https://github.com/user-attachments/assets/577aad28-3f1b-46f5-8eb5-81c677aaeadb)
![image](https://github.com/user-attachments/assets/11606310-6448-4e24-b208-abff53d3db43)
