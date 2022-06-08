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

### ARRAYS

- Ordered List!

- WHEN TO USE ARRAYS

  - When you need ORDER
  - When you need Fast ACCESS / INSERTING and REMOVAL (Sort of DEPENDS)

- BIG O of ARRAYS

  - INSERTION - It Depends

    - Inserting/Adding an Element at the END of the ARRAY is CONSTANT TIME - O(1)
    - Inserting/Adding an Element at the BEGINNING of the ARRAY is LINEAR TIME - O(N)
      - It is becuase the Array requires the reindexing when you ADD/INSERT an element in the BEGINNING or MIDDLE of the ARRAY
      - PUSH and POP are always Faster then SHIFT and UNSHIFT

  - REMOVAL - It Depends

    - Removing an Element at the END of the ARRAY is CONSTANT TIME - O(1)
    - Removing an Element at the BEGINNING of the ARRAY is LINEAR TIME - O(N)
      - It is becuase the Array requires the reindexing when you REMOVE an element in the BEGINNING or MIDDLE of the ARRAY
      - PUSH and POP are always Faster then SHIFT and UNSHIFT

  - SEARCHING - O(N)
  - ACCESS - O(1)

- BIG O of ARRAY METHODS
  - push - O(1) - because no reindexing involves when you add the element at the end of array
  - pop - O(1) - because no reindexing involves when you remove the element at the end of the array
  - shift - O(N)
  - unshift- O(N)
  - concat - O(N)
  - slice - O(N)
  - splice - O(N)
  - sort - O(N \* log N)
  - forEach/map/filter/reduce/etc. - O(N)
