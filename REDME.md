# Basic of Time Complexity
***
***
#### Sometimes, there are more than one way to solve a problem. We need to learn how to compare the performance different algorithms and choose the best one to solve a particular problem. While analyzing an algorithm, we mostly consider time complexity and space complexity. Time complexity of an algorithm quantifies the amount of time taken by an algorithm to run as a function of the length of the input. Similarly, Space complexity of an algorithm quantifies the amount of space or memory taken by an algorithm to run as a function of the length of the input.

Time and space complexity depends on lots of things like hardware, operating system, processors, etc. However, we don't consider any of these factors while analyzing the algorithm. We will only consider the execution time of an algorithm.

Lets start with a simple example. Suppose you are given an array  and an integer  and you have to find if  exists in array .####

Simple solution to this problem is traverse the whole array  and check if the any element is equal to .

for i : 1 to length of A
    if A[i] is equal to x
        return TRUE
return FALSE
Each of the operation in computer take approximately constant time. Let each operation takes  time. The number of lines of code executed is actually depends on the value of . During analyses of algorithm, mostly we will consider worst case scenario, i.e., when  is not present in the array . In the worst case, the if condition will run  times where  is the length of the array . So in the worst case, total execution time will be .  for the if condition and  for the return statement ( ignoring some operations like assignment of  ).

As we can see that the total time depends on the length of the array . If the length of the array will increase the time of execution will also increase.

Order of growth is how the time of execution depends on the length of the input. In the above example, we can clearly see that the time of execution is linearly depends on the length of the array. Order of growth will help us to compute the running time with ease. We will ignore the lower order terms, since the lower order terms are relatively insignificant for large input. We use different notation to describe limiting behavior of a function.

-notation:
To denote asymptotic upper bound, we use -notation. For a given function , we denote by  (pronounced “big-oh of g of n”) the set of functions:
 {  : there exist positive constants  and  such that  for all  }

-notation:
To denote asymptotic lower bound, we use -notation. For a given function , we denote by  (pronounced “big-omega of g of n”) the set of functions:
 {  : there exist positive constants  and  such that  for all  }

-notation:
To denote asymptotic tight bound, we use -notation. For a given function , we denote by  (pronounced “big-theta of g of n”) the set of functions:
 {  : there exist positive constants  and  such that  for all  }

enter image description here

Time complexity notations

While analysing an algorithm, we mostly consider -notation because it will give us an upper limit of the execution time i.e. the execution time in the worst case.

To compute -notation we will ignore the lower order terms, since the lower order terms are relatively insignificant for large input.
Let 
Lets consider some example:

1.

int count = 0;
for (int i = 0; i < N; i++) 
    for (int j = 0; j < i; j++) 
        count++;
Lets see how many times count++ will run.

When , it will run  times.
When , it will run  times.
When , it will run  times and so on.

Total number of times count++ will run is . So the time complexity will be .

2.

int count = 0;
for (int i = N; i > 0; i /= 2) 
    for (int j = 0; j < i; j++) 
        count++;
This is a tricky case. In the first look, it seems like the complexity is .  for the  loop and  for  loop. But its wrong. Lets see why.
Think about how many times count++ will run.

When , it will run  times.
When , it will run  times.
When , it will run  times and so on.

Total number of times count++ will run is . So the time complexity will be .

The table below is to help you understand the growth of several common time complexities, and thus help you judge if your algorithm is fast enough to get an Accepted ( assuming the algorithm is correct ).

Length of Input (N)	Worst Accepted Algorithm
