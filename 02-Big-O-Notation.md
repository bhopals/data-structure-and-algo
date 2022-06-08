## Big O Notation

- OBJECTIVES

### Intro to Big O

- Motivate the need for something like `Big O Notation`

  - Whats the Idea here?

    - Imagine we have multiple implementations of the same function.
    - How can we determine which one is the `BEST`?

  - Who Cares?
    - It is important to have a precise vocabulary to talk about how our code performs.
    - Useful for discussing trade-offs between different approaches
    - When your code slows down or crashes, identifying parts of the code that are inefficient can help us find
      pain points in our applications.
    - Less Important: It comes up in INTERVIEWS!

### Timing Our Code

- What does better mean?

  - Faster?
  - Less memory-intensive?
  - More readable?

  - Means - Writing efficient code that does not use tons of memory, but also readable

- Why not use Timers?

  `let t1 = performance.now()`
  `YOUR CODE`  
   `let t1 = performance.now()`  
   `` console.log(`Time Elapsed: ${(t2-t1)/1000} seconds.`) ``

  - EXAMPLE 1
    ```
    function addUpTo(n) {
      let total = 0;
      for(let i = 0; i <= n; i++) {
       total+=i
      }
      return total
    }
    ```
  - EXAMPLE 2

  ```
    function addUpTo(n) {
        return n * ((n+1)/2)
    }
  ```

- The Problem with Time

  - Difference machines will record different times
  - The same machine will record different times!
  - For fast algorithms, speed measurements may not be precise enough?

### Counting Operations

- If not Time, then What?

  - Rather than counting seconds, which are so variable...
  - Let's countthe number of simple operations the computer has to Perform!

  - 3 SIMPLE Operations (Multiply, Addition, Division), regardless of the size of `n`

    ```
    function addUpTo(n) {
       return n * ((n+1)/2)
    }
    ```

  - `n` addition operations (total+=i), `n` assignments (total+=i), `n` additions and assignments (i++),
    `1` assignment (let i = 0), `1` assignment (let total = 0), `n` comparisons (i <= n)

```
   function addUpTo(n) {
     let total = 0;
     for(let i = 0; i <= n; i++) {
     total+=i
       }
       return total
   }
```

- COUNTING IS HARD!

  - Depending on what we count, the number of operations can be as low as `2n` or high as `5n+2`
  - But regardless of the exact number, the number of operations grows roughly proportionally with `n`

### Official Intro to Big O

- Big O Notation is a way to formalize fuzzy counting.
- It allows us to talk formally about how the runtime of an algorithm grows as the input grow.
- It is a way of describing a relationship between INPUT to Function or as it grows.
- The relationship between the input size and then the time relative to that input.

- BIG O DEFINITION

  - We say that an algorithm is `O(f(n))` if the number of simple operations the computer has to do it eventually less
    than a constant times `f(n)`, as `n` increases.
  - `f(n)` could be LINEAR `(f(n)=n)` ==> `O(n)`
  - `f(n)` could be QUADRATIC `(f(n)=n2)` ==> `O(n2)`
    - `O(n)` operation inside of an `O(n)` operation (NESTED LOOP) ==> `O(n*n)` ==> `O(n2)` ==> O n square
  - `f(n)` could be CONSTANT `(f(n)=1)` ==> `O(1)`
  - `f(n)` could be something entirely different.

  - When we talk about Big O Notation, we talk about the worst case scenario. That means
    we are talking about basically the UPPER BOUND for the RUNTIME

### Simplifying Big O Expression

- When determining the time complexity of an algorithm, there are some helpful rule of thumbs for Big O Expressions.
- These RULE OF THUMB are consequences of the definition of Big O Notation.
- RULE OF THUMB

  - Constants Don't Matter

    - O(2n) ==> O(n)
    - O(500n) ==> O(n)
    - O(500) ==> O(1)
    - O(12n2) ==> O(n2)

  - The Smaller Terms Don't Matter

    - O(n+10) ==> O(n)
    - O(1000n + 50) ==> O(n)
    - O(n2+5n+8) ==> O(n2)

  - Arithmetic Operations are CONSTANT
  - Variable Assignment is CONSTANT
  - Accessing Element in an Array (by INDEX) or Object (by KEY) is CONSTANT
  - In a Loop, the complexity is the length of the LOOP TIMES the complexity of whatever happens inside of the LOOP.

- EXAMPLES

  - 1. logAtLeast5 ==> `O(n)`

    ```
    function logAtLeast5(n) {
        for(var i=0; i <= Math.max(5, n); i++) {
            console.log(i)
        }
    }
    ```

  - 2. logAtMost5 ==> `O(1)`
    ```
    function logAtMost5(n) {
        for(var i=0; i <= Math.min(5, n); i++) {
            console.log(i)
        }
    }
    ```

### Space Complexity / Auxiliary Space Complexity

- TIME COMPLEXITY - How can we analyze the `RUNTIME` of an algorithm as the size of the inputs increases.
- SPACE COMPLEXITY - How much additional memory do we need to allocate in order to run the code in our Algorithm.
- Auxiliary Space Complexity is to refer to SPACE required by the ALGORITHM, not including space taken up by the INPUTS.
- That means when we talk about SPACE COMPLEXITY, technically we will be talking about AUXILIARY SPACE COMPLEXITY.

- SPACE COMPLEXITY - RULE OF THUMB

  - Most Primitives (booleans, numbers, undefined, null) are CONSTANT SPACE
  - Strings require `O(n)` SPACE where `n` is the string length
  - Reference Types are generally `O(n)`, where `n` is the length (for arrays) or the number of keys (for objects)

- EXAMPLES

  - 1. sum ==> `O(1)`

  ```
   function sum(arr) {
       let total = 0;
       for (let i=0; i< arr.length; i++) {
           total += arr[i];
       }
       return total;
   }
  ```

  - Calculate Space Complexity

    - one number (let total - number), one number (let i=0 - number) ==>` O(1)` Space

  - 2. double ==> `O(n)`

  ```
   function double(arr) {
       let newArr = [];
       for (let i=0; i< arr.length; i++) {
           newArr.push(2 * arr[i]);
       }
       return newArr;
   }
  ```

  - Calculate Space Complexity
    - one Reference Types with `n` length (let newArr = []; - Reference Types/Array), one number (let i=0 - num) ==> `O(n)` Space

### Logarithms

- We have encountered some of the most common complexities: `O(1)`,` O(n)`, `O(n2)`
- Sometimes Big O Expressions involve more complex mathematical expressions
- One that appears more often than you might like is the LOGARITHM.

- What is Logarithm

  - Logarithm is the INVERSE of Exponentiation. Log2N, Log3N
  - The Logarithm of a number roughly measures the number of times you can divide that number by 2
    before you get a value that is less than or equal to one.

- LOGARITHMIC Time Complexity IS GREAT
- CONSTANT Time Complexity IS the BEST

- BEST to WORST ==>

  - CONSTANT => Logarithm => LINEAR => Linearithmic => Quadratic => Cubic => Exponential => Factorial
  - `O(1)` < `O(log n)` < `O(n)` < `O(n log n)` < `O(n2)` < `O(n3)` , `O(2n)`, `O(n!)`

- WHY CARES ABOUT LOGARITHM COMPLEXITY

  - Certain Searching Algorithms have Logarithmic TIME Complexity
  - Effecient Sorting Algorithms involve Logarithms
  - Recursion Sometimes involves Logarithmic Space Complexity

- RECAP

  - To Analyze the performance of an Algorithm, we use Big O Notation
  - Big O Notation can give us a high level understanding of the TIME or SPACE complexity of an Algorithm
  - Big O Notation doesn't care about precision, only about general trends(linear? quadratic? constant?)
  - The Time or Space Complexity (as measured by Big O) depends only on the algorithm, not Hardware used to run the Algo.
  - Big O Notation is everywhere, so get lots of practice!

- KEYWORDS
  - <CONSTANT/Logarithm/LINEAR/Linearithmic/Quadratic/Cubic/Exponential/Factorial> Time COMPLEXITY
  - <CONSTANT/Logarithm/LINEAR/Linearithmic/Quadratic/Cubic/Exponential/Factorial> (Auxiliary) Space COMPLEXITY
  - Compare the Runtime of all the algorithms to choose the best one
