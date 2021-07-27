## Logarithms:

Log2(8): Log base 2 of 8, which is commonly used in Computer Science.

Log2 is the thing of cutting half.

## Heap: Offer us either the largest or the smallest number of a group of numbers.

It is a complete binary tree. Left to right, top to bottom. 

## Merge Sort: Drill down to base cases, push us back upwards and merge. 

How it works: We split the input until I reach a base case. One input is a sorted list.

One of the fatest sorting algorithms in CS. 

Merge Sort has two parts: the merge function, and the splitting function.

The splitting function can at maximum split the original input log(n) times (before getting to the base case of a 1 element array) and at each of the log(n) levels we will apply the merge function to the two halves that come back from our splitting calls.

The merge function runs in O(n) time.

Each stack/level has a merge sort and a splitting sort(Touch base return to stack and then merge)

## Merge 2 Sorted Lists

Put a pointer at the begining of each of these lists, and we are going to use a dummy head to build this new list. 

Dummyhead is needed for limitless problems because we don't need to worry about having an empty state on DH.

## Merge k Sorted Lists

Use min-heap to extract the smallest elements between these arrays.
