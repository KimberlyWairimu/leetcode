# My Squareroot (LeetCode 69)

## 1. Problem Statement

Given a **non-negative** integer x, return the square root of x rounded down to the nearest integer. The returned integer should be non-negative as well.

You **must not use** any built-in exponent function or operator.

For example, do not use pow(x, 0.5) in c++ or x \*\* 0.5 in python.

**Example 1:**

**Input:** x = 4

**Output:** 2

**Explanation:** The square root of 4 is 2, so we return 2.

**Example 2:**

**Input:** x = 8

**Output:** 2

**Explanation:** The square root of 8 is 2.82842..., and since we round it down to the nearest integer, 2 is returned.

Constraints:

0 <= x <= 231 - 1

## 2. Solution (Binary Search Approach)

Instead of using **brute force** (which runs in O(√x) time), we optimize by applying **binary search** to efficiently locate the largest integer mid such that **mid² ≤ x.**

### Thought Process:

**1. Defining the Search Space**

We know the square root of x must lie between 0 and x (lower = 0, upper = x).

We repeatedly divide the search space in half (mid = (lower + upper) // 2).

**2. Binary Search Steps**

If mid \* mid == x, we have found the exact square root and return mid.

If mid \* mid < x, it means mid is too small, so we shift lower to mid + 1.

If mid \* mid > x, it means mid is too large, so we shift upper to mid - 1.

The loop stops when lower > upper, and the correct answer is upper, since it holds the largest integer ≤ sqrt(x).

**3. Efficiency**

Since binary search halves the search space in each step, this runs in O(log x) time, making it much faster than a brute force approach (O(√x)).

## 3. Performance and Complexity Analysis

| Metric               | Value        | Explanation                                                     |
| -------------------- | ------------ | --------------------------------------------------------------- |
| **Time Complexity**  | `O(log x)`   | Binary search reduces search space by half in each step         |
| **Space Complexity** | `O(1)`       | Only a few integer variables are used (`lower`, `upper`, `mid`) |
| **Runtime**          | **3 ms**     | Beats **60.83%** of Python submissions                          |
| **Memory Usage**     | **17.67 MB** | Beats **81.15%** of Python submissions                          |

## 4. LeetCode Submission

[View my Submission](https://leetcode.com/problems/sqrtx/submissions/1562464591/)
