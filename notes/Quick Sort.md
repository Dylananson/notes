---
tags: [Algorithm, FIT1008, Sorting]
title: Quick Sort
created: '2020-11-16T00:04:51.971Z'
modified: '2020-11-16T00:14:14.295Z'
---

# Quick Sort
~~~
def quick_sort(self, array):
    start = 0
    end = len(array) -1
    res = quick_sort_aux(array, start, end)

def quick_sort_aux(self, array, start, end):
    boundary = partition(array, start, end):
    quick_sort_aux(array, start, boundary)
    quick_sort_aux(array, boundary+1, end)

def partition(self, array, start, end):
    pivot_i = (start+end)//2
    pivot_val = array[mid]

    swap(array, start, pivot_i)

    boundary = start
    
    for k in range(start, end):
        if array[k] < pivot_val:
            boundary += 1
            swap(array, k, boundary)

    swap(array, start, boundary)
    return boundary
~~~


