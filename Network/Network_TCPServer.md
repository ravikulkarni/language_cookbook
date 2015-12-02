# Implementing TCP server

## Java
Use ServerSocket to listen on some port for the incoming connections. Use InputStream and OutputStream to read and write data to the socket. Example given below.

```java
try {
   int port = 2000;
   ServerSocket srv = new ServerSocket(port);

   // Wait for connection from client.
   Socket socket = srv.accept();
 //Use InputStream from socket.getInputStream and use it for reading
  //Similarly use OutputStream from socket.getOutputStream and use it for writing
  socket.close();       
} catch (IOException e) {
    //Handle this exception
}
```

One example how to write and read from socket is given below. Here data is string but this will show the use of input and output stream from the sockets.

```java
BufferedWriter wr = new BufferedWriter(new OutputStreamWriter(socket.getOutputStream()));
wr.write("some text");
wr.flush();

BufferedReader rd = new BufferedReader(new InputStreamReader(socket.getInputStream()));
String str;
while ((str = rd.readLine()) != null) {
     //Do something with this str
}
```

## Perl
IO::Socket::INET is used to create a socket on local port that accepts connection and creates a handle $client that can be used to read and write.

```perl
use IO::Socket;

my $server_port = 2002;

$server = IO::Socket::INET->new(LocalPort => $server_port,
                               Type      => SOCK_STREAM,
                               Reuse     => 1,
                               Listen    => 10 )   # or SOMAXCONN
   or die "Couldn't be a tcp server on port $server_port : $@\n";
print "Waiting for socket to be accepted\n";
$client = $server->accept();
print "Socket Accepted";
# $client is the new connection. Use that as a handle to read and write information from.

close($server);
```

## C
In the code below following things are done. 
In the example below following things are done
- Socket is created using socket function
- Initialize socket address structure and receiving buffer to 0 instead of having some garbage values.
- The socket address structure values for port, address(IN_ADDR), and socket family which is AF_INET for tcp sockets.
- Connect to the remote host and get handle to be used for reading or writiing
- The bind assigns the details specified in the structure ‘serverAddress’ to the socket created in the step above. 
- The ‘listen()’ with second argument as ’5′ specifies maximum number of client connections that server will queue for this listening socket.
- In the call to accept(), the server waits for incoming client request and then returns the socket descriptor representing the client socket.
- The socket is then used for reading and writing.

```c
int socketHandle = 0, connectedSocketHandle = 0;
struct sockaddr_in serverAddress; 

char sendBuffer[256];
time_t ticks; 

socketHandle = socket(AF_INET, SOCK_STREAM, 0);
memset(&serverAddress, '0', sizeof(serverAddress));
memset(sendBuffer, '0', sizeof(sendBuffer)); 

serverAddress.sin_family = AF_INET;
serverAddress.sin_addr.s_addr = htonl(INADDR_ANY);
serverAddress.sin_port = htons(5000); 

bind(socketHandle, (struct sockaddr*)&serverAddress, sizeof(serverAddress)); 

listen(socketHandle, 5); 

while(1)
{
    connectedSocketHandle = accept(socketHandle, (struct sockaddr*)NULL, NULL); 

    snprintf(sendBuffer, sizeof(sendBuffer), "Some text\r\n");
    write(connectedSocketHandle, sendBuffer, strlen(sendBuffer)); 

    close(connectedSocketHandle);
    sleep(1);
}
```

## Bash
This is not supported in bash to have something sent from one machine to another. There are client server implementation using named pipes but they are supposed to be on the same machine.
