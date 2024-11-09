**Justin Ciocoi**

**Nov. 21, 2023**

# CSCI 375 Operating Systems

## Project 3 Report: Synchronization Exercise

    For both parts of the synchronization project, the synchronization logic remains consistent and only the implementation changes. The logic is as follows:

- A writer can enter the critical section if no other processes are in the critical section, and blocks all other processes once it is in the critical section

- A reader can enter the critical as long as no writer and less than 3 readers are present in the critical section
  
  - All readers block writer processes
  
  - Only the third reader to enter the critical section blocks other reader processes

#### Part 1:

    In part 1, synchronization was implemented using counting semaphores. A writer semaphore was initialized to $1$ and a reader semaphore initialized to $3$. Within the reader and writer processes, code analogous to the `wait()` and `signal()` functions controls processes' access to shared data.

- The following output snippet shows a more "interesting" part of the output which displays behavior consistent with the synchronization rules outlined above
  
  <img title="" src="file:///Users/justin/Pictures/marktextImages/76af94f627194b551e5f64364eec0f534c5c344f.png" alt="" data-align="center" width="527">

- I used additional variables to track the proportion of readers and writers chosen by the `rand()` function to verify the behavior is as expected

- I also tracked the total number of reader and writer processes completed, and reported all of these totals at the end of the output
  
  <img title="" src="file:///Users/justin/Pictures/marktextImages/42924b99b0003bb633a94660d3e25afe2682c629.png" alt="" data-align="center" width="534">

****

#### Part 2:

- In part 2, synchronization was instead implemented using the `compareAndSwap()` functioned taken almost exactly from the textbook:
  
  ```cpp
  bool compareAndSwap(bool *value, bool expected, bool newValue)
  {
      if(*value == expected)
      {
          *value = newValue;
          return true;
      }
      return false;
  }
  ```

- Two separate locks - one for readers and one for writers - were used to control access to the shared data

- The two screenshots below display the same features illustrated for part 1 of the project, with additional statements informing the user of lock status
  
  <img title="" src="file:///Users/justin/Pictures/marktextImages/56aedd12e778cb1d4b523af8c0101da3e8f71949.png" alt="" data-align="center" width="501">

****

<img title="" src="file:///Users/justin/Pictures/marktextImages/b1efe956282831142fff9af332020913f7243a77.png" alt="" data-align="center" width="505">
