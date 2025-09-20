# 2a_Stop_and_Wait_Protocol
## AIM 
To write a python program to perform stop and wait protocol
## ALGORITHM
1. Start the program.
2. Get the frame size from the user
3. To create the frame based on the user request.
4. To send frames to server from the client side.
5. If your frames reach the server it will send ACK signal to client
6. Stop the Program
## PROGRAM

Server


```python
import socket 
s=socket.socket() 
s.connect(('localhost',8000)) 
while True: 
    print(s.recv(1024).decode()) 
    s.send("Acknowledgement Recived".encode())
```

Client


```python

import socket 
s=socket.socket()
s.bind(('localhost',8000))
s.listen(5) 
c,addr=s.accept() 
while True: 
    i=input("Enter a data: ") 
    c.send(i.encode()) 
    ack=c.recv(1024).decode() 
    if ack: 
        print(ack) 
        continue 
    else: 
        c.close() 
        break
```


## OUTPUT

<img width="610" height="352" alt="image" src="https://github.com/user-attachments/assets/a50522c6-110f-4a78-a18e-1bdfb09af116" />

<img width="591" height="242" alt="image" src="https://github.com/user-attachments/assets/04acfe6f-a909-4eff-a2da-1f22309005d5" />


## RESULT
Thus, python program to perform stop and wait protocol was successfully executed.
