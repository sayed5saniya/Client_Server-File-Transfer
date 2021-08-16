# Client_Server-File-Transfer

 Write two programs (in C or in Java), a client and a server, to implement a simple remote shell connection. The server process and the client process will run on two different machines and the communication between the two processes is achieved using Sockets. The server task can be summarized as follows :

• The server must start running before any client, and wait for connections.

• When the server gets a client, it forks and let the child process take care of the client in a separate function, called
   serviceClient, while the parent process goes back to wait for the next client.

• Then, the server’s child process
       1. uses " dup2()" to make the screen descriptor designate the client socket
       2. gets in an infinite loop then :
            – reads a shell command from the client’s socket,  
            – if the client sends "quit", then the server’s child, closes socket and quits.
            – otherwise, it excutes command, using the " system()" library function,

The client process connects to the server, then

• gets into an infinite loops
     1. reads a command from keyboard,
     2. write the command to the server,
     3. if command is "quit", closes socket and quits
     4. otherwise, reads command output from socket and displays them on the screen 
