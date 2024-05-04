Problem Statement: This problem has 3 variations. They are stated below:

Variation 1: Given row number r and column number c. Print the element at position (r, c) in Pascal’s triangle.

Variation 2: Given the row number n. Print the n-th row of Pascal’s triangle.

Variation 3: Given the number of rows n. Print the first n rows of Pascal’s triangle.

In Pascal’s triangle, each number is the sum of the two numbers directly above it as shown in the figure below:

# Pascal's Triangle Element Calculator

## Introduction
This tool calculates the element at a specific position (r,c) in Pascal's Triangle using both naive and optimal approaches.

## Naive Approach
The naive approach involves generating the entire Pascal triangle and then finding the element at position (r,c). It calculates the value of nCr using separate calculations for n!, r!, and (n-r)!. This method has a time complexity of O(n)+O(r)+O(n-r).

## Optimal Approach
The optimal approach utilizes a formula derived from Pascal's triangle properties. It optimizes the calculation by iterating through a loop and calculating the combination value using the formula:

```(n / 1)((n-1) / 2).....*((n-r+1) / r)```

This approach significantly reduces the computational complexity.

## Algorithm / Intuition
1. Consider r-1 as n and c-1 as r.
2. Calculate the value of the combination using the optimized formula.
3. Iterate through a loop from 0 to r, multiplying (n-i) with the result and dividing the result by (i+1).
4. The calculated value of the combination will be the answer.

## Code Implementation
```python
def calculate_pascals_triangle_element(r, c):
    n = r - 1
    r = c - 1
    result = 1
    for i in range(r):
        result *= (n - i)
        result //= (i + 1)
    return result

# Example usage:
row_number = 7
column_number = 4
element = calculate_pascals_triangle_element(row_number, column_number)
print(f"The element at position ({row_number},{column_number}) is: {element}")
