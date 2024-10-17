# 2b IMPLEMENTATION OF SLIDING WINDOW PROTOCOL

## AIM:
To write a python program to perform sliding window protoco
## ALGORITHM:

1. Start the program.
2. Get the frame size from the user
3. To create the frame based on the user request.
4. To send frames to server from the client side.
5. If your frames reach the server it will send ACK signal to client
6. Stop the Program

## PROGRAM
# Name:GOKHULRAJ V
# Ref no:212223230064
## CLIENT:
```py
import socket
s=socket.socket()
s.bind(('localhost',8000))
s.listen(5)
c,addr=s.accept()
size=int(input("Enter number of frames to send : "))
l=list(range(size))
s=int(input("Enter Window Size : "))
st=0
i=0
while True:
 while(i<len(l)):
     st+=s
     c.send(str(l[i:st]).encode())
     ack=c.recv(1024).decode()
     if ack:
       print(ack)
       i+=s
```
## SERVER:
```py
import socket
s=socket.socket()
s.connect(('localhost',8000))
while True: 
 print(s.recv(1024).decode())
 s.send("acknowledgement recived from the server".encode())
```
## OUPUT
## Cilent:
![image](https://github.com/priyankaarrr/2b_SLIDING_WINDOW_PROTOCOL/assets/147475464/63ecb3d7-ff3a-470c-a4a1-6cf9bc14039e)


## Server:
![image](https://github.com/priyankaarrr/2b_SLIDING_WINDOW_PROTOCOL/assets/147475464/90efeded-82d7-4519-9bbb-3b8f4f7f7e16)


## RESULT
Thus, python program to perform Sliding Window protocol was successfully executed

