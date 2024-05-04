# Algorithm / Intuition

## Approach (Using two extra arrays):

The steps are as follows:

1. First, we will declare two arrays: a row array of size N and a col array of size M, both initialized with 0.
2. Then, we will use two nested loops to traverse all the cells of the matrix.
3. If any cell (i,j) contains the value 0, we will mark the ith index of the row array i.e., `row[i]`, and the jth index of the col array i.e., `col[j]` as 1. It signifies that all the elements in the ith row and jth column will be 0 in the final matrix.
4. We will perform step 3 for every cell containing 0.
5. Finally, we will traverse the entire matrix again and put 0 into all the cells (i, j) for which either `row[i]` or `col[j]` is marked as 1.
   Thus, we will get our final matrix.

## Intuition:

In the previous approach, we were marking the cells with -1 while traversing the matrix. However, in this approach, we are not marking the entire row and column. Instead, we are marking the ith index of the row array i.e., `row[i]`, and the jth index of the col array i.e., `col[j]` with 1. These marked indices of the two arrays, row and col, will indicate for which rows and columns we need to change the values to 0. For any cell (i, j), if the `row[i]` or `col[j]` is marked with 1, we will change the value of cell(i, j) to 0.

Here, we are marking the cells after traversal, whereas in the previous case, we were marking the cells while traversing. This is how the time complexity reduces in this case.

