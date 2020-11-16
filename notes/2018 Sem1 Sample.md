---
tags: [FIT1008]
title: 2018 Sem1 Sample
created: '2020-11-14T21:10:43.006Z'
modified: '2020-11-14T21:46:05.528Z'
---

# 2018 Sem1 Sample
## Question 1

~~~
#if n >= 0
lw $t0, 8($fp)
slt $t1, $0, $t0
bne $t1, $0, else

addi $sp, $sp, -4
sw $t0, 4($sp)

jal fact

addi $sp, $sp, 4
addi $t0, $v0, 0

sw $t0, -4($fp)

j endif

else:

lw $t0, 8($fp)
addi $t1, $0, 7
div $t0, $t1
mfhi $t2

sw $t2, -4($fp)

~~~

## Question 2

~~~
def __str__(self):
    res = '['
    for i in range(self.count):
        item = self.array[(i+self.front) % len(self.array)]
        res += str(item)+','
    res += ']'

    return res
~~~

~~~
def __resize__(self):
      new_size = len(self.array)
      new_arr = [None]*new_size
      for i in range(self.count):
          new_arr[i] = self.array[(i+self.front) % len(self.array)]
      self.front = 0
      self.end = self.count -1
      self.array = new_array[i]

~~~


The best case complexity for appending to a queue with n elements is O(1), simply add an element to an array is a constant time operation, happens when the array is not full. The worst case complexity is when the array is full and resizing is needed, this is O(n) time as each element must be copied to a new array.


## Question 3

This method does not work. 
The iterator will only change the value next to the value specified. For example with the list given -1,2,3,-4,5,-6 the first element -1 is never changed to 0 as at the beggining of the iter the item being looked at is -1, however next(it) is called making the item 2, therefore -1 is skipped.


~~~
def zeroed(a_list, it=None):
    it = iter(a_list)
    if not has_next(it):
        return
    if item < 0:
        set_item(it, 0)
    next(it)
    zeroed(a_list, it)


~~~

## Question 4
Merge Sort









