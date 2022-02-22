소켓 옵션 설정하기
===
(2022/2/22)

setsockopt() 소켓 송수신 동작 제어
---
socket : socket number  
level : option category  
optname : number of socket for setting  
optval : address, setting saved  
optlen : size of optval buffer  

SOL_SOCKET level
---
|value|type|explanation|  
|:-----|:----|:---|
|SO_REUSEADDR|BOOL|reuse already used address| 
|SO_RCV_BUF|int|Specify the size of the receive buffer|






SO_REUSEADDR option
---
if error occurred like this
```
bind error : address already in use
```
use SO_REUSEADDR option to reuse previously binded addr



[ref1](https://snowdeer.github.io/c++/2017/08/17/setsockopt/)
[ref2](https://www.joinc.co.kr/w/Site/Network_Programing/AdvancedComm/SocketOption)
