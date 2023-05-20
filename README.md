# Telusko-Contest

**Day-1---Recursion-and-Memoization**

-- Printing a complete pascal triangle -- 

Method - 1:

Iteration:

in the iteration technique we will iterate over each row and each index in the pascal triangle.
lets consider i as row iterator and j as column iterator
we know that "1" is the  value in first index (i.e, 0) and last index (i.e, i) of each row in the triangle.
if the index is not the first and last then we will add [(i-1)th row's (j)th column and (j-1)th column] values (of course which are already computed)


!![WhatsApp Image 2023-05-20 at 09 18 54](https://github.com/cs25-esc/Telusko-Contest/assets/68850280/a357b4b3-134e-4bb3-8f98-2024cc781208)

avg time taken by iteration technique - 3.126723527908325 msecs


Method - 2:

Recursion:

in the recursion technique we will recursively find by iterating over each row and each index in the pascal triangle.
lets consider i as row iterator and j as column iterator
for value at index(i,j) we implemented recursive function solve.

code snippet:

def solve(i,j):
    
    if j == 0 or j == i:                          --> this is the base case like the same way we did for iterative method                      
        return 1
    else:
        return solve(i-1 , j-1) + solve(i-1,j)     --> here we recusrively call for (i-1)th row's jth and (j-1)th column values


avg time taken by recursive technique - 4.400288105010986 msecs

Note: as discussed in the live class recursion is solving all the sub problems (even the previously computed values) so we go for memoized technique where we store the previously computed values.

Method - 3:

Memoization:

same as in the recursion technique we will recursively find by iterating over each row and each index in the pascal triangle ***but we will not call recusrive call for previously stored values***

since we already know that first and last index of each row is value "1" we keep 1 in the memoize table

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

1
1 1
1 0 1
1 0 0 1
1 0 0 0 1

then we will call memoize recusrive function for each index in each row

code snippet:

def solve(i,j):
    #print(i,j)
    if memoized[i][j]:            --> if it is previously computed we just return that value
        return memoized[i][j]
    else:
        memoized[i][j] = solve(i-1 , j-1) + solve(i-1,j)            --> we store each computed value for (i-1)th row's jth and (j-1)th column values
        return memoized[i][j]
    

avg time taken by memoized technique - 3.2637522220611572 msecs





