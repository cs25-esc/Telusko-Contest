# Telusko-Contest

**Day-1---Recursion-and-Memoization**

-- Printing a complete pascal triangle -- 

Method - 1:

Iteration:

in the iteration technique we will iterate over each row and each index in the pascal triangle.
lets consider i as row iterator and j as column iterator
we know that "1" is the  value in first index (i.e, 0) and last index (i.e, i) of each row in the triangle.
if the index is not the first and last then we will add [(i-1)th row's (j)th column and (j-1)th column] values (of course which are already computed)


![WhatsApp Image 2023-05-20 at 09 18 54](https://github.com/cs25-esc/Telusko-Contest/assets/68850280/a357b4b3-134e-4bb3-8f98-2024cc781208)

avg time taken by iteration technique - 3.126723527908325 msecs





