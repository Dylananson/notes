---
tags: [FIT1008]
title: SAMPLE EXAM 2
created: '2020-11-12T05:54:43.898Z'
modified: '2020-11-12T07:54:04.754Z'
---

# SAMPLE EXAM 2
## Question 1
f none of the above


**Marks: 0**
## QUestion 2
D
**Marks: 3** 
## Question 3
C
**Marks: 1,5**
## Question 4
This is not needed becuase in the MIPS because the equation to find the index location of the ith location should be i*4 +4, in the code shown the +4 operation is not used thus this is the same as doing i*4 which is 1 index lower than i.

**Marks: 1**
## Question 5
This algorithm is correct
The invariant that ensures correctness is that the_array[q] >= the_array[p] before starting the while loop q<=P
**Marks:2**
## Question 6
~~~
def partition(self, array, start, end):
    pivot = end
    
~~~
**Marks:0**
## Question 7
~~~
def __contains__(self, item):
    if is_empty:
        return false
    else:
        for i in range(self.count):
            if self.array[i] == item:
                return True
    return False
~~~

**Marks: 4**
## Question 8 
~~~
def remove_first(self):
    assert is_empty == False
    self.count -= 1
    for i in range(self.count):
        self.array[i] = self.array[i+1]


~~~
**Marks: 6**
## Question 9
 to append you would push to stack.left, then to pop you would move each to the stack.right and pop elements, then you would move them back to stack.left before pushing again.

**Marks:4**
## Question 10


Option D, the first while loop will change the head while the item is negative essentially removing the negatives at the begining of the list. Then the second while loop will delete each node that is negative by changing the previous link such that the node that is negative is skipped and therefore removed.

**Marks: 7**

## Question 11
100

**Marks: 2**
## Question 12

16
**Marks: 2**

## Question 13

4
**Marks: 0**
## Question 14

16
** Marks: 0**

## Question 15
worst case is log(y), because y will keep recusring until y//2 = 1, which is log(y), each other operation is constant time

**Marks:3**
## Question 16
#1 return 0
#2 low_sum = sum_leq_aux(current.left, item)
#3 return item
#4 elif tree.right is None
#5 return current.item

**Marks: 1**
## Question 17
Worst case is o(n) this occurs when the tree is unbalanced.

**Marks:2**
## Question 18
#1 return None
#2 acc = sum_def_partents_tail_aux(node.left, value, acc) + sum_parents_tail_aux(node.right, value, acc)
#3 return acc

**Marks 1**

## Question 19
~~~
def find_kth_smallest(alist, k):
    mx = MaxHeap()
    n = len(alist)
    for i in range(n):
        mx.add(alist[i])
    for _ in range(n- k):
        res = mx.get_max()
    return res
~~~
**Marks: 7**

## Question 20

It will run normally and output a is not equal to b

mystery2(3,4) will try to return mystert1(3,4), which will raise assertionError 3<=4 is False, the assertion error is then caught by the orginal main call which will except the assertion error and print(e)

**MARks :4**

### ACHEIVED MARKS: 50.5

### AVALIABLE MARKS: 91
### GRADE 55%

