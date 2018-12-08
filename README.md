# HTTP-Client-and-Server
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
