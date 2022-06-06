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

- Describe what `Big O Notation` is
- Simplify `Big O Notation`
- Define `Time Complexity` and `Space Complexity`
- Evaluate `Time Complexity` and `Space Complexity` of different algorithms using Big O notation.
- Describe what a `logarithm` is

- KEYWORDS
