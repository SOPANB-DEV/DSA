# 🧠 Data Structures & Algorithms in C

> A collection of fundamental Data Structures and Algorithms implemented in C, organized for learning, revision, and GitHub reference.

## 📚 Contents

- [🔗 Linked List](#-linked-list)
- [🚶 Queue](#-queue)
- [🔎 Search Algorithms](#-search-algorithms)
- [🔃 Sorting Algorithms](#-sorting-algorithms)
- [📚 Stack](#-stack)
- [⏱️ Complexity Cheat Sheet](#️-complexity-cheat-sheet)
- [⌨️ Useful Shortcuts](#️-useful-shortcuts)
- [▶️ Compile & Run](#️-compile--run)
- [📝 Learning Roadmap](#-learning-roadmap)

---

# 🔗 Linked List

A linked list stores data in dynamically allocated nodes connected using pointers.

## 1. Singly Linked List

**File:** `SLL.c`

```text
HEAD
  |
  v
[10] -> [20] -> [30] -> NULL
```

Operations implemented:

- Create list
- Display list
- Insert at beginning
- Insert at end
- Insert after a position
- Delete from beginning
- Delete from end
- Delete from a position

The uploaded implementation uses a node containing `data` and a `next` pointer. fileciteturn0file1L5-L8

## 2. Doubly Linked List

**File:** `DLL.c`

```text
NULL <- [10] <-> [20] <-> [30] -> NULL
```

Operations implemented:

- Create nodes
- Display
- Insert at beginning
- Insert at a position
- Insert at end
- Delete at beginning
- Delete at a position
- Delete at end
- Reverse

Each node contains both `next` and `prev` pointers. fileciteturn0file0L4-L7

## 3. Circular Linked List

**File:** `CLL.c`

```text
       +----------------------+
       |                      |
       v                      |
     [10] -> [20] -> [30] ----+
```

Operations implemented:

- Create circular list
- Display
- Insert at beginning
- Insert at end
- Insert at position
- Delete at beginning
- Delete at end
- Delete at position

The implementation maintains a `tail` pointer and connects the last node back to the first node. fileciteturn0file18L23-L29

---

# 🚶 Queue

A queue follows **FIFO — First In, First Out**.

```text
ENQUEUE -> [10] [20] [30] -> DEQUEUE
            ^           ^
          FRONT        REAR
```

## 1. Queue

**File:** `queue.c`

Implemented operations include:

- `enqueue()`
- `dequeue()`
- `peek()`
- `IsEmpty()`
- Empty queue
- Display

The uploaded program uses an array with `front` and `rear` indices. fileciteturn0file4L5-L7

## 2. Circular Queue

**File:** `circular_queue.c`

```text
        +---------------------+
        |                     |
        v                     |
      [10] -> [20] -> [30] -> [40]
        ^                     |
        +---------------------+
```

Implemented operations:

- Enqueue
- Dequeue
- Display

The implementation uses modulo arithmetic so the rear can wrap around the array. fileciteturn0file2L5-L8

## 3. Priority Queue

**File:** `priorityQueue.c`

Each queue node contains:

```text
+----------------+
| Data           |
| Priority       |
| Next Pointer   |
+----------------+
```

Implemented operations:

- Enqueue
- Dequeue
- Display

The program stores `data` and `priority` in each node and inserts nodes according to priority. fileciteturn0file3L3-L7

## 4. Queue using Linked List

**File:** `queue_linked_list.c`

```text
FRONT                         REAR
  |                             |
  v                             v
[10] -> [20] -> [30] -> NULL
```

Implemented operations:

- Enqueue
- Dequeue
- Display

The implementation maintains separate `front` and `rear` pointers. fileciteturn0file5L9-L21

---

# 🔎 Search Algorithms

## 1. Linear Search

**File:** `linear_search.c`

```text
[10] [25] [30] [45] [60]
  ^
Check elements one by one
```

- No sorting requirement
- Best: `O(1)`
- Average: `O(n)`
- Worst: `O(n)`

The uploaded program scans the array from the beginning until it finds the target or reaches the end. fileciteturn0file7L16-L24

## 2. Binary Search

**File:** `binary_search.c`

> The input array must be sorted.

```text
[1] [3] [5] [7] [9] [11] [13]
            ^
           MID
```

- Best: `O(1)`
- Average: `O(log n)`
- Worst: `O(log n)`

The implementation repeatedly calculates a middle position and reduces the search range. fileciteturn0file6L16-L30

## 3. Recursive Binary Search

**File:** `recursive_binary_search.c`

The function recursively searches either the left or right half of the sorted array. fileciteturn0file8L3-L15

- Time: `O(log n)`
- Recursive stack space: `O(log n)`

> The repository also contains `binary_search(1).c`, another iterative binary-search implementation.

---

# 🔃 Sorting Algorithms

## 1. Bubble Sort

**File:** `bubblesort.c`

```text
5  3  8  1  2
   ^  ^
 compare adjacent elements
```

The implementation repeatedly compares adjacent elements and swaps them when they are out of order. fileciteturn0file10L13-L20

| Case | Time |
|---|---:|
| Best | O(n²) |
| Average | O(n²) |
| Worst | O(n²) |

## 2. Insertion Sort

**File:** `InsertionSort.c`

```text
Sorted       Unsorted
[2 5 7]  |  [4 9 1]
             ^
            key
```

The program selects a `key`, shifts larger elements, and inserts the key into the correct position. fileciteturn0file11L2-L13

| Case | Time |
|---|---:|
| Best | O(n) |
| Average | O(n²) |
| Worst | O(n²) |

## 3. Quick Sort

**File:** `quick_sort.c`

```text
              PIVOT
                |
        +-------+-------+
        |               |
     smaller          larger
        |               |
     recursive       recursive
```

The uploaded implementation uses the last element as the pivot, partitions the array, and recursively sorts both partitions. fileciteturn0file12L8-L23

| Case | Time |
|---|---:|
| Best | O(n log n) |
| Average | O(n log n) |
| Worst | O(n²) |

## 4. Selection Sort

**File:** `selectionsort.c`

```text
Find minimum
     |
     v
Place at beginning
     |
     v
Repeat
```

The program finds the minimum element in the remaining unsorted portion and swaps it into position. fileciteturn0file13L13-L21

| Case | Time |
|---|---:|
| Best | O(n²) |
| Average | O(n²) |
| Worst | O(n²) |

---

# 📚 Stack

A stack follows **LIFO — Last In, First Out**.

```text
       TOP
        |
        v
      +----+
      | 30 | <- POP
      +----+
      | 20 |
      +----+
      | 10 |
      +----+
        ^
       PUSH
```

## 1. Stack using Array

**File:** `stack.c`

Operations:

- Push
- Pop
- Peek
- Display
- Search

The stack uses an array and a `top` index. fileciteturn0file16L3-L11

## 2. Stack using Linked List

**File:** `stack_linked_list.c`

```text
TOP
 |
 v
[30] -> [20] -> [10] -> NULL
```

Operations:

- Push
- Pop
- Display

The linked-list version stores the stack top in a pointer and inserts/removes nodes from that end. fileciteturn0file17L9-L16

## 3. Infix to Postfix

**File:** `infix_to_postfix.c`

Example:

```text
Infix:
A + B * C

Postfix:
ABC*+
```

The program uses a stack for operators, parentheses, and precedence. Its precedence levels include `^`, `* /`, and `+ -`. fileciteturn0file14L12-L20

## 4. Postfix Evaluation

**File:** `postfix_eval.c`

Example:

```text
Postfix: 23*5+

2 3 * -> 6
6 5 + -> 11

Result = 11
```

The implementation evaluates postfix expressions using an integer stack and supports `+`, `-`, `*`, `/`, and `^`. fileciteturn0file15L79-L110

> **Note:** This implementation treats postfix operands as individual digits.

---

# ⏱️ Complexity Cheat Sheet

| Algorithm / Operation | Best | Average | Worst |
|---|---:|---:|---:|
| Linear Search | O(1) | O(n) | O(n) |
| Binary Search | O(1) | O(log n) | O(log n) |
| Recursive Binary Search | O(1) | O(log n) | O(log n) |
| Bubble Sort | O(n²) | O(n²) | O(n²) |
| Insertion Sort | O(n) | O(n²) | O(n²) |
| Quick Sort | O(n log n) | O(n log n) | O(n²) |
| Selection Sort | O(n²) | O(n²) | O(n²) |
| Stack Push | O(1) | O(1) | O(1) |
| Stack Pop | O(1) | O(1) | O(1) |
| Queue Enqueue | O(1) | O(1) | O(1) |
| Queue Dequeue | O(1) | O(1) | O(1) |

---

# ⌨️ Useful Shortcuts

## 💻 VS Code

| Shortcut | Action |
|---|---|
| `Ctrl + S` | Save |
| `Ctrl + P` | Quick file search |
| `Ctrl + Shift + P` | Command Palette |
| `Ctrl + F` | Find |
| `Ctrl + H` | Find & Replace |
| `Ctrl + /` | Toggle comment |
| `Shift + Alt + F` | Format document |
| `Ctrl + `` | Open/close terminal |
| `Ctrl + Shift + E` | Explorer |
| `Ctrl + Shift + G` | Source Control |
| `Alt + Up/Down` | Move line |
| `Shift + Alt + Down` | Duplicate line |
| `Ctrl + Z` | Undo |
| `Ctrl + Y` | Redo |

## 🐙 Git / GitHub

```bash
git status
git add .
git commit -m "Add DSA implementations"
git push
git pull
git log --oneline
git checkout -b feature/dsa-update
```

---

# ▶️ Compile & Run

### Linux / macOS

```bash
gcc SLL.c -o SLL
./SLL
```

### Windows / MinGW

```bash
gcc SLL.c -o SLL.exe
SLL.exe
```

### Recommended compiler flags

```bash
gcc -Wall -Wextra program.c -o program
```

---

# 📁 Repository File List

```text
Linked List
├── SLL.c
├── DLL.c
└── CLL.c

Queue
├── queue.c
├── circular_queue.c
├── priorityQueue.c
└── queue_linked_list.c

Search Algorithm
├── linear_search.c
├── binary_search.c
├── recursive_binary_search.c
└── binary_search(1).c

Sorting Algorithm
├── bubblesort.c
├── InsertionSort.c
├── quick_sort.c
└── selectionsort.c

Stack
├── stack.c
├── stack_linked_list.c
├── infix_to_postfix.c
└── postfix_eval.c
```

---

# 🧭 Learning Roadmap

```text
C Fundamentals
      |
      v
Pointers
      |
      v
Linked Lists
      |
      +-------> Stack
      |
      +-------> Queue
      |
      v
Searching
      |
      v
Sorting
      |
      v
Problem Solving
      |
      v
    🚀 DSA
```

## 🎯 Main Learning Goals

- Understand pointers and dynamic memory allocation
- Practice linked data structures
- Understand FIFO and LIFO
- Learn searching techniques
- Learn common sorting techniques
- Practice recursion
- Understand time complexity
- Build confidence in C programming

---

<div align="center">

### 🚀 Keep Coding • Keep Practicing • Keep Learning

**Data Structures & Algorithms in C**

</div>
