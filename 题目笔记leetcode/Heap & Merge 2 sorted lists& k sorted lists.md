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

## 优先队列 priority queue
优先队列是一个容器数据结构，使用具有全序关系的键（例如用数值表示的权重）来管理元素，以便快速访问容器中键值最小或最大的元素。

Python 优先队列 列表——手动维护有序队列：

使用有序列表能够快速识别并删除最小或最大的元素，缺点是向列表插入元素表是很慢的。

```python
q = []

q.append((2, 'code'))
q.append((1, 'eat'))
q.append((3, 'sleep'))

# 注意：每当添加新元素或调用bisect.insort()时，都要重新排序。
q.sort(reverse=True)

while q:
    next_item = q.pop()
    print(next_item)
# 结果：
#   (1, 'eat')
#   (2, 'code')
#   (3, 'sleep')
```
Python 优先队列 heapq——基于列表的二叉堆:

heapq是二叉堆，通常用普通列表实现，能在短时间内插入和获取最小的元素。具有O(log n)push和O(log n)pop

```python
import heapq
q = []
heapq.heappush(q, (2, 'code'))
heapq.heappush(q, (1, 'eat'))
heapq.heappush(q, (3, 'sleep'))
while q:
    next_item = heapq.heappop(q)
    print(next_item)

# 结果：
#   (1, 'eat')
#   (2, 'code')
#   (3, 'sleep')
```

heappush(heap, ele) :- This function is used to insert the element mentioned in its arguments into heap. The order is adjusted, so as heap structure is maintained.

heappop(heap) :- This function is used to remove and return the smallest element from heap. The order is adjusted, so as heap structure is maintained.

heapify(iterable) :- This function is used to convert the iterable into a heap data structure. i.e. in heap order.


