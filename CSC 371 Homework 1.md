[[CSC 371 Fri 09-23-22]]
Viet Minh Bui (Ethan Bui Bui)
vietbui20@augustana.edu

# Homework 1

Q1. You have a list of words. Can you sort them in lexicographical order? Write a code in java or python. Expected time complexity O(N^2) and expected space complexity O(1).
Sample input: [‘cat’, ‘pen’, ‘apple’, ‘act’, ‘beach’, ‘junk’, ‘root’]
Sample output: [‘act’, ’apple’, ‘beach’, ’cat’, ‘junk’, ‘pen’, ‘root’]
```python
sample_list =  ['cat', 'pen', 'apple', 'act', 'beach', 'junk', 'root']

def sort_lexico(a):
    temp = a[0]
    for i in range(0, len(a) - 2):
        for j in range(i+1, len(a) - 1):
            if a[j] < a[i]:
                temp = a[i]
                a[i] = a[j]
                a[j] = temp
    
sort_lexico(sample_list)
print(sample_list)
```

Q2. You have two different sorted arrays of numbers. How can you sort them together in a single array? Write a code in java or python. Include the time and spacy complexity of your algorithm at the end of the code inside a comment section.
Sample input: [2, 7, 8], [0, 5, 6]
Sample output: [0, 2, 5, 6, 7, 8]
```python
sampleArr1 = [2,7,8]
sampleArr2 = [0,5,6]

sampleArr1 = sampleArr1 + sampleArr2
def sort(a):
    temp = a[0]
    for i in range(0, len(a) - 2):
        for j in range(i+1, len(a) - 1):
            if a[j] < a[i]:
                temp = a[i]
                a[i] = a[j]
                a[j] = temp
    
sort(sampleArr1)
print(sampleArr1)
# time complexity O(N^2)
# Space Complexity O(1)
```

Q3. Can you recall the 3-sum problem that we have discussed in class? A 3-sum problem is where you have an array of numbers, and you have to find if there is any triplet in the array whose sum is 0. If you find any, you have to print ‘yes’. The complexity of the bruit force approach is O(N^3). Now can you reduce the complexity (less than N^3) of 3-sum problem by sorting the elements first? Implement your new approach and write the time complexity at the end of your code inside a comment section.
Sample input: [3, 6, 0, 8, -9]
Sample output: ‘yes’
```python
def heapify(arr, n, i):
    largest = i
    l = 2 * i + 1
    r = 2 * i + 2
    if l < n and arr[largest] < arr[l]:
        largest = l
    if r < n and arr[largest] < arr[r]:
        largest = r
    if largest != i:
        arr[i], arr[largest] = arr[largest], arr[i]
        heapify(arr, n, largest)

def heapSort(arr):
    n = len(arr)
    for i in range(n//2 - 1, -1, -1):
        heapify(arr, n, i)
    for i in range(n-1, 0,-1):
        arr[i], arr[0] = arr[0], arr[i] #swap
        heapify(arr, i, 0)

def find3Sum(arr):
    i = 0
    check = True
    while i < len(arr) and check:
        if i > 0 and arr[i] == arr[i-1]:
            i += 1
        a,b,c = i+1, len(arr)-1, i
        while a<b:
            if arr[a] + arr[b] == -arr[c]:
                print('yes')
                check = False
                break
            elif arr[a] + arr[b] < -arr[c]:
                a = a+1
            else:
                b = b-1
        i += 1
    if check:
        print('no')

arr = [3, 8, 0, 8, -9]
heapSort(arr)
find3Sum(arr)

#Time complexity O(nlogn) + O(n^2) = O(n^2)
# Space O(1)
```

Q4. Implement Selection, Insertion, Merge, and Quick sort in java or python. After you have coded your algorithms, you need check how long each sorting algorithm takes to run. You should test each algorithm on both random and sorted lists of sizes 20000, 40000, 90000, 200000 and 400000 in milliseconds. Finally, report your findings at the end of the code inside a comment section.
```python
'''
 Implement Selection, Insertion, Merge, and Quick sort 
 '''
from random import randrange
import time
import sys
sys.setrecursionlimit(400000)

# Initialize list of n values sorted and unsorted
# n will be change to 20000, 40000, 90000, 200000 and 400000
n = 20000
unsortedList = [randrange(0,n) for i in range(n)]
sortedList = [i for i in range(n)]

# print(unsortedList)

# Selection Sort
def selectionSort(arr):
    startTime = time.process_time()
    
    for i in range(len(arr)-1):
        for j in range(i+1, len(arr)):
            if arr[i] > arr[j]:
                arr[i], arr[j] = arr[j], arr[i]
    
    endTime = time.process_time()
    res = (endTime - startTime) * 1000
    
    print('Selection Sort CPU Execution time:', res, 'milliseconds')

# Insertion Sort
def insertionSort(arr):
    startTime = time.process_time()
    
    # Code goes Here
    for i in range(1, len(arr)):
        key = arr[i]
        j = i-1
        while j >=0 and key < arr[j]:
            arr[j+1] = arr[j]
            j -= 1
        arr[j+1] = key
    
    endTime = time.process_time()
    res = (endTime - startTime) * 1000
    print('Insertion Sort CPU Execution time:', res, 'milliseconds')

# Merge Sort
def merge(arr, l , m , r):
    # Code goes Here
    n1 = m - l +1
    n2 = r - m
    
    L = [0] * n1
    R = [0] * n2
    
    for i in range(n1):
        L[i] = arr[l+i]
    for j in range(n2):
        R[j] = arr[m+1+j]
    
    i,j = 0,0
    k = l
    while i < n1 and j < n2:
        if L[i] <= R[j]:
            arr[k] = L[i]
            i += 1
        else:
            arr[k] = R[j]
            j += 1
        k += 1
    while (i < n1):
        arr[k] = L[i]
        i += 1
        k += 1
    while (j < n2):
        arr[k] = R[j]
        j += 1
        k += 1
        
def mergeSort(arr, l, r):
    if l < r:
        m = l + int((r-l) / 2)
        
        mergeSort(arr, l, m)
        mergeSort(arr, m + 1, r)
        
        merge(arr, l, m, r)
    
def runMergeSort(arr):
    startTime = time.process_time()
    
    mergeSort(arr, 0, len(arr) - 1)
    
    endTime = time.process_time()
    res = (endTime - startTime) * 1000
    print('Merge Sort CPU Execution time:', res, 'milliseconds')


# Quick Sort
def partition(arr, low, high):
    pivot, i = arr[high], low - 1
    
    for j in range(low, high):
        if arr[j] <= pivot:
            i += 1
            arr[i], arr[j] = arr[j], arr[i]
    arr[i+1], arr[high] = arr[high], arr[i+1]
    return i+1
        
def quickSort(arr, low, high):
    if low < high:
        pi = partition(arr, low, high)
        quickSort(arr, low, pi - 1)
        quickSort(arr, pi + 1, high)
        
def runQuickSort(arr):
    startTime = time.process_time()
    
    quickSort(arr, 0, len(arr) - 1)
    
    endTime = time.process_time()
    res = (endTime - startTime) * 1000
    print('Quick Sort CPU Execution time:', res, 'milliseconds')


# uncomment each section bellow to see the time
# selectionSort(unsortedList)
# insertionSort(unsortedList)
# runMergeSort(unsortedList)
# runQuickSort(unsortedList)

# selectionSort(sortedList)
# insertionSort(sortedList)
# runMergeSort(sortedList)
# runQuickSort(sortedList)

```

Runtime in milliseconds
Using CPU runtime I have collected the data below:
*** means it takes too long to run on my computer
|list size of n|type of list | Selection      | Insertion| Merge| Quick|
|--------|-------------------|----------------|----------|------|------|
| 20000  | Unsorted (Random) | 19166 -> 19225 | 13442 -> 13658| 92 -> 95| 42.9 -> 47|
| 20000  | Sorted            | 12838 -> 12885 | 3     | 82 -> 85 | 30781|
| 40000  | Unsorted          | 78528 | 55277  | 198 -> 199   | 92 -> 94 |
| 40000  | Sorted            | 52381       | 6.4   |    176 -> 179| *** |
| 90000  | Unsorted          | 400149      | 292724    | 499      | 238 |
| 90000  | Sorted            | 238500      | 15.6      | 531.25   | *** |
| 200000 | Unsorted          | ***         | ***       | 1139     | 598 | 
| 200000 | Sorted            | 232859.375  | 15.625    | 546.875  | *** |
| 400000 | Unsorted          | ***         | ***       | 2506    | 1229 |
| 400000 | Sorted            | ***         | ***       | 2265    | ***  |
![[Pasted image 20220924182147.png]]

 From the table, selection is the one that would take up the most in runtime for both sorted and unsorted list. What I find interesting is the runtime of quicksort for sorted list. Quick sort is the fastest in runtime with unsorted list in any cases of num list n but when they got introduced the 40K and above sorted list, the program takes much much longer than the other function to the point my computer could not handle the wait time and have to restart the "kernel". For sorted list of n Insertion sort out performs other algorithms, this make sense because its best case (in this case a sorted list) has runtime O(N). Merge sort in the other hand would alway guarantee the output for the timed in my program because best, average, and worst case for merge is always O(nlogn) 