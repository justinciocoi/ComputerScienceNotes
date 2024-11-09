**Justin Ciocoi**

**Nov. 3, 2023**

# Wireshark Lab 3

#### Q1

<img title="" src="file:///Users/justin/Pictures/marktextImages/5bc8d3e4feead4338439266618d64a84436f17fb.png" alt="" data-align="center" width="357">

****

    The value in the upper layer protocol field is the IP version



#### Q2

<img title="" src="file:///Users/justin/Pictures/marktextImages/153fa1a04c4c7f28eaa07a1ae6997324e7d7db1f.png" alt="" width="357" data-align="center">

****

    The IP header is comprised of 20 bytes. Since the total length of the IP datagram is 56 bytes, the IP datagram's payload is 36 bytes



#### Q3

<img title="" src="file:///Users/justin/Pictures/marktextImages/eaf6f98e99bc73aa1d462b446dce82f33d648c3c.png" alt="" data-align="center" width="353">

****

    This IP datagram has not been fragmented, as we can see from the more fragments flag being offset, and the fragmentation offset being 0



#### Q4

<img title="" src="file:///Users/justin/Pictures/marktextImages/35afdf550d2156c796bfcbb1a63f0fd9a24054fb.png" alt="" width="351" data-align="center">

****

    The identification will change each time since it is unique between each packet



#### Q5

<img title="" src="file:///Users/justin/Pictures/marktextImages/5bc8d3e4feead4338439266618d64a84436f17fb.png" alt="" data-align="center" width="362">

****

    The IP Version stays constant between packets



<div style="page-break-after: always">

</div>

#### Q6

    Yes, the message has been fragmented into two datagrams, which are pictured below



#### Q7

<img title="" src="file:///Users/justin/Pictures/marktextImages/8bcc4bce4016410166ac98f1b103825d0dc71414.png" alt="" data-align="center" width="464">

****

<img title="" src="file:///Users/justin/Pictures/marktextImages/e6ed3772c4550fa14237b35c014d12f62e4ca44c.png" alt="" data-align="center" width="466">

****

    We can tell the datagram has been fragmented due to the presence of the more fragments flag in the top datagram, as well as the fragmentation offset in the bottom datagram. We know that is the more fragments flag is set to 1 and the fragmentation offset is 0, it is the first fragment, and if the more fragments flag is set to 0, and the fragmentation offset is non-zero, it is the last fragment. Thus we can tell the top datagram is the first fragment and the bottom datagram is the last fragment.



<div style="page-break-after: always">

</div>

#### Q8

    Yes, this message has been fragmented into 3 IP datagrams, which are pictured below



#### Q9

<img title="" src="file:///Users/justin/Pictures/marktextImages/05a67bac33c27c2013f9b95a952613d69f373198.png" alt="" data-align="center" width="412">

****

<img title="" src="file:///Users/justin/Pictures/marktextImages/9e2f997b83f8981dc95124088f78d26df2a0091e.png" alt="" data-align="center" width="410">

****

<img title="" src="file:///Users/justin/Pictures/marktextImages/9623f1276b89e2ebdf5deb4f073ecc8f2b7da512.png" alt="" data-align="center" width="418">

****

    The more fragments flags and the fragmentation offsets let us know that the message has been fragmented. As in question 7, if the more fragments flag is set to 1 and the fragmentation offset is 0, it is the first fragment, and if the more fragments flag is set to 0, and the fragmentation offset is non-zero, it is the last fragment. Thus we can tell the top datagram is the first fragment and the bottom datagram is the last fragment. In this scenario, we can also see that the middle packet satisfies neither set of properties, since it has the more fragments flag set to 1 *and* a non-zero fragmentation offset, meaning it is some datagram in the middle, between the first and last


