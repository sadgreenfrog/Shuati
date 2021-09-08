String common usage:

1. 
sorted(list,key=f)会返回一个排列好的序列，排列依据的键值是f函数处理list中每个元素后的输出
f函数生成键值
split:

split the string into list of strings: Input: "Geeks for Geeks" string.split(' ')

Output:['Geeks', 'for', 'Geeks']

join: '_'.join(list), Input: ['Geeks', 'for', 'Geeks'] Output: Geeks-for-Geeks

2. Count of a tring

Use count of string

count() Returns the number of times a specified value occurs in a string

Use counter
A counter is a container that stores elements as dictionary keys, and their counts are stored as dictionary values.

The get() method returns the value of the item with the specified key.

3. Sort the hashmap by value/key


import operator
x = {1: 2, 3: 4, 4: 3, 2: 1, 0: 0}
sorted_x = sorted(x.items(), key=operator.itemgetter(0))

import operator
x = {1: 2, 3: 4, 4: 3, 2: 1, 0: 0}
sorted_x = sorted(x.items(), key=operator.itemgetter(1))
