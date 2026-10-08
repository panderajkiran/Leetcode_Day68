# Leetcode_Day68
# Day 68 — Longest Increasing Subsequence

## Problem

Given an integer array `nums`, find the length of the longest strictly increasing subsequence.

A subsequence does not need to contain consecutive elements, but the selected elements must remain in the same order.

### Example

Input:
`[10,9,2,5,3,7,101,18]`

Output:
`4`

One possible longest increasing subsequence is:

`[2,3,7,101]`

---

## Approach

I used the **Binary Search + Tails Array** approach.

I created an array called `tails`.

For every number in `nums`, I use binary search to find the first position in `tails` where the value is greater than or equal to the current number.

- If such a position exists, I replace that value with the current number.
- If the current number is greater than all values in `tails`, I add it at the end.
- The final size of `tails` gives the length of the Longest Increasing Subsequence.

### Why does this work?

The `tails` array stores the smallest possible ending value for an increasing subsequence of each length.

Smaller ending values are useful because they leave more room for future numbers to extend the subsequence.

---

## Complexity

### Time Complexity

`O(n log n)`

Each element is processed once, and binary search takes `O(log n)`.

### Space Complexity

`O(n)`

The `tails` array can contain up to `n` elements.

---

## What I Learned

Today I learned that sometimes we don't need to build the entire subsequence to find its length.

Instead, we can maintain the best possible "tail" for subsequences of different lengths.

The important part was understanding why replacing an existing value in `tails` does not reduce the answer. It simply gives that subsequence a smaller ending value, which makes it easier to extend later.

---

## Takeaway

Today reminded me that solving a problem efficiently often means changing the way we represent the problem.

Instead of storing everything, sometimes storing just the right information is enough.
