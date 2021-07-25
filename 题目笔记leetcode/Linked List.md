## How to reverse singly linked list 

Initialize pointers:

1. Prev pointer: In Singly list, you can't get the node before current one.

2. Cur pointer: To say where we are at

3. Next pointer: If we change cur to next value, we are going to lose next pointer in the interation.

```python
'''
Here is the implementation for the linked list and corresponding algorithm
'''

class Node: # Represents an individual element in linked list
    def __init__(self, data=None, next=None ): # None is the default value of data and next
        self.data  = data
        self.next = next

class LinkedList:
    def __init__(self):
        self.head = None

    def insert_at_begining(self,data):
        node = Node(data, self.head) #Initialize a node element/self.head对应着NEXT
        self.head = node

    def print(self):
        if self.head is None:
            print("Linked list is empty")
            return
        itr = self.head
        llstr= ''
        while itr:
            llstr += str(itr.data) + '-->'
            itr = itr.next
        print(llstr)

    def insert_at_end(self,data):
        if self.head is None:
            self.head = Node(data,None)
            return
        itr = self.head
        while itr.next: # If itr.next not null, means still not end
            itr = itr.next
        itr.next = Node(data,None)

    def insert_values(self, data_list):
        self.head = None
        for data in data_list:
            self.insert_at_end(data)

    def reverse_list(self):
        prev = None
        cur = self.head
        while cur:
            next = cur.next
            cur.next = prev
            prev = cur
            cur = next
        return prev


if __name__ == '__main__':
    ll = LinkedList()
    ll.insert_values([1,2,3,4,5,6])
    ll.print()
    ll.reverse_list()
    ll.print()

```
