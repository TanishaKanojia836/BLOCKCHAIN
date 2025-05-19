// SPDX-License-Identifier: MIT
pragma solidity ^0.8.0;

contract VotingSystem {
    struct Candidate {
        string name;
        uint voteCount;
    }
    
    Candidate[] public candidates;
    mapping(address => bool) public hasVoted;
    address public owner;
    
    constructor(string[] memory _candidateNames) {
        owner = msg.sender;
        for(uint i = 0; i < _candidateNames.length; i++) {
            candidates.push(Candidate({
                name: _candidateNames[i],
                voteCount: 0
            }));
        }
    }
    
    function vote(uint _candidateIndex) public {
        require(!hasVoted[msg.sender], "You have already voted");
        require(_candidateIndex < candidates.length, "Invalid candidate");
        
        candidates[_candidateIndex].voteCount++;
        hasVoted[msg.sender] = true;
    }
    
    function getWinner() public view returns (string memory) {
        uint winningVoteCount = 0;
        uint winningIndex = 0;
        
        for(uint i = 0; i < candidates.length; i++) {
            if(candidates[i].voteCount > winningVoteCount) {
                winningVoteCount = candidates[i].voteCount;
                winningIndex = i;
            }
        }
        
        return candidates[winningIndex].name;
    }
}
![image](https://github.com/user-attachments/assets/b6887d4a-747c-4c85-b5fe-e7e321c92e01)
![image](https://github.com/user-attachments/assets/6e37423c-a547-4673-a413-134db5be8010)
![image](https://github.com/user-attachments/assets/bb114d00-4ec7-40e7-a1c6-bfdf62df6324)
