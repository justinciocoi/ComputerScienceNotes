**Justin Ciocoi**

**Nov. 7, 2023**

# CSCI 377

## Homework for Quick Sort

#### Question 1)

- Given array: $A=[13, 27, 18, 2, 40, 39, 6, 10]$

- Given function call: `partition(A,1,8)`

- So, the partition function will set the 8th element, 10, as the pivot and find its correct position

- Thus, the resulting array will be ini the form

$$
[2,6,10,13,27,18,40,39]
$$

#### Question 2)

- Starting array $A=[28,52,18,43,16]$

- 16 is the pivot to begin

- $i$ begins at $A[-1]$

| 0     | 1   | 2   | 3   | 4           |
| ----- |:--- | --- | --- | ----------- |
| 28    | 52  | 18  | 43  | *16*        |
| **j** |     |     |     | **r=pivot** |

- **First repetition of for loop**
  - Compare $A[j]=28$ to $A[r]=16$
  - Is $28<16$? No.
    - Increment j

| 0   | 1     | 2   | 3   | 4           |
| --- |:----- | --- | --- | ----------- |
| 28  | 52    | 18  | 43  | *16*        |
|     | **j** |     |     | **r=pivot** |

- **Second repetition of for loop**
  
  - Compare $A[j]=52$ to $A[r]=16$
  
  - Is $52<16$? No.
    
    - increment j

| 0   | 1   | 2     | 3   | 4           |
| --- |:--- | ----- | --- | ----------- |
| 28  | 52  | 18    | 43  | *16*        |
|     |     | **j** |     | **r=pivot** |

- **Third repetition of for loop**
  
  - Compare $A[j]=18$ to $A[r]=16$
  
  - Is $18<16$? No.
    
    - increment j

| 0   | 1   | 2   | 3     | 4           |
| --- |:--- | --- | ----- | ----------- |
| 28  | 52  | 18  | 43    | *16*        |
|     |     |     | **j** | **r=pivot** |

- **Fourth repetition of for loop**
  
  - Compare $A[j]=43$ to $A[r]=16$
  
  - Is $43<16$? No.
    
    - increment j, and exit for loop

- **Finally, swap $A[i+1]=A[-1+1]=A[0]$ and $A[r]$**

| 0   | 1   | 2   | 3   | 4   |
| --- |:--- | --- | --- | --- |
| 16  | 52  | 18  | 43  | 28  |

- Now, we can repeat the process setting the pivot as 28, j to 1, and i to 0

| 0     | 1     | 2   | 3   | 4           |
| ----- |:----- | --- | --- | ----------- |
| 16    | 52    | 18  | 43  | *28*        |
| **i** | **j** |     |     | **r=pivot** |

- **First repetition**
  
  - Compare $A[j]=52$ to $A[r]=28$
  
  - Is $52<28$? No.
    
    - Increment j

| 0     | 1   | 2     | 3   | 4           |
| ----- |:--- | ----- | --- | ----------- |
| 16    | 52  | 18    | 43  | *28*        |
| **i** |     | **j** |     | **r=pivot** |

- **Second repetition**
  
  - Compare $A[j]=18$ and $A[r]=28$
  
  - Is $18<28$? Yes.
    
    - Increment i
    
    - Swap $A[i]=A[1]=52$ and $A[j]=A[2]=18$
    
    - Increment j

| 0   | 1     | 2   | 3     | 4           |
| --- |:----- | --- | ----- | ----------- |
| 16  | 18    | 52  | 43    | *28*        |
|     | **i** |     | **j** | **r=pivot** |

- **Third repetition**
  
  - Compare $A[j]=43$ to $A[r]=28$
  
  - Is $43<28$? No.
    
    - Increment j and exit for loop
  
  - **Finally, swap $A[i+1]=A[-1+1]=A[2]$ and $A[r]$**

| 0   | 1   | 2   | 3   | 4   |
| --- |:--- | --- | --- | --- |
| 16  | 18  | 28  | 43  | 52  |

- The array has now been sorted



#### Question 3)

- The best case scenario running time for the quick sort algorithm is $O(nlog(n))$




