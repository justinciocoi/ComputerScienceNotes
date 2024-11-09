**Justin Ciocoi**

**Oct. 16, 2023**

# CSCI 377 Textbook Notes

****

## Computer Algorithms

****

### Chapter 4: Divide and Conquer

****

- *Recall* that in a divide and conquer problem, we solve problems recursively using three steps at each level of recursion
  
  - ***Divide*** the problem into a number of sub-problems that are smaller instances of the same problem
  
  - ***Conquer*** the sub-problems by solving them recursively, or in a straightforward manner
  
  - ***Combine*** the solutions to the subproblems into the solution for the original problem

- *Recursive case* requires further recursion, after which we can say the recursion "bottoms out" and reaches the

- *Base case*, which can then be solved in a straightforward manner

- ****

#### Recurrences

****

- Recurrences go hand in hand with the divide and conquer paradigm

- A *recurrence* is an equation or inequality that describes a function in terms of its value on smaller inputs, for example
  
  - $T(n)=\Theta(1)$ if $n=1$
  
  - $T(n)=2T(n/2)+\Theta(n)$ if $n>1$
  
  - *Solution:* $T(n)=\Theta(nlog(n))$

- There are three methods covered in this chapter for obtaining asymptotic $\Theta$ or $O$ bounds on the solution
  
  - *The Substitution Method:* where we can use mathematical induction to find our bounds
  
  - *The Recursion-Tree Method:* where we turn the recurrence into a tree whose nodes represent the costs incurred at various different levels of the recursion
    
    - We can then use this tree and mathematical reasoning to solve for the bounds
  
  - *The Master Method:* Which generalizes a form –– $T(n)=aT(n/b)+f(n)$ –– of the recurrence and provides rules for the bounds based on the values of $a$,  $b$, and $f(n)$
