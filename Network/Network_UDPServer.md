# Implementing UDP server 

## Java
Create DatagramPacket with the data and destination address and port. Create DatagramSocket and send the packet using send call.

```java
byte outbuf[] = new byte[10];
for(byte i=0;i < outbuf.length ; i++) {
   outbuf[i] = i;
}
int port = 8081;
try {
   InetAddress dst = InetAddress.getByName("localhost");
   DatagramPacket request = new DatagramPacket(outbuf, outbuf.length, dst, port);
   DatagramSocket socket = new DatagramSocket();
   socket.send(request);
} catch (SocketException e) {
   e.printStackTrace();
}  catch (IOException e) {
   e.printStackTrace();
}
```

## Perl

With IO::Socket, create a udp socket for a particular destination and port. Call send to send some data over the socket.

```perl
use IO::Socket;
my $server_port = 2002;

$socket = new IO::Socket::INET (PeerAddr   => "$server_name:$server_port",
				Proto        => "udp"
   ) or die "ERROR in Socket Creation : $!\n";
$socket->send("Test message");
```

## C

This is also same as one for tcp sockets but with following differences
- Socket is initialized with type as SOCK_DGRAM and protocol IPPROTO_UDP
- sendto function is used to send data over datagram
- receivefrom function is used to send data over datagram

```c
int socketHandle = 0, connectedSocketHandle = 0;
struct sockaddr_in serverAddress, clientAddress; 

int clientAddrLength = sizeof(clientAddress);
char receiveBuffer[256];

socketHandle = socket(AF_INET, SOCK_DGRAM, IPPROTO_UDP);
memset(&serverAddress, '0', sizeof(serverAddress));
memset(sendBuffer, '0', sizeof(sendBuffer)); 

serverAddress.sin_family = AF_INET;
serverAddress.sin_addr.s_addr = htonl(INADDR_ANY);
serverAddress.sin_port = htons(5000); 

bind(socketHandle, (struct sockaddr*)&serverAddress, sizeof(serverAddress)); 

listen(socketHandle, 5); 

while(1)
{
        
   if (recvfrom(socketHandle, receiveBuffer, 256, 0, (struct sockaddr*)&clientAddress, &clientAddrLength)==-1)
	    err("recvfrom()");
   printf("Received packet from %s:%d\nData: %s\n\n",
	     inet_ntoa(clientAddress.sin_addr), ntohs(clientAddress.sin_port), receiveBuffer);
}
```

## Bash

No support in Bash
