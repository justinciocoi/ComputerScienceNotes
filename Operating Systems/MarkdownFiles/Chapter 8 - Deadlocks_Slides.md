**Justin Ciocoi**

**Nov. 8, 2023**

# CSCI 375 Slide Notes

## Chapter 8: Deadlocks

- Every computer system consists of resources of different types

- Resource types, like CPU cycles, memory space, I/O Devices, are denoted by $R_1, R_2,...,R_m$

- Each resource type, $R_i$ has a certain number of instances. $W_i$

- A process, when utilizing a resource, will do so as follows
  
  - First, the process must *request* a resource from the system
  
  - Next, once the request is granted the process can use those resources
  
  - Once the process has finished using those resources, it must *release* them such that other processes can access them 

- Deadlocks, where processes cannot proceed because they block each other's progress, happen only if the following four conditions all hold simultaneously
  
  - *Mutual Exclusion*, where only one process at a time may use a resource
  
  - *Hold and Wait*, when a process which is holding at least one resource is waiting to acquire additional resources
  
  - *No preemption*, such that a resource can be released only voluntarily by the process is holding it after that process has completed its task
  
  - *Circular Wait*, meaning that there exists a set, $[P_0, P_1, ..., P_n$], such that:
    
    - $P_0$ is waiting for a resource that is held by $P_1$
    
    - $P_1$ is waiting for a resource that is held by $P_2$
    
    - ...
    
    - $P_{n-1}$ is waiting for a resource that is held by $P_n$
    
    - $P_n$ is waiting for a resource that is held by $P_0$
