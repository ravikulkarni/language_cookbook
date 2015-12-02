# Implementing TCP client

## Java
Below are the 2 ways to create a socket. Both of them create Socket for a particular address and port. Once the socket is created then the InputStream and OutputStream is used to read and write from that socket.

```java
// Create a socket without a timeout
try {
   InetAddress addr = InetAddress.getByName("java.sun.com");
   int port = 80;

   // This constructor will block until the connection succeeds
   Socket socket = new Socket(addr, port);
   //Use InputStream from socket.getInputStream and use it for reading
  //Similarly use OutputStream from socket.getOutputStream and use it for writing
} catch (UnknownHostException e) {
} catch (IOException e) {
}

// Create a socket with a timeout
try {
   InetAddress addr = InetAddress.getByName("java.sun.com");
   int port = 8080;
   SocketAddress sockaddr = new InetSocketAddress(addr, port);

   // Create an unbound socket
   Socket socket = new Socket();

   int timeoutMs = 3000;   // 3 seconds
   socket.connect(sockaddr, timeoutMs);
  //Use InputStream from socket.getInputStream and use it for reading
  //Similarly use OutputStream from socket.getOutputStream and use it for writing
  socket.close();       
} catch (UnknownHostException e) {
       //Handle this exception
} catch (SocketTimeoutException e) {
      //Handle this exception
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

Use IO:Socket:INET to create a socket for a particular address and port. Use $socket as handle for reading or writing.

```perl
use IO::Socket;

my $remote_port = 2002;
my $remote_host = "hostname_to_be_connected_to";
$socket = IO::Socket::INET->new(PeerAddr => $remote_host,
                               PeerPort => $remote_port,
                               Proto    => "tcp",
                               Type     => SOCK_STREAM)
   or die "Couldn't connect to $remote_host:$remote_port : $@\n";
# Do something with the $socket like printing something on the socket. Use $socket has the handle to print it.
# You could also use the $socket for reading.

# and terminate the connection when we're done
close($socket);
```

## C
In the example below following things are done
- Socket is created using socket function
- Initialize socket address structure and receiving buffer to 0 instead of having some garbage values.
- The socket address structure values for port, remote address, and socket family which is AF_INET for tcp sockets.
- Connect to the remote host and get handle to be used for reading or writiing

```c
int socketHandle = 0, n = 0;
char receiveBuffer[256];
struct sockaddr_in serverAddress; 

memset(receiveBuffer, '0',sizeof(receiveBuffer));
if((socketHandle = socket(AF_INET, SOCK_STREAM, 0)) < 0)
{
    /* Handle error */
} 

memset(&serverAddress, '0', sizeof(serverAddress)); 

serverAddress.sin_family = AF_INET;
serverAddress.sin_port = htons(5000); 

if(inet_pton(AF_INET, remote_address_ip_addr, &serverAddress.sin_addr)<=0)
{
 	 /* Handle error */
} 

if( connect(socketHandle, (struct sockaddr *)&serverAddress, sizeof(serverAddress)) < 0)
{
    /* Handle error */
} 

while ( (n = read(socketHandle, receiveBuffer, sizeof(receiveBuffer)-1)) > 0)
{
    receiveBuffer[n] = 0;
    if(fputs(receiveBuffer, stdout) == EOF)
    {
        /* Handle error */
    }
} 
```

## Bash

This is not supported in bash to have something sent from one machine to another. There are client server implementation using named pipes but they are supposed to be on the same machine.
