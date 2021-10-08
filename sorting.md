# Sorting

## Selection Sort

1. Algorithm
```py
def selectionSort(self, arr,n):
    for i in range(n):
        # find minimum from array
        mini = i 
        for index in range(mini+1, len(arr)):
            if arr[mini] > arr[index]:
                mini = index
        # swap minimum with the current index
        arr[mini],arr[i] = arr[i],arr[mini]
```
2. Complexities 
```
Time Complexity: O(n2) as there are two nested loops.
Auxiliary Space: O(1) 
Sorting In Place: Yes
The good thing about selection sort is it never makes more than O(n) swaps and can be useful when memory write is a costly operation.
```
3. It is not stable sorting. 
   

## Bubble Sort

1. Algorithm
```py
 for i in range(n):
    j = n-1
    while j > i:
        if arr[j] < arr[j-1]:
            arr[j], arr[j-1] = arr[j-1], arr[j]
        j -= 1
// IF no two elements were swapped by inner loop, then break. This reduces complexitiy to o(n) for sorted array
```
2. Complexities
```
Worst and Average Case Time Complexity: O(n*n). Worst case occurs when array is reverse sorted.
Best Case Time Complexity: O(n). Best case occurs when array is already sorted.
Auxiliary Space: O(1)
Sorting In Place: Yes
Stable: Yes
```


## Insert Sort

1. Algorithm
```py
for i in range(n):
    j = i
    # shift untill precessor element is bigger
    while j > 0 and alist[j] < alist[j-1]:
        alist[j],alist[j-1] = alist[j-1],alist[j]
        j -= 1
```
2. Complexities
```
Time Complexity: O(n^2) 
Auxiliary Space: O(1)
Boundary Cases: Insertion sort takes maximum time to sort if elements are sorted in reverse order. And it takes minimum time (Order of n) when elements are already sorted.
Sorting In Place: Yes
Stable: Yes
Uses: Insertion sort is used when number of elements is small. It can also be useful when input array is almost sorted, only few elements are misplaced in complete big array.
```


## Merge Sort

1. Algorithm
```py
def merge(self,arr, l, m, r): 
    left=[arr[i] for i in range(l,m+1)]
    right = [arr[i] for i in range(m+1,r+1)]

    arrPtr = l
    leftPtr = 0
    rightPtr = 0
    while leftPtr < len(left) and rightPtr < len(right):
        if left[leftPtr] < right[rightPtr]:
            arr[arrPtr] = left[leftPtr]
            leftPtr += 1
        else:
            arr[arrPtr] = right[rightPtr]
            rightPtr += 1
        arrPtr += 1
    
    while leftPtr < len(left):
        arr[arrPtr] = left[leftPtr]
        leftPtr += 1
        arrPtr += 1
    
    while rightPtr < len(right):
        arr[arrPtr] = right[rightPtr]
        rightPtr += 1
        arrPtr += 1
    
def mergeSort(self,arr, l, r):
    if  l<r:
        mid = (l+r)//2
        self.mergeSort(arr,l,mid)
        self.mergeSort(arr,mid+1,r)
        self.merge(arr,l,mid,r)
```
2. Complexities
```
Time complexity of Merge Sort is  θ(nLogn) in all 3 cases (worst, average and best
Auxiliary Space: O(n)
Algorithmic Paradigm: Divide and Conquer
Sorting In Place: No in a typical implementation
Stable: Yes
```
3. Uses
```
Merge Sort is useful for sorting linked lists in O(nLogn) time
```
4. Drawbacks:
```
Slower comparative to the other sort algorithms for smaller tasks.
Merge sort algorithm requires an additional memory space of 0(n) for the temporary array.
It goes through the whole process even if the array is sorted.
```


## Quick Sort

1. Algorithm
```py
def quickSort(self,arr,low,high):
        if low >= high: return 
        
        pivot = high
        strt = low
        end = high-1
        
        while strt <= end:
            if arr[strt] >= arr[pivot] and arr[end] <= arr[pivot]:
                arr[strt],arr[end] = arr[end], arr[strt]
                strt += 1
                end -= 1
            else:
                if arr[strt] < arr[pivot]:
                    strt += 1
                    
                if arr[end] > arr[pivot]:
                    end -= 1
        arr[strt],arr[pivot] = arr[pivot],arr[strt] 
        self.quickSort(arr,low,strt-1)
        self.quickSort(arr,strt+1,high)
   
```
2. Complexities
```

```

## Counting sort
1. Algorithm
```py
    # 1. store count of all elements in count_array
    # 2. Create new array , replicate the element (index of count array) X times as in count array
```
2.Complexties
```
Time Complexity: O(n+k) where n is the number of elements in input array and k is the range of input. 
Auxiliary Space: O(n+k)
```
3. Points to remeber
```
> Can be extended for negative numbers as well
> Counting sort is efficient if the range of input data is not significantly greater than the number of objects to be sorted. Consider the situation where the input sequence is between range 1 to 10K and the data is 10, 5, 10K, 5K. 
> It is not a comparison based sorting. It running time complexity is O(n) with space proportional to the range of data. 
```