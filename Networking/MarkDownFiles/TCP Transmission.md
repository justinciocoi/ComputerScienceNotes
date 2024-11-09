**Justin Ciocoi**

**Oct. 10, 2023**

# CSCI 379 Class Notes

## TCP Transmission

### **Flow Control**

- *Cumulative Acknowledgements* are used to pipeline packets and lessen the overhead of TCP connections by allowing for fewer transmissions to be sent back and forth

- *Flow Control* is a way for a receiver to tell a sender that its buffer is close to filling up
  
  - This happens to prevent the buffer filling up and causing packet loss

- This is achieved using the *receive window* field in the TCP segment header

- <img src="file:///Users/justin/Pictures/marktextImages/6f1064ecec9c188f802558b5a0174aa5211a0fce.png" title="" alt="Screenshot 2023-10-10 at 11.40.17 AM.png" width="513">

- <img src="file:///Users/justin/Pictures/marktextImages/8f2262676fe079b672e9d5119def7998e98abf25.png" title="" alt="Screenshot 2023-10-10 at 11.41.16 AM.png" width="306">

- The receiver informs sender of free space using the `rwnd` value in the TCP header
  
  - `RcvBuffer` size is set via socket options (typical default is 4096 bytes)
  
  - Many OSes auto-adjust `RcvBuffer`

- Sender limits size of sent data to the value oof the receivers `rwnd` variable

- Prevents buffer overflow

### Connection Management

- **The TCP Three-Way Handshake**
  - ![](/Users/justin/Pictures/marktextImages/db2e6b6ab98c669212f5ece99ecae2d2b158ba68.png)
- **Closing a connection**
  - A TCP connection is closed using the `FIN` flag in the TCP header and setting it to 1
  - When receiver receives a FIN flag, it will acknowledge it, and then after some time it will send its own `FIN` flag
    - During this time, the receiver is still capable of transmitting data over the connection
  - ![](/Users/justin/Pictures/marktextImages/60c47a44e2b8e7543fc17da8005464a304fde20b.png)

### Congestion Control

- In a connection, lost packets and long delays are often the result of *congestion* in the network

- This is a very important issue in thee realm of networking, given that most networks are susceptible to congestion at times
