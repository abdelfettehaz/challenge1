# Challenge 1: Consecutive Increasing Numbers

## Problem Description

Given a string containing only digits, determine whether it can be split into at least two positive integers such that:

- The numbers are strictly increasing
- Each number is exactly 1 greater than the previous one
- All digits are used in order
- No number contains leading zeros

Return `True` if such a split exists, otherwise return `False`.

## Examples

| Input | Output | Explanation |
|-------|--------|-------------|
| `"99100"` | `True` | Can be split as 99, 100 |
| `"979899100101"` | `True` | Can be split as 97, 98, 99, 100, 101 |
| `"1234"` | `False` | Cannot form consecutive increasing numbers |
| `"91011"` | `True` | Can be split as 9, 10, 11 |
| `"101112"` | `True` | Can be split as 10, 11, 12 |
| `"99100101"` | `False` | 99, 100, 101 would require 99,100,101 but string is "99100101" |

## Solution Approach

The solution tries different possible lengths for the first number and validates if the remaining string can be split into consecutive increasing numbers:

1. Try each possible length for the first number (from 1 to half the string length)
2. Extract the first number and ensure no leading zeros
3. For each subsequent position, verify that the next segment matches the expected next number (current + 1)
4. Check for leading zeros in subsequent numbers
5. If the entire string is consumed and at least two numbers are found, return True

## Time Complexity

O(n²) where n is the length of the input string. For each possible first number length, we traverse the string once.

## Space Complexity

O(1) as we only use constant extra space.

## Function Signature

```python
def is_possible(ch: str) -> bool:
    """
    Determines if a string of digits can be split into consecutive increasing numbers.
    
    Args:
        ch: String containing only digits
    
    Returns:
        True if such a split exists, False otherwise
    """
