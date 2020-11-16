---
tags: [FIT1008, Sample Exam]
title: FIT1008 Practice Exam 2018_l
created: '2020-11-11T23:36:13.659Z'
modified: '2020-11-12T01:56:21.185Z'
---

# FIT1008 Practice Exam 2018_l
## Question 1
### Python Code
def my_function(n, m)
### Mips Translation
* Save $ra and fp on stack
addi $sp, $sp, -8
sw $ra, 0( $sp)
sw $fp, 4( $sp)
* copy sp to fp
add $fp, $sp, $0
* allocate local variables on stack

* if n == 0
lw $t0, 8( $fp) $t0 = n
bne $t0, $0, else

* set $v0 to return value
lw $t1, 12( $fp) $t1 = m
add $v0, $t1, $0

* restore fp and ra off stack
lw $fp, 4( $sp)
lw $ra, 0( $sp)
addi $sp, $sp, 8

* return to caller
jr $ra

.else 
* m//n
lw $t0, 8( $fp) $t0 = n
lw $t1, 12( $fp) $t1 = m
div $t1, $t0
mfhi $t2 WRONG MFLO

* set $v0 to return value
add $v0, $t2, $0

* restore fp and ra off stack
lw $fp, 4( $sp)
lw $ra 0( $sp)
addi $sp, $sp, 8

* return to caller
jr $ra


**MARKS: 9**
## Question 2

### Part A

~~~
def __resize__(self):
    #double size of underlying array

    curr_size = len(self.array)
    new_size = 2*curr_size
    new_arr == build_array(new_size)

    #if neccessary re arrange values of instance variables
    for i in range(self.front, len(self.array)):
        new_arr[i] = self.array[i]%self.len(array)
    for i in range(self.rear):
        new_arr[i + len(self.array)] = self.array[i]%self.len(array)

    self.array = new_arr
~~~

**Marks: 2**
### Part B
~~~
def serve(self):
    if self.is_empty:
        raise Exception()
    item = self.array[self.front]
    self.front += 1
    self.count -= 1
    return item

~~~
**Marks: 2**
### Part C 

~~~
def __str__(self):
    res = '['
    if self.is_empty:
        return '[]'
    else: 
      for i in range(self.front, len(self.array)):
          item = str(self.array[i])
          if i == self.rear:
              res += item
          else:
              res += item + ','
          
      for i in range(self.rear, self.front):
          item = str(self.array[i])
          if i == self.rear:
              res += item + ']'
          else:
              res += item + ','
~~~
**Mark: 2**

### Part D

Best case for appending to queue: 
* Occurs when the queue is not Full
* O(1)
* Example: if there is a free slot in the array after self.rear, we simply increase rear and add in the element which is constant time
Worst Case for appending to queue:
* Occurs when resize is required
* O(n)
* Example: if the array is full we must resize the array copying each element to a new array, this is n time as we must copy each element.

**Marks: 2** 
## Question 3
### Part A
* Not stable means that the sort will potentially move elements that are the same to a different order.
* 
**Marks: 0**
### Part B
* Merge Sort
* merge sort algorithm split the array using recursion and rebuild, the splitting process creates a tree of log(n) height
and the merging process will take n operations, this create n*log(n) time for worst and best case

**Marks: 1.5**

### Part C
* Heap Sort 
* not sure
**Marks: 0**

## Question 4
* Ranking:
  * C
  * B
  * A
* C:
  * Advantages:
    * has unique key depending on values entered, has to have the same multiplication resutl for collision to occur
  * Disadvantages:
    * Depending on sparsity of data, collisions can occur when the multiplication result is the same
    * for instance [4,2] = [2,2,2]
* B:
  * Advantages:
    * key depending on values entered
    * could create unique hash_key if min is different
  * Disadvantages:
    * Potentially lots of collisions as if min value is the same then collision will occur,
    * Not as good as C as only there is a greater chance of collision as only 1 value must be the same, i.e the min, whereas C has to have a combination of values equal the same upon multiplication
* A:
  * Advantages:
    * Collisions occur as a function of the table size, so increasing table size reduces chance of collision
  * Disadvantages:
    * The hashed_key are not unique to key vallues, so impossible to know what is stored where,

**Marks: 7**
## Question 5
### Part A:
| 0 | 7 |
| --|---|
| 1 |   |
|---|---|
| 2 |   |
|---|---|
| 3 | 3 |
|---|---|
| 4 | 10|
|---|---|
| 5 | 5 |
|---|---|
| 6 | 4 |
|---|---|
| 7 | 11|
|---|---|

**Marks: 3.5**

### Part B:
IDk? 6?
 **Marks: 0**

## Question 6
### Part A
~~~
def copy(self):
    new_list = List()
    new_list.head = Node(item = self.head.item)
    node = self.head
    while node not None:
        node.link = Node(item = node.item)
    return new_list
~~~ 
**Marks: 3**

### Part B
~~~
def __next__(self):
    return self.current.link

def __iter__(self):
    return MyLinkedListIterator(self.head)
~~~
**Marks: 0**

## Question 7
~~~
list = heap_sort(list)
res = []
for i in range(len(list) - 1):
    if list[i] == list[i+1]:
      if res[len(res)-1] != list[i]:
          res.append(list[i])
return res
~~~
**Marks: 4**
## Question 8

### Part A
~~~
serach for key1, 
search for key2
def LCA_aux(self, current, key1, key2):


~~~
**Marks: 0**

### Part B

~~~
def traverse_preorder(self):
    return traverse_preorder_aux([], self.root)
def traverse_preorder_aux(self, res=None, current):
    if current == None:
        return res
    
    res.append(current)
    res += traverse_preorder_aux(res, self.left)
    res += traverse_preorder_aux(res, self.right)

~~~
**Marks: 1,5**
### Part C

The best case and worst case is the same, due to having to print each element in the tree, this makes the best and worst case the size of the tree. Each element must be added to the list to print thus best and worst is O(n) where n is the number of nodes in the tree.

**Marks: 2**

## Question 9

### Part A
~~~
def swap_children(self):
    return swap_children_aux()

def swap_children_aux(self, current):

    if current.left == None:
        swap(current)
    #swap left and right children
    swap_children(current.left)
    swap_children(current.right)
    #check if breaks heap property
    #sink the root to fix heap property

~~~

**MARKS: 0**
## Question 10
### Part A
* 1: Green
* 2: Red
* 3: Left
* 4: Front
* 5: 6
* 6: 4
* 7: 2400
* 8: 3

**Marks: 7**



# TOTAL MARKS 46.5

# AVALIABLE MARKS: 91

# GRADE: 51%

HEAPS
TREES
SORTING , STABLE, HEAPSORT, BUBBLESORT

