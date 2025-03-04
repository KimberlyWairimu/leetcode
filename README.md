# Climbing Stairs (Leetcode 70)

## Problem Statement

You are climbing a staircase. It takes n steps to reach the top.

Each time you can either climb 1 or 2 steps. In how many distinct ways can you climb to the top?

**Example 1:**

**Input:** n = 2

**Output:** 2

**Explanation:** There are two ways to climb to the top.

1. 1 step + 1 step
2. 2 steps

**Example 2:**

**Input:** n = 3

**Output:** 3

**Explanation:** There are three ways to climb to the top.

1. 1 step + 1 step + 1 step
2. 1 step + 2 steps
3. 2 steps + 1 step

**Constraints:**

1 <= n <= 45

## Solution: Dynamic Programming (Optimized Fibonacci Approach)

Instead of using recursion (which has **O(2ⁿ) exponential time complexity**), we optimize the approach by recognizing that this problem follows the **Fibonacci sequence.**

### Thought Process:

**1.Observing the Pattern**

- If n = 1, there's only 1 way (just 1 step).
- If n = 2, there are 2 ways (either 1+1 or 2).
- If n = 3, we can either:

  - Take a 1-step from n=2, meaning we inherit its count (which is 2).

  - Take a 2-step from n=1, inheriting its count (which is 1).

  - Total ways for n=3 = **ways(n-1) + ways(n-2)** = 2 + 1 = 3.

  This pattern continues, forming a Fibonacci-like sequence.

**2.Optimizing Space**

Instead of storing all previous results (which costs O(n) space in traditional Dynamic Programming),
We only store the last two computed values, reducing space complexity to O(1).

**3.Iterative Approach**

- We start with the base values (1 step → 1 way, 2 steps → 2 ways).
- We iteratively compute the next step using a + b (Sum of the previous two steps).

## Performance and Complexity Analysis

| Metric               | Value        | Performance                            |
| -------------------- | ------------ | -------------------------------------- |
| **Time Complexity**  | `O(n)`       | We iterate once from `3` to `n`        |
| **Space Complexity** | `O(1)`       | Only two variables (`a`, `b`) are used |
| **Runtime**          | **42 ms**    | Beats **0.11%** of Python submissions  |
| **Memory Usage**     | **17.74 MB** | Beats **48.60%** of Python submissions |

### LeetCode Submission

[View My Submission](https://leetcode.com/problems/climbing-stairs/submissions/1562324621/)
