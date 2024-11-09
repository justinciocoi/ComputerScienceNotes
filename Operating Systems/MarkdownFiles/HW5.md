**Justin Ciocoi**

**Dec. 17, 2023**

# CSCI 375 Homework 5

## Chapter 9 Exercises

### 9.1

    One difference between the two is that logical addresses exist in an abstract address space whereas physical addresses are associated with actual physical memory in the computer system. Another difference is how they are generated, with logical addresses being generated by the CPU and the MMU translating those logical addresses into physical addresses.

### 9.2

    Paging is implemented through using a page number and an offset number that are each comprised of a certain number of bits. Each bit position is a power of two, so the size of pages therefore is always a power of two

### 9.3

    The major advantage of this scheme is that it allows for code and data to be shared among multiple users, but the drawback is that the code and data must be kept separate

### 9.4

a) The logical address is 16 bits

$$
64*1024=65536\newline
\log_2(65536)=16
$$

b) The physical address is 15 bits

$$
32*1024=32768\newline
\log_2(32768)=15
$$

### 9.5

    By allowing two entries in a page table to point to the same frame in memory, users can share code and data, which allows large amounts of memory space to be saved in the case of large programs. However, any modifications made would then be reflected in the system for all users

### 9.6

*First Fit*

- 115 KB is put in 300 KB partition (185 new partition)

- 500 KB is put in 600 KB partition (100 new partition)

- 358 KB is put in 750 KB partition (392 new partition)

- 200 KB is put in 350 KB (150 new partition)

- 375 KB is put in 392 KB partition (17 new partition)

*Best Fit*

- 115 KB is put in 125 KB partition (10 new partition)

- 500 KB is put in 600 KB partition (100 new partition)

- 358 KB is put in 750 KB partition (392 new partition)

- 200 KB is put in 200 KB partition

- 375 KB is put in 392 KB partition (17 new partition)

*Worst fit*

- 115 KB is put in the 750 KB partition (635 new partition)

- 500 KB is put in the 635 KB partition (135 new partition)

- 358 KB is put in the 600 KB partition (242 new partition)

- 200 KB is put in the 350 KB partition (150 new partition)

- 375 KB has to wait

### 9.7

a)

$$
\frac{3085}{1024}=3\frac{13}{1024}\\
\text{page = 3 and offset = 13}
$$

b)

$$
\frac{42095}{1024}=41\frac{111}{1024}\\
\text{page = 41 and offset = 111}
$$

c)

$$
\frac{215201}{1024}=210\frac{161}{1024}\\
\text{page = 210 and offset = 161}
$$

d)

$$
\frac{650000}{1024}=634\frac{784}{1024}\\
\text{page = 634 and offset = 784}
$$

e)

$$
\frac{2000001}{1024}=1953\frac{129}{1024}\\
\text{page = 1953 and offset = 129}
$$

### 9.8

    A conventional page table will have $2^{10}=1024$ entries, whereas an inverted page table will have $2^5=32$ entries. There is a 16-bit physical address so the total amount of physical memory is $2^{16}=65536$ 

### 9.9

a)

$$
\log_2(256*4096) = 20\ \text{bits}
$$

b)

$$
\log_2(64*4096) = 18\ \text{bits}
$$

### 9.10

a) We can simply divide the total logical address space by the page size

$$
\frac{2^{32}}{2^{12}}=2^{20}=1048576
$$

b) Here, the number of entries is equal to the number of frames in physical memory (We can assume 512 MB $=2^{29}
$)

$$
\frac{2^{29}}{2^{12}}=2^{17}=131072
$$





## Chapter 10 Exercises

### 10.1

    A page fault occurs when a page that has not been brought into memory is referenced or accessed by a process. Assuming the memory access is a valid one, the operating system will find a free frame, copy the requested frame into the free frame, and restart the instruction.

### 10.2

    A lower bound would be $n$, since each distinct frame would page fault once, and an upper bound would be $p$ if page faults occur at every possible time

### 10.3

    Optimal and LRU are generally better algorithms, especially given that these two are the two that do not suffer from Belady's anomaly, whereas FIFO and second-chance do.

### 10.4

$$
0.99(1+(0.008*2)+0.002(11000)+0.03(11000))\approx 34\  \mu \sec
$$

### 10.5

- 9EF $\rightarrow$ 0EF

- 111 $\rightarrow$ 211

- 700 $\rightarrow$ D00

- 0FF $\rightarrow$ EFF

### 10.8

This took a lot of scratch work so I didn't include it but the approach is essentially the same as in problem 10.9

| # of Frames | 1   | 2   | 3   | 4   | 5   | 6   | 7   |
| ----------- | --- | --- | --- | --- | --- | --- | --- |
| **LRU**     | 20  | 18  | 15  | 10  | 8   | 7   | 7   |
| **FIFO**    | 20  | 18  | 16  | 14  | 10  | 10  | 7   |
| **Optimal** | 20  | 15  | 11  | 8   | 7   | 7   | 7   |

### 10.9

<img title="" src="file:///C:/Users/Justin/Pictures/marktextImages/9a9f78fdc13472cbbd45907eb668f881bf67066e.png" alt="" data-align="center" width="498">

### 10.10

    A reference bit can essentially be simulated by using a valid-invalid bit

### 10.11

    No, by definition an optimal algorithm will not suffer from Belady's anomaly

### 10.12

*FIFO*

    Find the first segment large enough, and if there is no single segment long enough, then the first series of segments and, if possible rearrange memory such that this will be contiguous in memory

*LRU*

    Similar to the FIFO outlined above, but instead of finding the first segment, we find the oldest segment or series of segments 

### 10.13

    In *a*, thrashing is occurring since CPU utilization is low and disk utilization is very high. In *b* CPU utilization is sufficiently high such that the degree of multiprogramming need not be increased. In *c* CPU utilization is low and we can increase the degree of multiprogramming