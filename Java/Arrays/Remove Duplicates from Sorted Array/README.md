# LeetCode 26 - Remove Duplicates from Sorted Array

## Problem Statement

Given an integer array `nums` sorted in **non-decreasing order**, remove the duplicates **in-place** such that each unique element appears only once.

The relative order of the elements should remain the same.

Return the number of unique elements (`k`).

The first `k` elements of `nums` should contain the unique elements, and the remaining elements are ignored.

---

## Example

### Input

```text
nums = [0,0,1,1,1,2,2,3,3,4]
```

### Output

```text
k = 5

nums = [0,1,2,3,4,_,_,_,_,_]
```

---

## Approach

Since the array is already sorted, duplicate elements always appear next to each other.

We use the **Two Pointer** technique.

- `i` keeps track of the last unique element.
- `j` scans the array from left to right.
- Whenever `nums[j] != nums[i]`, we have found a new unique element.
- Increment `i` and copy `nums[j]` to `nums[i]`.

This modifies the array in-place without using extra space.

---

## Algorithm

1. Initialize `i = 0`.
2. Traverse the array using `j` from `1` to `n-1`.
3. If `nums[j]` is different from `nums[i]`:
   - Increment `i`
   - Copy `nums[j]` to `nums[i]`
4. Return `i + 1`.

---

## Java Solution

```java
class Solution {

    public int removeDuplicates(int[] nums) {

        if (nums.length == 0) {
            return 0;
        }

        int i = 0;

        for (int j = 1; j < nums.length; j++) {

            if (nums[i] != nums[j]) {
                i++;
                nums[i] = nums[j];
            }
        }

        return i + 1;
    }
}
```

---

## Dry Run

Input:

```text
[0,0,1,1,1,2,2,3,3,4]
```

| j | nums[j] | Action | Unique Array |
|---|----------|--------|--------------|
|1|0|Duplicate|0|
|2|1|Copy|0 1|
|3|1|Duplicate|0 1|
|4|1|Duplicate|0 1|
|5|2|Copy|0 1 2|
|6|2|Duplicate|0 1 2|
|7|3|Copy|0 1 2 3|
|8|3|Duplicate|0 1 2 3|
|9|4|Copy|0 1 2 3 4|

Result:

```text
k = 5

nums = [0,1,2,3,4,_,_,_,_,_]
```

---

## Complexity Analysis

**Time Complexity**

```text
O(n)
```

Each element is visited exactly once.

**Space Complexity**

```text
O(1)
```

No extra space is used.

---

## Concepts Used

- Arrays
- Two Pointer Technique
- In-place Array Modification
- Time Complexity Optimization

---

## LeetCode

Problem Number: **26**

Difficulty: **Easy**

Topic: **Array, Two Pointers**