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
client:
```

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
server:
```

   import socket
s=socket.socket()
s.connect(('localhost',8000))
while True:
 print(s.recv(1024).decode())
 s.send("Acknowledgement Recived".encode())
```
## OUTPUT
client:

![Screenshot (392)](https://github.com/Anusharonselva/2a_Stop_and_Wait_Protocol/assets/119405600/d3925ab5-bbe5-4523-a71a-5f6aee6b2f3e)

server:
![Screenshot (392) 1](https://github.com/Anusharonselva/2a_Stop_and_Wait_Protocol/assets/119405600/2d6d0b45-63e0-469f-9490-f122948f3d10)


## RESULT
Thus, python program to perform stop and wait protocol was successfully executed.
