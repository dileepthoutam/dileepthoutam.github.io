- [Binary Search](#binary-search)
- [Linear Search](#linear-search)
- [Bubble Sort](#bubble-sort)
- [Selection Sort](#selection-sort)
- [Insertion Sort](#insertion-sort)

### Binary Search

Binary search is a divide and conquer algorithm. It's a very efficient algorithm with time complexity *O(logn)*.

```python
def binary_search(arr, target):
    start = 0
    end = len(arr) - 1
    while start <= end:
        mid = start + (end - start) // 2
        if target == arr[mid]:
            return mid
        elif target < arr[mid]:
            end = mid - 1
        else:
            start = mid + 1
    return -1
```

### Linear Search

Linear search is a straight forward algorithm where you iterate through every element until you find what you want.

```python
def linear_search(arr, target):
    for x in arr:
        if x == target:
            return True
    return False
```

### Bubble Sort

Bubble sort is a simple sorting algorithm. You swap the adjacent elements until you get the sorted array. 
Ofcourse it's expensive. Time complexity is *O(logn)*.

```python
def bubble_sort(arr):
    for i in range(len(arr)):
        for j in range(len(arr) - i - 1):
            if arr[j] > arr[j + 1]:
                arr[j], arr[j + 1] = arr[j + 1], arr[j]
```

### Selection Sort

Selection sort algorithm is a bit different where first you find out the minimum element and then swap it 
with the current element. Time complexity is *O(logn)*.

```python
def selection_sort(arr):
    for i in range(len(arr)):
        min_index = i
        for j in range(i + 1, len(arr)):
            if arr[j] < arr[min_index]:
                min_index = j
        arr[i], arr[min_index] = arr[min_index], arr[i]
```

### Insertion Sort

Insertion sort is a bit different that bubble sort and selection sort. You iterate through the array, 
you swap out minimum element until it's sorted.

```python
def insertion_sort(arr):
    for i in range(1, len(arr)):
        current = arr[i]
        j = i - 1
        while j >= 0 and arr[j] > current:
            arr[j + 1] = arr[j]
            j -= 1
        arr[j + 1] = current
```

