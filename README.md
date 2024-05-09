# Ex-2b IMPLEMENTATION OF SLIDING WINDOW PROTOCOL
## Register Number: 212222230064
## Name: Kavinesh M
## AIM
To perform a study on sliding window protocol.
## ALGORITHM:
1. Start the program.
2. Get the frame size from the user
3. To create the frame based on the user request.
4. To send frames to server from the client side.
5. If your frames reach the server it will send ACK signal to client
6. Stop the Program
## Program:
### Client:
```
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
### Server:
```
import socket
s=socket.socket()
s.connect(('localhost',8000))
while True: 
 print(s.recv(1024).decode())
 s.send("acknowledgement recived from the server".encode())
```
## Output:
### Client:

![image](https://github.com/kavinesh8476/2b_SLIDING_WINDOW_PROTOCOL/assets/118466561/0c86a208-7fb0-47e3-b785-c8bec92b1f64)


### Server:

![image](https://github.com/kavinesh8476/2b_SLIDING_WINDOW_PROTOCOL/assets/118466561/382ac3bf-888e-4192-8eaf-2394f73ef27b)


## RESULT
Thus, python program to perform stop and wait protocol was successfully executed
