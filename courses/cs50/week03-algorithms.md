# Week 03 — Algorithms

status: [ in progress ]

---

## Overview

how to search and sort data efficiently.
not whether something works, but how fast it works, and how that scales.

---

## Key Concepts

- linear search
- binary search
- bubble sort
- selection sort
- big O notation (asymptotic notation) (time complexity)
- command-line arguments

---

## Mental Models

- linear search: check every until found (or not)
- binary search: only works on sorted (cut problem in half) (phonebook example)
- bubble sort: repeatedly swap adjacent that are out of order--largest values "bubble up"
- selection sort: find smallest, move to front, repeat.
- big O: how does the work scale as input grows? O(n) / O(log n) / O(n^2)

---

## Code Patterns

**linear search:**
```c
for (int i = 0; i < n; i++)
{
    if (arr[i] == target)
    {
        return i;
    }
}
return -1;
```

**binary search:**
```c
int low = 0, high = n - 1;
while (low <= high)
{
    int mid = (low + high) / 2;
    if (arr[mid] == target)
        return mid;
    else if (arr[mid] < target)
        low = mid + 1;
    else
        high = mid - 1;
}
return -1;
```

**command-line arguments:**
```c
int main(int argc, char *argv[])
{
    if (argc == 2)
    {
        printf("Hello, %s\n", argv[1]);
    }
}
```

**bubble sort:**
```c
// ex
```

**selection sort:**
```c
// ex
```

---

## Common Mistakes

- binary search: using on unsorted, or off-by-one in search bounds
- 


---

## Connections

- algorithms → arrays (week 02): search and sort operate on arrays
- 

---

## TL;DR

- linear search simple but slow to scale
- binary saerch fast but needs sorted
- sorting has cost--sometimes worth, sometimes not
- 

---

## Exercises

### Completed
1. { problem name }
2. { problem name }

### Challenges
1. { challenge 1 }
2. { challenge 2 }

### Notes on Solutions
- { insight }
- { pattern noticed }

---

## Questions

1. { question }
2. { question }

---

## Personal Notes

The lecture spends a lot of time on search and sort via the phonebook analogy — more time than it probably needs to, given that the concepts are fairly intuitive once stated. Command-line arguments (argc, argv) got noticeably less coverage but were harder to grasp initially. The lecture pacing doesn't map cleanly onto actual difficulty.
