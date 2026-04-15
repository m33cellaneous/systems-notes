# Week 03 — Algorithms

status: [ complete ]

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
- merge sort
- recursion (base case + recursive case)
- dot notation for structs (```people[i].name```)
- big O, omega (Ω), theta (Θ) — worst, best, average case (asymptotic notation) 
- command-line arguments

---

## Mental Models

- linear search: check every until found (or not)
- binary search: only works on sorted (cut problem in half) (phonebook example)
- bubble sort: repeatedly swap adjacent that are out of order--largest values "bubble up"
- selection sort: find smallest, move to front, repeat. every pass sitll scans full list
- merge sort: split array in half recursively, sort each half, merge; faster but uses extra memory for temp arrays
- recursion: a function that calls itself; base case must come first, or it runs forever
- dot notation: access a field inside a struct; ```people[i].name``` means "the name field of the i-th person"
- big O/omega/theta: (worst/best/average case): how does the work scale as input grows? O(n) / O(log n) / O(n^2)

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

**dot notation:**
```c
typedef struct
{
    string name;
    string number;
}
person;

person people[2];
printf("%s\n", people[0].name);
```

**bubble sort:**
```c
for (int i = 0; i < n - 1; i++)
{
    for (int j = 0; j < n - i - 1; j++)
    {
        if (arr[j] > arr[j + 1])
        {
            int tmp = arr[j];
            arr[j] = arr[j + 1];
            arr[j + 1] = tmp;
        }
    }
}
```

**selection sort:**
```c
for (int i = 0; i < n - 1; i++)
{
    int min = i;
    for (int j = i + 1; j < n; j++)
    {
        if (arr[j] < arr[min])
            min = j;
    }
    int tmp = arr[min];
    arr[min] = arr[i];
    arr[i] = tmp;
}
```

**recursion structure:**
```c
void draw(int n)
{
    if (n <= 0)
        return;
    draw(n-1);
for (int i = 0; i < n; i++)
        printf("#");
printf("\n");
}
```

---

## Common Mistakes

- binary search: using on unsorted, or off-by-one in search bounds
- missing base case in recursion, or placing after recursive call
- assuming merge sort is always the right choice. it's faster (O(n log n)) but allocates extra memory.


---

## Connections

- algorithms → arrays (week 02): search and sort operate on arrays

---

## TL;DR

- linear search simple but slow to scale
- binary saerch fast but needs sorted
- sorting has cost--sometimes worth, sometimes not
- recursion needs base case or it goes forever
- dot notaton accesses struct fields

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

lecture spends a disproportionate amount of time on search and sort; multiple demonstrations of each, with extended analogies; while omega and theta notation get roughly a minute between them. given that Ω and Θ complete the picture that O alone doesn't, the imbalance is odd.

same issue with command-line arguments: minimal screen time, but harder to grasp in practice than anything in the sort demos. worth independent study: argc and argv keeps showing up.

selection sort is visibly inefficient--every pass still scans the full remaining list even if data is nearly sorted. bubble sort at least has a best-case improvement (Ω(n) if already sorted); selection sort doesn't.

merge sort: obvious question is why not always use it. MEMORY - it needs extra space proportional to the input size to hold the split arrays during merging. matters for large datasets.
