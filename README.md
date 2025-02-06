# Dali-Leetcode-problem-solution13
PROBLEM

You are given a binary matrix matrix of size m x n, and you are allowed to rearrange the columns of the matrix in any order.
Return the area of the largest submatrix within matrix where every element of the submatrix is 1 after reordering the columns optimally.

Intuition

To solve this problem optimally, we need to make the best use of the column rearrangement to maximize the area of a submatrix consisting entirely of 1s

Approach

We can treat each row of the matrix as a histogram of heights, where each element represents the number of consecutive 1s in the matrix up to that row. The idea is to calculate the maximum area of 1s you can get from the histogram by sorting the heights in non-decreasing order.

Step 1: Calculate Heights: Convert each row into a histogram of heights. For each column in the matrix, calculate the consecutive number of 1s from the current row upwards. If the element is 0, reset the height to 0.

Step 2: Sort Heights: After calculating the histogram of heights for each row, sort the heights in descending order for the maximum area calculation. Sorting ensures that we can maximize the rectangle area by using the largest heights first.

Step 3: Calculate Maximum Area: For each row, after sorting the heights, compute the area by multiplying the height by its column index (since the heights are sorted). Track the maximum area found.

Complexity

Time complexity:
Height computation:
O(m×n), as we iterate through every element once.
Sorting each row:
O(nlogn), as we sort each row individually.
Total:
O(m×nlogn).

Space complexity:
O(m×n)
