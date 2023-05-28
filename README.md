

# 19CS406-EX-1 STUDY OF SOCKET PROGRAMMING WITH CLIENT-SERVER MODEL

 ## DATE :09-03-2023

 ## AIM :
    To write a python program to perform stop and wait protocol.

## ALGORITHM :
    1. Start the program.
    2. Get the frame size from the user
    3. To create the frame based on the user request.
    4. To send frames to server from the client side.
    5. If your frames reach the server it will send ACK signal to client
    otherwise it will sendNACK signal to client.
    6. Stop the program.
    
    

## PROGRAM :
```
CLIENT:

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

 
 SERVER:
 
 import socket
 s=socket.socket()
 s.connect(('localhost',8000))
 while True:
    print(s.recv(1024).decode())
    s.send("Acknowledgement Recived".encode())
```





OUTPUT:

### CLIENT
![image](https://github.com/Swetha733N/19CS406-EX-1/assets/122199934/7020548d-cd90-4727-9762-7fc175cb5667)


### SERVER
![image](https://github.com/Swetha733N/19CS406-EX-1/assets/122199934/9223a1cd-aa1f-4de8-bf07-bd8b5f588ff4)





### RESULT:
Thus, python program to perform stop and wait protocal was sucessfully executed.

