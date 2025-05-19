Installation of IPFS on local machine. Further, upload the files (such as photos, audio, and video) on IPFS and share it with other through content identifier (i.e., hash). Perform assessment using ubuntu WSL.
Commands (IPFS)
1.	Install the IPFS through WSL: wget https://dist.ipfs.tech/kubo/v0.32.1/kubo_v0.32.1_linux-amd64.tar.gz 
Or 
wget https://github.com/ipfs/kubo/releases/download/v0.32.1/kubo_v0.32.1_linux-amd64.tar.gz
2.	tar -xvzf kubo_v0.32.1_linux-amd64.tar.gz
3.	Kubo is a reference implementation of IPFS in Go: cd kubo 
4.	ls
5.	sudo bash install.sh
6.	ipfs –version
7.	ipfs init
8.	ipfs daemon
9.	On Browser: http://127.0.0.1:5001/webui
10.	To run ipfs daemon in background: ipfs daemon > ipfs.log 2>&1 &
11.	This is daemon ID: [1] 772
12.	Add file: echo "Hello, IPFS!" > hello.txt
13.	ipfs add hello.txt
14.	ipfs cat <CID>
15.	Add a directory: 
mkdir myfolder
echo "File 1 content" > myfolder/file1.txt
echo "File 2 content" > myfolder/file2.txt
16.	ipfs add -r myfolder
17.	ps aux | grep ipfs
18.	kill <PID>
19.	in Browser you can directly run this to see the IPFS: https://ipfs.io/ipfs/QmWd9cavD8UGZQcqYBVhZqs2Jure5W9cgxR7S6TC4StfZe
![image](https://github.com/user-attachments/assets/1453aa83-41d1-4bb7-9d29-3fdc4ed796f3)
![image](https://github.com/user-attachments/assets/e83c6c8a-0c90-471e-a11d-58fdd594a081)
![image](https://github.com/user-attachments/assets/974d3b9f-e79c-49a6-ae1b-0d75e46cfeaa)

