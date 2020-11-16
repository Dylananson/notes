---
tags: [FIT1008]
title: 2019 sem 1 Exam
created: '2020-11-13T21:53:29.302Z'
modified: '2020-11-13T23:55:50.141Z'
---

# 2019 sem 1 Exam
## Question 1
### def func(n)
~~~
.text
func:
#save $ra
sw $ra, ($sp)
#save $fp
sw $fp, 4($sp)
copy $sp to $fp
addi $fp, $sp, 0
allocate local variables
addi $sp, $sp, -4
#result at 4($fp)
~~~

### if n <= 0 
~~~
#load in n to $t0
lw $t0, 8($fp)
#if 0 < n do if else branch

slt $t1, $0, $t0
beq $t1, $0, else
~~~
### result = 0

~~~
#result = 0 
addi $t2, $0, 0 
sw $t2, 4($sp)
~~~

### else

~~~
else:
~~~

### result = 4*n+func(n-1)

~~~
#calc func(n-1)
#pass arguments on stack

lw $t0, 8($fp)
addi $t0, $0, -1 #$t0 = n-1

#store $t0 as argument.
addi $sp, $sp, -8
sw $t0, 8($sp) 

jal func(n-1)

#clear arguments off stack
addi $sp, $sp, 4


#$v0 = func(n-1)
add $t0, $v0, $0

#calc 4*n
lw $t1, 8($fp)
sll $t1, 2

#calc 4*n+func(n-1)
add $t2, $t1, $t0
~~~


### return result

~~~
#set $v0 to return

#clear locals
addi $sp, $sp, 4

# restor fp and rs
add $fp, 4($sp), $0
add $ra, ($sp), $0
addi $sp $sp, 8

jr $ra

~~~

## question 1 a


for stack memory N is 16, each of the following is 4 bytes: ra,fp,n,result
the recursive version uses more becuase the stack is increase everytime recusion is called.
for stack memory of recursive function N is dependant on the value n. it would be 16*n, as the function would recur n times, and each uses 16 bytes.

## Question 2
### Part A
1
### Part B
2
### Part C
2
### Part D
3
### Part E
6
### Part F
2
### Part G
10
### Part H
9
### Part I
1
### Part J
0

## Question 3
x=1: 1
x=2: 1
x=3: 2

x=4: 1
x=5: 2
x=6: 2
x=7: 3

x=8: 1
x=9: 2
y=10: 2
y=11: 3
y=12: 2
y=13: 3
y=14: 3
x=15: 4

x=16: 1
x=17: 2
x=18: 2
x=19: 3
x=20: 2
x=21: 3
x=22: 3
x=23: 4
x=24: 2
x=25: 3
x=26: 3
x=27: 4
x=28: 3
x=29: 4
x=30: 4
x=31: 5

x=32:1

mystery shows the number of 1s x has when changed to binary

time complexity: O(log(x)) as it divides itself by 2 each recursion which creates a log2(x) recursive calls

x=1: 1
x=2: 1
x=3: 3
x=4: 2
x=7: 6
x=8: 2

x=15: 6

enigma calculates something

time complexity: O((log(x))^2), the mystert function is log(x), which means y=log(x) is log(x) time, y is reduced to log(y)


## Question 4
~~~
def find_intervals(list):
    seperators = [0]
    start = 0 
    end = 1
    while end < len(list):
        while list[start] < list[end]:
            end += 1
        seperators.append(end)
        start = end
        end += 1
    seperators.append(end+1)

    return seperators
~~~

The worst case is O(n), happens when there are no sorted group, each iteration end increases, end will stop increasing when it is the length of the list, thus the loop will run at most n times.

~~~
def natural_merge(l):
    intervals = find_intervals(l)
    while len(intervals) > 2:
        merge(l, intervals[0], intervals[1], intervals[2])
        l.pop(1)
~~~
The worst case complexity of natural merge is O(n^2) where n is the number of elements in l. THe find intervals takes n time, and the while loop is n run n times, and the merge can run n times given the intervals is every index in the list. THis happens when the list has no sorted elements.



Merge sort is a good example of a better sorting algorithm that uses similar ideas to this, instead of splitting the list into sorted sublists, it simply splits the list into sublists of 1, and then uses merge n times.

## Question 5
A


