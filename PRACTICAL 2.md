// SPDX-License-Identifier: MIT
pragma solidity ^0.8.0;

contract StudentRecords {
    struct Student {
        string name;
        uint rollNumber;
    }
    
    Student[] public students;
    mapping(uint => bool) public rollNumberExists;
    
    function addStudent(string memory _name, uint _rollNumber) public {
        require(!rollNumberExists[_rollNumber], "Roll number already exists");
        students.push(Student(_name, _rollNumber));
        rollNumberExists[_rollNumber] = true;
    }
    
    function getStudent(uint _index) public view returns (string memory, uint) {
        require(_index < students.length, "Invalid index");
        return (students[_index].name, students[_index].rollNumber);
    }
    
    function getStudentCount() public view returns (uint) {
        return students.length;
    }
}
![image](https://github.com/user-attachments/assets/2377425f-4cca-4153-85b5-8d6f408b18e4)
![image](https://github.com/user-attachments/assets/eaad03ff-d2db-4d49-906a-e34934996bb6)
![image](https://github.com/user-attachments/assets/2af15675-0f42-4ba6-89be-bc15bd4ebbd1)
