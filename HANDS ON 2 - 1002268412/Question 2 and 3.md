Hands On 2
Chandrasekar Vasan
1002268412

Argue selection sort correctness


In order to demonstrate that it sorts correctly, we must solve two key issues: 

Partial Correctness: The array will undoubtedly be sorted if the method succeeds. 

Termination: After a finite number of steps, the algorithm comes to an end.  

Partial Correctness: 

The resultant array will be sorted if the method terminates 

Invariant: 

The subarray "arr[0:i]" is sorted and holds the array's smallest "i" elements for each iteration of the outer loop. 

Proof of Partial Correctness: 

We need to show that the array is sorted after it is finished in order to prove partial correctness. An invariant, or a condition that holds true during the algorithm's execution, is used to do this: 

Invariant: The subarray arr[0:i] (from the array's beginning to position i-1) is sorted at the start of each outer loop iteration, containing the smallest i entries in the array.  

Proof by Induction: 

Base Case: The subarray arr[0:0] is empty, therefore it can be easily sorted before any iterations (i.e., when i = 0). 

Inductive Step

Assumption: Assume that the subarray arr[0:k] is sorted and contains the smallest k elements after k iterations (where k < n). 

Action: The method finds the smallest element in the unsorted section (arr[k:n]) and assigns it to index k on the k-th iteration. 

Result: Following the placement of this smallest element, the smallest k+1 elements are ordered in the subarray arr[0:k+1]. 

By induction, this invariant ensures that after n-1 iterations, the entire array arr[0:n] is  

sorted, as all elements are placed in their correct positions. 

Termination:  

Outer Loop: Iterates from 0 to n-1, reducing the unsorted section each time, and will terminate after n iterations. 
Inner Loop: Runs n-i times per outer loop iteration, decreasing with i, and will end due to the finite array size.  

By ensuring the invariant holds and both loops terminates after processing all elements, Selection Sort is guaranteed to correctly sort the array and complete in a finite number pf operation. 

Benchmarking Results
System Specifications
Operating System: Microsoft Windows 11 Home
Processor: 11th Gen Intel(R) Core(TM) i7-1165G7 @ 2.80GHz (4 Cores, 8 Threads)
RAM: 8.00 GB
Input Sizes for Benchmarking
We test sorting on various array sizes:

Small Arrays: 5, 10, 20
Medium Arrays: 50, 100, 500, 1000
Large Arrays: 5000, 10000, 15000 (where system slows down)

Benchmarking Results (Execution Times in Seconds)

Input Size	Insertion Sort	Selection Sort	Bubble Sort
5	        0.000003 sec	0.000002 sec	0.000002 sec
10	        0.000008 sec	0.000007 sec	0.000006 sec
20	        0.000020 sec	0.000018 sec	0.000022 sec
50	        0.000078 sec	0.000071 sec	0.000092 sec
100	        0.000305 sec	0.000270 sec	0.000401 sec
500	        0.011645 sec	0.010832 sec	0.015901 sec
1000	    0.048211 sec	0.042354 sec	0.065932 sec
5000	    1.296543 sec	1.102934 sec	1.834921 sec
10000	    5.894302 sec	4.875321 sec	7.624893 sec
15000	    13.201982 sec	10.458213 sec	16.902332 sec

Observations:
Insertion Sort performs well for small inputs but slows down for large arrays.
Selection Sort consistently outperforms Bubble Sort.
Bubble Sort is the slowest for large inputs because of excessive swapping.

Graph Plot is given in the repository.


