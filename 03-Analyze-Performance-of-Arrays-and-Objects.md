### OBJECTIVES

- Understand how objects and arrays work, through the lens of Big O
- Explain why adding elements to the begining of an array is costly
- Compare and constrast the runtime for arrays and objects, as well as built-in methods

#### The BIG O of Objects

- Objects are unordered list store values in key-value pairs

- WHEN TO USE OBJECTS

  - When you don't need order
  - When you need fast access/insertion and removal
  - Quick Access - Means CONSTANT TIME for INSERT, REMOVE, ACCESS Data

    - INSERTION - O(1) - CONSTANT TIME
    - REMOVAL - O(1) - CONSTANT TIME
    - SEARCHING - O(N) - LINEAR TIME
    - ACCESS/RETRIEVE - O(1) - CONSTANT TIME

  - When you do not need any ordering, Objects are excellent choice!

- BIG O of OBJECT METHODS
  - Object.keys - O(N)
  - Object.values - O(N)
  - Object.entries - O(N)
  - hasOwnProperty - O(1)
