# Telusko-Contest

**Day-1---Recursion-and-Memoization**

-- Printing a complete pascal triangle -- 

**Method - 1 Iteration::**


In the iteration technique we will iterate over each row and each index in the pascal triangle. <br>
lets consider i as row iterator and j as column iterator  <br>
we know that "1" is the  value in first index (i.e, 0) and last index (i.e, i) of each row in the triangle. <br>
if the index is not the first and last then we will add [(i-1)th row's (j)th column and (j-1)th column] values (of course which are already computed) <br>


![WhatsApp Image 2023-05-20 at 09 18 54](https://github.com/cs25-esc/Telusko-Contest/assets/68850280/a357b4b3-134e-4bb3-8f98-2024cc781208)

**avg time taken by iteration technique - 3.126723527908325 msecs**

<br><br><br>
**Method - 2 Recursion:**


In the recursion technique we will recursively find by iterating over each row and each index in the pascal triangle. <br>
lets consider i as row iterator and j as column iterator <br>
for value at index(i,j) we implemented recursive function solve. <br>

code snippet:

def solve(i,j):
    
    if j == 0 or j == i:                          --> this is the base case like the same way we did for iterative method                      
        return 1
    else:
        return solve(i-1 , j-1) + solve(i-1,j)     --> here we recusrively call for (i-1)th row's jth and (j-1)th column values


**avg time taken by recursive technique - 4.400288105010986 msecs**

<br><br><br>

**Note: as discussed in the live class recursion is solving all the sub problems (even the previously computed values) so we go for memoized technique where we store the previously computed values.**
<br><br><br>

**Method - 3 Memoization:**

Same as in the recursion technique we will recursively find by iterating over each row and each index in the pascal triangle ***but we will not call recusrive call for previously stored values*** <br>

since we already know that first and last index of each row is value "1" we keep 1 in the memoize table <br>

code snippet to intialize memoized table:

memoized = []
for i in range(n):

    e = []
    for j in range(i+1):
        if j == 0 or j == i:
            e.append(1)
        else:
            e.append(0)
    memoized.append(e) 

**if n = 5 the memoized table looks like**


1   <br>
1 1   <br>
1 0 1   <br>
1 0 0 1   <br>
1 0 0 0 1   <br>

then we will call memoize recusrive function for each index in each row

code snippet:

def solve(i,j):

    if memoized[i][j]:            --> if it is previously computed we just return that value
        return memoized[i][j]
    else:
        memoized[i][j] = solve(i-1 , j-1) + solve(i-1,j)            --> we store each computed value for (i-1)th row's jth and (j-1)th column values
        return memoized[i][j]
    

**avg time taken by memoized technique - 3.2637522220611572 msecs**


<br><br><br>

**Observation:**

**The iterative method and memoized method looks similar in both approach wise and time taken to execute <br> 
but in terms of memory iterative and recursive are good**

