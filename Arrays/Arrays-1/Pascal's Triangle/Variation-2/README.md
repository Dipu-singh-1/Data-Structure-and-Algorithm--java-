# Pascal's Triangle Row Calculator

## Introduction
This tool prints the n-th row of Pascal’s triangle.

## Naive Approach
The naive approach involves calculating each element of the row separately using the combination calculation method. It iterates over each column from 1 to n and calculates the element (n, c) using a loop. Finally, it prints the entire row.

## Optimal Approach
The optimal approach builds the row by multiplying the previous element with (n-index) and dividing by index, where index marks the indices of the column starting from 0. This approach significantly reduces computation by exploiting the pattern observed in Pascal's triangle.

## Algorithm / Intuition
### Naive Approach
1. Iterate over each column from 1 to n.
2. For each column, calculate the element (n, c) using the combination calculation method.
3. Print each element to form the row.

### Optimal Approach
1. Manually print the 1st element, which is always 1.
2. Use a loop to iterate from 1 to n-1 to print the rest of the elements.
3. Use the formula: Current element = prevElement * (rowNumber - colIndex) / colIndex to calculate each element.
4. Print each element to form the row.

## Code Implementation
```python
def print_pascals_triangle_row(n):
    row = [1]  # Manually print the first element
    for i in range(1, n):
        element = row[i - 1] * (n - i) // i
        row.append(element)
    print(" ".join(map(str, row)))

# Example usage:
row_number = 5
print("The", row_number, "th row of Pascal's triangle is:")
print_pascals_triangle_row(row_number)
