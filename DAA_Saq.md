# Unit 1

## 1. **What is an Algorithm? How to devise an Algorithm?**
   An algorithm is a step-by-step procedure to solve a problem or perform a task. To devise an algorithm, follow these steps: 
   1. Understand the problem.
   2. Break down the problem into smaller subproblems.
   3. Design a high-level plan or pseudocode.
   4. Refine the plan and handle details.
   5. Implement and test the algorithm.

## 2. **Describe the characteristics of an Algorithm.**
   An algorithm should be: 
   - Clear: Well-defined steps.
   - Input: Takes inputs and produces outputs.
   - Finiteness: Terminates after a finite number of steps.
   - Effective: All steps are doable.
   - Unambiguous: Steps have precise meanings.
   - Efficient: Solves problem in a reasonable time.

## 3. **Write short notes on calculating Space complexity.**
   Space complexity measures memory usage by an algorithm. It includes: 
   - **Auxiliary space:** Space for variables and data structures.
   - **Input space:** Memory required by input.
   - **Output space:** Memory required by output.
   Analyze these spaces to determine the algorithm's memory requirements.

## 4. **Define Big O notation. Explain with suitable example.**
   Big O notation describes the upper bound of an algorithm's growth rate. 
   - The function f(n) = O(g(n)) if and only if there exists positive constants C and n₀ such that f(n) ≤ C * g(n) for all values of 'n' greater than or equal to n₀.

## 5. **Define Omega notation. Explain with suitable example.**
   Omega notation represents the lower bound of an algorithm's growth rate. 
   - The function f(n) = Ω(g(n)) if and only if there exists positive constants C and n₀ such that C * g(n) ≤ f(n) for all values of 'n' greater than or equal to n₀.

## 6. **Define Theta notation. Explain with suitable example.**
   Theta notation provides both upper and lower bounds, indicating a tight bound on growth rate. 
   - The function f(n) = Θ(g(n)) if and only if there exist positive constants C₁, C₂, and n₀ such that C₁ * g(n) ≤ f(n) ≤ C₂ * g(n) for all values of 'n' greater than or equal to n₀.

## 7. **Describe control abstraction of Divide and Conquer strategy.**
   Divide and Conquer breaks a problem into smaller subproblems, solves them independently, and combines their solutions to solve the original problem. Control abstraction involves the steps of dividing, conquering, and combining to create a modular and efficient algorithm.

## 8. **Solve the recurrence relation for a=2, b=2, T(1)=2, and f(n)=n.**
   - Given the recurrence relation $T(n) = 2 \cdot T\left(\frac{n}{2}\right) + n$, we want to find  its time complexity.  
   - The Master Theorem helps us analyze this kind of recurrence.   
   - For our values $a = 2$ and $b =   2$, we compare $f(n)$ (which is $n$) with $n^{\log_b a}$ (which is $n^{\log_2 2} = n$).   
   - Since $f(n)$ and $n^{\log_b a}$ are in the same category, the time complexity is in the 2nd case of the Master Theorem. This means the time complexity is approximately $T(n) =   \Theta(n \log n)$.   
   - So, for the given recurrence relation, the time complexity is $\Theta(n \log n)$.

## 9. **Derive the time complexity for a=28, b=3, and f(n)=cn^3 using the substitution method.**
   ! Answer unknown

## 10. **Derive the time complexity of Strassen’s Matrix multiplication?**

Strassen's algorithm recursively divides the problem into smaller subproblems. For each of the four submatrices, there are seven matrix multiplications (denoted as M1, M2, ..., M7) involved. These multiplications occur on submatrices of size $n/2 \times n/2$.

The recursive algorithm has a recurrence relation $T(n) = 7T(n/2) + O(n^2)$, where the $7T(n/2)$ accounts for the seven subproblems and $O(n^2)$ is the cost of combining the subproblems.

Using the Master Theorem or recurrence solving techniques, we can determine that the time complexity of Strassen's Matrix Multiplication is approximately $O(n^{\log_2 7}) \approx O(n^{2.81})$. This complexity is better than the naive matrix multiplication algorithm, which is $O(n^3)$, especially for large matrices.

---


Additional Information:

    
Given two $n \times n$ matrices A and B, Strassen's algorithm breaks them into four 
$n/2 \times n/2$ submatrices each, resulting in the following partitions:

```
A = | A11  A12 |    B = | B11  B12 |
    | A21  A22 |        | B21  B22 |
```

The multiplication of matrices A and B using Strassen's algorithm can be expressed as:

```
C = | C11  C12 |
    | C21  C22 |
```

Where each $C_{ij}$ is calculated as follows:

```
C11 = A11*B11 + A12*B21
C12 = A11*B12 + A12*B22
C21 = A21*B11 + A22*B21
C22 = A21*B12 + A22*B22
```

**Master Theorem:**

The Master Theorem is a tool used to analyze the time complexity of divide-and-conquer algorithms with recurrence relations of the form $T(n) = aT(n/b) + f(n)$, where $a$ is the number of subproblems, $b$ is the factor by which the problem size is reduced, and $f(n)$ is the cost of combining the subproblems.

The Master Theorem has several cases depending on how $f(n)$ compares with $n^{\log_b a}$:

1. If $f(n) = O(n^{\log_b a - \epsilon})$ for some constant $\epsilon > 0$, then $T(n) = \Theta(n^{\log_b a})$.
2. If $f(n) = \Theta(n^{\log_b a})$, then $T(n) = \Theta(n^{\log_b a} \log n)$.
3. If $f(n) = \Omega(n^{\log_b a + \epsilon})$ for some constant $\epsilon > 0$ and $a f(n/b) \leq k f(n)$ for some constant $k < 1$ and sufficiently large $n$, then $T(n) = \Theta(f(n))$.

**Applying the Master Theorem to Strassen's Matrix Multiplication:**

1. We have the recurrence relation $T(n) = 7T(n/2) + O(n^2)$, where $a = 7$ (due to seven subproblems created), $b = 2$ (because matrices are divided into four parts), and $f(n) = O(n^2)$ (the cost of combining subproblems).

2. We need to compare $f(n)$ with $n^{\log_b a}$:

   - $f(n) = O(n^2)$.
   - $n^{\log_b a} = n^{\log_2 7}$.

   Since $f(n)$ is polynomially smaller than $n^{\log_b a}$, we are in Case 1 of the Master Theorem. Therefore, the time complexity of Strassen's Matrix Multiplication is $T(n) = \Theta(n^{\log_b a}) = \Theta(n^{\log_2 7})$.

**Approximating the Logarithm:**

$\log_2 7$ is approximately 2.8074. Hence, $T(n)$ is often approximated as $O(n^{2.8074})$, which is better than the $O(n^3)$ time complexity of the naive matrix multiplication algorithm.

Keep in mind that while Strassen's algorithm has a theoretically better time complexity, it's not always faster in practice due to constants and overhead. Nonetheless, the analysis provides valuable insights into how divide-and-conquer techniques can lead to improved algorithms for specific problems.
