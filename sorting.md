o
# Sorting

## Selection Sort

1. Algorithm
```
-> for i in range array
-> -> for j in range (i+1,array)
-> -> -> find min element from j to len array
-> -> swap array[i] with array[j]
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
```
for i in range array
	for j in range (i+1,array)
		if array[i] < array[j] 
			swap array[i] array[j]
            
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
```
for i in range array
	j = i
	while j > 0 and array[j] < array[j-1]:
		swap(array[j], array[j-1])
                j =- 1
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
```
mergesort(arr,strt,end):
	return if strt >= end
	mid = strt+end /2 
	recurse mergesort(arr, strt,mid)
	recurse mergesort(arr,mid+1,end)
	merge(strt,mid,mid+1,end)

merge(strt,mid,mid+1,end):
	create leftArr from strt to mid
	create rightArr from mid+1 to end

	currArrIndex = strt

	add smallest from left*right arr to strt
	add left array if left
	add right array if left
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
```

```
2. Complexities
```

```
