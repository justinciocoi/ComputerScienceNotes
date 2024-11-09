**Justin Ciocoi**

**Oct. 19, 2023**

# CSCI 379 Computer Networking

****

## WireShark Lab 2

****

#### Questions 1 and 2

<img title="" src="file:///C:/Users/Justin/Pictures/marktextImages/1bdc1fc5d4cd8698e838148ceb415877165ad8dc.jpg" alt="" width="467" data-align="center">

    Questions 1 and 2 can both be answered using the information from the initial transmission. The relevant IP addresses are highlighted in $\textcolor{red}{red}$ and the relevant ports are highlighted in $\textcolor{blue}{blue}$. In the screenshot above, we can see that my client computer uses IP address 10.106.65.193 and port 50529. gaia.cs.umass.edu has IP address 128.119.245.12 and uses port 80.



#### Question 3

<img title="" src="file:///C:/Users/Justin/Pictures/marktextImages/158faeac7bf81c7ca3cb6f9a00fd32302f647158.jpg" alt="" data-align="center" width="405">

    The sequence number of the TCP SYN segment is 10679640. This segment is designated as a SYN segment due to the presence of the SYN flag, which is the 11th digit in what is seemingly a 12-bit integer storing a variety of segment flags. This number can be represented in a 3-byte hexadecimal number and we can see here that the SYN segment flag has a hex value of 0x002.



#### Question 4

<img title="" src="file:///C:/Users/Justin/Pictures/marktextImages/d9cf2f497fd0ce26bc02765d32fde1b8cb3b82c8.jpg" alt="" data-align="center" width="402">

    The Sequence number of the SYNACK segment, which we find by looking for the presence of both flags, is 847453135. The acknowledgement field is set to 10679641.



#### Question 5

<img title="" src="file:///C:/Users/Justin/Pictures/marktextImages/743634613d069eca8929cdee21311b0c2b3f76e5.jpg" alt="" data-align="center" width="413">

    I don't think there were any retransmitted segments in this connection. I observed the SEQ and ACK numbers grow with cumulative ACKs coming in every once in a while without any necessary retransmissions. However, when filtering the trace file for retransmissions, there was one retransmission present in the trace file that was unrelated to this lab.
