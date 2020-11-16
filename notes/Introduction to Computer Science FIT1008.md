---
attachments: [FIT1008 Practice Exam 2018_l.md, Heaps.md]
favorited: true
tags: [Uni Work]
title: Introduction to Computer Science FIT1008
created: '2020-10-23T06:51:55.274Z'
modified: '2020-11-12T07:25:54.036Z'
---

# Introduction to Computer Science FIT1008
## Recursion
### Recursive sorts
#### Divide and Conquer
split orignial problem into subproblems
solve each subproblem independently
combine solutions to yield final solution
 - Binary Search
     - a divide and conquer algorithm
     - divides the array by half in each iteration 
     - keep dividing until base case
 - Sorting
     - break the list down to a base case
     - dividing by half each iteration
     - Reach base case then merge back up
 
 ```
 def sort(array: ArrayR) -> None:
     if len(array) > 1:
         split(array, first_part, second_part)
         sor(first_part)
         sort(second_part)
         combine(first_part, second_part)
 ```
- Merge Sort
    - simple split 
    - complex combine
    - Split array into 2 halves 
    - combination merge the 2 halves into a sorted array
    - requires a temporary array 
    - can do in place sorting which would need temp array
    - Need:
        - Markers for part of the array 
          ```
    def merge_sort(array: ArrayR) -> None:
        tmp = ARrrayR(len(array))
        start = 0 
        end = len(array) -1
        merge_sort_auc(array, start, end, tmp)

    def merge_sort_aux(array: ArrayR, start: int, end: int, tmp: T) -> None
        if not start = end:
            mid = (start + end)//2
            merge_sort_aux(array, start, mid, tmp)
            merge_sort_aux(array, mid+1, end, tmp)
            
            merge_arrays(array, start, mid, end, tmp)
            
            for i in range(start, end+1):
                array[i] = tmp[i]
    
    def merge_arrays(a: ARrrayR, start: int, mid:int , end: int, tmp: T) -> None:
        ia = start
        ib = mid+1
        for k in range(start, end+1_:
            if ia> mid:
                tem[k] = a[ib]
                ib += 1
            elif ib > end:
                tmp[k] = a[ia]
                ia += 1
            elif a[ia] <= a[ib]:
                tmp[k] = a[ia]
                ia += 1
            else:
                tmp[k] = a[ib]
                ib += 1
          ```
        - Complexity
            - Worst Case: O(nlog(n))
            - Uses more space
          
- Quick Sort
    - complex split 
    - simple combine


