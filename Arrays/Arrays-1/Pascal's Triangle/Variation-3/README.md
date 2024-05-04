# Naive Pascal's Triangle Generation

## Introduction
This tool generates the Pascal's triangle up to the n-th row using a naive approach.

## Algorithm / Intuition
The naive approach combines the methods from variations 1 and 2. It iterates over each row from 1 to n and generates all row elements using the naive approach described in variation 2. This involves calculating the combination values for each element.

## Approach
1. Iterate over each row from 1 to n.
2. For each row, iterate over each column from 1 to n.
3. Calculate the combination value for each element using the method described in variation 2.
4. Add the calculated element to a temporary list.
5. After calculating all elements for a row, add the temporary list to the final answer list.
6. Return the answer list containing the generated Pascal's triangle.

## Code Implementation
```python
def generate_pascals_triangle(n):
    triangle = []
    for row in range(1, n + 1):
        temp_row = []
        for col in range(1, row + 1):
            element = calculate_pascals_triangle_element(row, col)  # Calculate element using naive approach
            temp_row.append(element)
        triangle.append(temp_row)
    return triangle

def calculate_pascals_triangle_element(r, c):
    n = r - 1
    r = c - 1
    result = 1
    for i in range(r):
        result *= (n - i)
        result //= (i + 1)
    return result

# Example usage:
row_count = 5
print("Generated Pascal's triangle up to", row_count, "rows:")
pascals_triangle = generate_pascals_triangle(row_count)
for row in pascals_triangle:
    print(" ".join(map(str, row)))
