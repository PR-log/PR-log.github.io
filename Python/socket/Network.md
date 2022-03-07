# 파이썬 네트워크
-----

간단한 파이썬 소켓 프로그래밍  
sockt 
```
import socket
from _thread import *

def threaded(client_socket,addr):
    print('Connected by;', addr[0], ':', addr[1]) #접속 확인 출력

    while True:
        try:

            data = client_socket.recv(1024)

            if not data:
                print('Disconnected by ' + addr[0], ':', addr[1])
                break
            print('Recived from ' + addr[0],':', addr[1] , data.decode())

            client_socket.send(data)

        except ConnectionResetError as e:
            print('Disconnected by' + addr[0], ':', addr[1])
            break
    
    client_socket.close()
```
```
HOST = '127.0.0.1' #호스트 주소 
PORT = 9999 #임의의 포트
```
```
server_socket = socket.socket(socket.AF_INET, socket.SOCK_STREAM)
```
[AF_INET](https://github.com/PR-log/PR-log.github.io/blob/cd4dfc2c1b40555498dd9dd58f2359067a5e9525/Python/socket/AF_INET%20%EC%84%A4%EB%AA%85.md)   
[SOCK_STREAM](https://github.com/PR-log/PR-log.github.io/blob/2a9ab46b498836f56027adf36b37c4bd999bdb73/Python/socket/%EC%86%8C%EC%BC%93%20Type.md)
```
server_socket.setsockopt(socket.SOL_SOCKET, socket.SO_REUSEADDR, 1)
```
서버 사용중이라 연결할수 없다는 오류 해결 위해 필요 [setspckopt](https://github.com/PR-log/PR-log.github.io/blob/2a9ab46b498836f56027adf36b37c4bd999bdb73/Python/socket/setsockopt.md)  
```
server_socket.bind((HOST, PORT))
server_socket.listen() #서버가 클라이언트의 접속 허용

print('server start') #서버 시작 알림

while True:
    print('wait')
    client_socket, addr = server_socket. accept() #accept에서 대기하다 클라이언트가 접속하면 새로운 소켓 리턴
    start_new_thread(threaded, (client_socket, addr)) #새로운 쓰레드에서 만들어서 실행

server_socket.close()
```
