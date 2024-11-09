**Justin Ciocoi**

**Mar. 28, 2024**

# CSCI 400 Textbook Notes

## Chapter 10: Buffer Overflow

### Buffer Overflow Basics

- There are known prevention techniques, but buffer overflow attacks are still of major concern due to legacy buggy code and careless programming practices

- Buffer overflow is defined by NIST as *“A condition at an interface under which more input can be placed into a buffer or data holding area than the capacity allocated, overwriting other information. Attackers exploit such system or to insert that allows
  system.”*

- A buffer overflow occurs when a process attempts to store data beyond the limits of a fixed-size buffer
  
  - This overwrites adjacent memory locations which could hold other program variables or program control flow data

- Many consequences exist for buffer overflow attacks
  
  - Corruption of program data
  
  - Unexpected transfer of control
  
  - Memory access violations
  
  - Execution of arbitrary code 

### Buffer Overflow Attacks

- In order to exploit a buffer overflow, an attacker needs the following
  
  - Identification of some buffer overflow vulnerability
  
  - Determination of how exactly that buffer is stored in memory

- Identification of vulnerable programs can be done as follows
  
  - Inspection of program source
  
  - Tracing program execution
  
  - Using fuzzing tools to identify vulnerabilities

### Stack Buffer Overflows

- This occurs when the buffer is located on the stack 

- These types of buffer overflows are still being widely exploited

- The target program of a stack overflow could be any of the following
  
  - A trusted system utility
  
  - Network service daemon
  
  - Commonly used library code

### Shellcode

- Shellcode refers to an attacker having the capability of remotely connecting to a victim's machine via the shell as the result of a buffer overflow attack 

- Arbitrary code which is supplied by the attacker
  
  - Traditionally, this will be saved in buffer being overflowed and will transfer control to a user command-line interpreter

- Machine code, which is specific to hardware and operating systems and requires a very high technical skill to adequately utilize and exploit

- The **Metasploit Project** provides information to people who perform penetration testing, IDS signature development, and exploit research 

- Shellcode functions
  
  - Launch a remote shell
  
  - Create a reverse shell connecting back to the attacker
  
  - Use local exploits that establish a shell
  
  - Flush firewall rules which prevent other attacks
  
  - Break out of a chroot

### Buffer Overflow Defenses

- There are two broad approaches for defense against buffer overflow attacks: compile-time defenses and run-time defenses

- **Compile-time**
  
  - Using a modern high-level language is often advisable since these languages are less vulnerable to buffer overflow attacks
  
  - Additional execution of code costs resources and this also can limit a language's usefulness in terms of writability
  
  - Coding written in older languages should be paid close attention to in order to avoid introducing buffer overflow vulnerabilities to a process 
  
  - One concern with the C language is the use of unsafe standard library routines, and replacements for these libraries have arisen to stop the use of older vulnerable libraries
  
  - Stack protection adds function entry and exit code which checks the stack for signs of random corruption
    
    - This uses a random canary which is different on different systems and unpredictable
    
    - This is also referred to as Stack Guard and Return Address Defender (RAD)

- **Run-time**
  
  - Use virtual memory to make some regions of memory non-executable 
  
  - Requires MMU support
  
  - The location of key data structures (stack, heap, global data) should be manipulated by using a random shift for each process
  
  - There should also be guard pages in between critical regions of memory which are flagged in the MMU as illegal addresses

### Return to System Call

# 
