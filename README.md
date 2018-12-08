# Project 1: HTTP-Client-and-Server
HTTP Client: Client initiates communication with server
  Steps:
    1. Creating Sockets using Socket class
    2. Requesting server for TCP connection
    3. If connected, client requests for GET/PUT using String command
GET: To get a file from server using InputStream inputSt
PUT: To save a file in server using InputStream inputs and clientSocket.getOutputStream()
    4. Read and display Server’s response using

HTTP Server: Server responds to client’s request
  Steps:
    1. Creating Sockets
    2. Server waits for clients (terminated by ctrl + c)
    3. Server accepts Client (if same port) using method- accept()
    4. Once connected, it will receive request from client
    5. Server process the Client’s request

GET(httpMethod.equals("GET")): It fetches the file mentioned in the client’s request if it
is present and displays it to client with the help of BufferedReader br.
If file is present- it responds with ‘200 OK’ message and contents of the file.
If the file is not present- it responds with ‘404 Not Found’ message

PUT(httpMethod.equals("PUT")): It saves the file (given by the client)

To run the program:
1. Open two command prompt window (for client and server)
2. Navigate to the directory where the server and client programs are kept
3. Compile the programs – javac filename.java--------(1)
4. On server cmd, type - java filename portnumber and press enter ---------(2)
5. Now the server will wait for the clients
6. On client side, type – java Filename Localhost PortNumber Command Filename(with ext)
Where portnumber should be the same as in (2) command
Command can be GET/PUT
7. The server’s response can be seen in client


# Project 2: Implementation and Simulation of Go-Back-N and Selective Repeat Protocols
In this program we have two files: one, inputsfile -which have arguments or parameters to be passed to Mysender and second, fileread.txt -which is the data to be sent to receiver by sender.
Two Protocols are implemented : 1. Go back N and 2. Selective Repeat
1. Go back N:
Window size = 2m-1
Receive window size = 1
The required packet seq number with ACK
2. Selective Repeat:
Window size = 2m-1
Receive window size = 2m-1
The received packet seq number with ACK
The two protocols are in same program. They can be executed by changing the inputsfile contents. They also have checksum to detect the data if it is corrupted. A timer is included to detect timeout. If ACK is received after timeout, then it is again sent. Duplicate packets are deleted. In GBN, if packet 1,2,3,4 are sent and packet 3 is lost (all other packets sent successfully), then receiver will send ACK3. In response to this, the sender will send packets 3,4,5,6 (if 5,6 are to be sent else only 3,4). In SR, its receive window size is same as sending window size and receiver ACKs for the received packets. In both cases, if there is timeout, ACK loss or data packet loss, the sender will resend the packets.
Steps to execute:
1. Open two command windows – for Mysender.java and Myreceiver.java
2. Create a file of any filename in same directory as .java files (inputsfile)
3. It should be
For eg:
SR
4
20
1000
500
Shanmathi Rajasekar
800966697
(Values in different line)
4. Create another file – having file name “fileread.txt”. Write anything in fileread.txt . This is the data that is sent to the Receiver.
5. Compile both
‘javac Mysender.java’
‘javac Myreceiver.java’
6. Execute Myreceiver first and then Mysender
‘Java Myreceiver portNum’
‘Java Mysender text_file_name(with ext) portNum seg’
(The two port names should be same to communicate)


# Project 3: Implementing Distance Vector Routing Protocol
Distance Vector Routing Protocol: Routers using distance-vector protocol have no knowledge about the entire path from source to destination. Distance-vector protocols are based on calculating the minimum direction and distance to any link in a network, which is the destination. It determines the next hop or next router which is nearest to the first. It measures the costs between two consecutive nodes. The least cost is the minimum distance between two nodes. Each node maintains a vector of minimum distance to every node. The values in this can be changed dynamically. The input files are sensed every 15 seconds. If values are changed, the router tables get updated.
Steps to execute the code:
1. Download the CCN zip file and unzip it.
2. Edit inputs (to change costs) if required (the default is given costs and nodes)
3. Open command prompt and change your path (“CCN” should be the last folder)
4. To compile – javac Dist_vector_RP.java
5. To run - proj4.bat
