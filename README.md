# Command Line Interface Chat Application

## About
This application is a simple implementation of a chat application. The only feature missing here is authentication. This chat application has a command line interface with the details of the message format present below. \
There are two files in the src folder - [```server.py```](./src/server.py) and [```client.py```](./src/client.py). The first file contains the code for the server end whereas the second file contains the code for the client end.

## How to run the code?
1. Run the following command to start the server-
    ```
    python3 server.py 
    ``` 
2. Run the following command to start a client system-
    ```
    python3 client.py [USERNAME] [SERVER_IP]
    ```
    Here, USERNAME is the client's username. This username can only contain alphanumeric ```[a-zA-Z1-9]``` characters.

    SERVER_IP is the server's IP address for connection. For example- ```127.0.0.1``` (localhost)

### *Note*
- ```ALL``` can't be used as a client's username. It is a reserved keyword for broadcast messages. 
- Multiple clients can be started using the above mentioned command on same system.

## Message format
- For unicast messages, use
    ```
    @[RECVR_USERNAME]: Message
    ```
    Remember RECVR_USERNAME should be a legal username of a client connected to the user. Otherwise, error would be raised by the server side (ERROR 102). \
     If the format of the message is wrong, appropiate help will be printed.

- For broadcast messages, use
    ```
    @ALL: Message
    ```
    Broadcast messages are visible to all the clients connected to the server. 

## Implementation details
- Python is used for the implementation. Python's ```socket``` library is used for making TCP sockets. 
- To handle multiple clients, threads are used to run parallel processes. Python's ```threading``` library is used for making threads.  
- At client's end, two threads are used to separate the sending and listening sockets' processes.
- Registration protocol is implemented to register client's sockets at server side. 


Enjoy :)

## Author
- Name - [Gaurav Jain](https://github.com/GauravJain28) 
- Entry Number - 2019CS10349

...