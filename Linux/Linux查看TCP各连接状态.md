# Linux查看TCP各连接状态

**TCP连接状态详解**  
LISTEN（listen）：侦听来自远方的TCP端口的连接请求

SYN-SENT（syn-send）：再发送连接请求后等待匹配的连接请求

SYN-RECEIVED（syn-received）：再收到和发送一个连接请求后等待对方对连接请求的确认

ESTABLISHED（established）：代表一个打开的连接

FIN-WAIT-1（fin-wait-1）：等待远程TCP连接中断请求，或先前的连接中断请求的确认

FIN-WAIT-2（fin-wait-2）：从远程TCP等待连接中断请求

CLOSE-WAIT（close-wait）：等待从本地用户发来的连接中断请求

CLOSING（closing）：等待远程TCP对连接中断的确认

LAST-ACK（last-ack）：等待原来的发向远程TCP的连接中断请求的确认

TIME-WAIT（time-wait）：等待足够的时间以确保远程TCP接收到连接中断请求的确认

CLOSED（closed）：没有任何连接状态