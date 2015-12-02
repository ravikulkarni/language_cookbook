# Implementing UDP client 

## Java
Use DatagramSocket to create a socket for a particular destination and port. Call method receive to receive the packet.

```java
try {
    byte[] inbuf = new byte[256];  // default size
   
    InetAddress dst = InetAddress.getByName("hostname");
   int port = 8081;
   DatagramSocket socket = new DatagramSocket(dst,port);

    // Wait for packet
    DatagramPacket packet = new DatagramPacket(inbuf, inbuf.length);
    socket.receive(packet);

    // Data is now in inbuf
  //Process the data
    int numBytesReceived = packet.getLength();

} catch (SocketException e) {
    //Handle the exception
} catch (IOException e) {
   //Handle the exception
}
```

## Perl

Just like for the TCP sockets, use the same IO::Socket::INET to create a UDP sockets on some local port. recv is the function to call to receive the data in the datagram.

```
use IO::Socket;
my $server_port = 2002;
$server = IO::Socket::INET->new(LocalPort => $server_port,  Proto     => "udp")
   or die "Couldn't be a udp server on port $server_port : $@\n";
my $datagram;
$server->recv($datagram, 256);
  # do something with $datagram.
 close $handle;
```

## C

This is mostly same as one for tcp sockets but with following differences
- Socket is initialized with type as SOCK_DGRAM and protocol IPPROTO_UDP
- sendto function is used to send data over datagram
- receivefrom function is used to send data over datagram

```c   
int socketHandle = 0, n = 0;
char sendBuffer[256];
struct sockaddr_in serverAddress; 

if(argc != 2)
{
  /* Handle error */
} 

if((socketHandle = socket(AF_INET, SOCK_DGRAM, IPPROTO_UDP)) < 0)
{
   /* Handle error */
} 

memset(&serverAddress, '0', sizeof(serverAddress)); 

serverAddress.sin_family = AF_INET;
serverAddress.sin_port = htons(5000); 

if(inet_pton(AF_INET, receiver_ip_address, &serverAddress.sin_addr)<=0)
{
   /* Handle error */
} 

snprintf(sendBuffer, sizeof(sendBuffer), "Some text\r\n");
if (sendto(socketHandle, sendBuffer, 256, 0, (struct sockaddr*)&serverAddress, sizeof(serverAddress))==-1) {
    /* Handle error */
}
 
close(socketHandle);
```

## Bash

No support in Bash

