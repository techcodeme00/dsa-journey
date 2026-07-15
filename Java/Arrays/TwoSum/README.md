# Two Sum

## Problem
Given an array of integers and a target, return the indices of the two numbers that add up to the target.

## Approaches

### 1. Brute Force

Time Complexity: O(n²)

Space Complexity: O(1)

Idea:
Check every possible pair until the target sum is found.

---

### 2. HashMap (Optimal)

Time Complexity: O(n)

Space Complexity: O(n)

Idea:
Store previously visited numbers in a HashMap.
For every element, check whether its complement already exists.