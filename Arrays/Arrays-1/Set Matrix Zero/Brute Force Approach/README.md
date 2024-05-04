# Algorithm / Intuition

## Approach:

The steps are as follows:

1. First, we will use two nested loops to traverse all the cells of the matrix.
2. If any cell (i,j) contains the value 0, we will mark all cells in row i and column j with -1, except those which contain 0.
3. We will perform step 2 for every cell containing 0.
4. Finally, we will mark all the cells containing -1 with 0.
   Thus, the given matrix will be modified according to the question.

**Note:** Here, we are assuming that the matrix does not contain any negative numbers. If it contains negatives, we need to find other ways to mark the cells instead of marking them with -1.

## Intuition:

This approach is straightforward, following the process stated in the question. However, there are two questions that need clarification to understand the algorithm further:

1. **Why are we marking the cells with -1 and not with 0 directly?**

   Let’s understand this with an example. Consider the following matrix:

```
[1, 0, 1]
[1, 1, 1]
[1, 1, 1]
```

If we mark cells directly with 0, after finding 0 at cell (1,1), the matrix would look like this:

```[0, 0, 0]
[0, 0, 0]
[1, 1, 1]
```


Now, if we find 0 at cell (1,2), which was initially 1, not 0, we would mark the wrong rows and columns with 0. Hence, we choose -1 as our marker.

2. **While marking the cells with -1, why are we not marking the cells that contain 0?**

Again, let’s understand this with an example. Consider the following matrix:

```[1, 0, 1]
[1, 1, 1]
[1, 1, 1]
```

If we mark all cells with -1 directly, after finding 0 at cell (1,1), the matrix would look like this:

```[-1, -1, -1]
[1, 1, 1]
[1, 1, 1]
```

Now, we would not be able to find the value 0 that should be in cell (1,3). Our algorithm would not modify column 3, which is why we do not modify cells with value 0 while marking cells with -1, as those cells with 0 contribute to the answer.

The given matrix:

```[1, 0, 1]
[1, 1, 1]
[1, 1, 1]
```

