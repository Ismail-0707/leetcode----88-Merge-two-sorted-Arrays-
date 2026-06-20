# LeetCode 88 - Merge Sorted Array

## Problem Statement
You are given two integer arrays `nums1` and `nums2`, sorted in non-decreasing order, and two integers `m` and `n`, representing the number of valid elements in `nums1` and `nums2` respectively.

Merge `nums2` into `nums1` as one sorted array.

---

## Brute Force Approach

### Intuition
Since `nums1` has enough extra space to hold all elements of `nums2`, we can:

1. Copy all elements of `nums2` into the empty positions of `nums1`.
2. Sort the entire `nums1` array.
3. Return the sorted array.

This approach is simple but not efficient because sorting is performed after merging.

---

## Algorithm

1. Traverse `nums2`.
2. Copy each element into the vacant positions of `nums1`.
3. Sort `nums1`.
4. The sorted `nums1` becomes the final merged array.

---

## Java Code

```java
class Solution {
    public void merge(int[] nums1, int m, int[] nums2, int n) {

        for(int i = 0; i < n; i++) {
            nums1[m + i] = nums2[i];
        }

        Arrays.sort(nums1);
    }
}
```

---

## Dry Run

### Input
```text
nums1 = [1,2,3,0,0,0]
m = 3

nums2 = [2,5,6]
n = 3
```

### Step 1: Copy nums2 into nums1

```text
nums1 = [1,2,3,2,5,6]
```

### Step 2: Sort nums1

```text
nums1 = [1,2,2,3,5,6]
```

### Output

```text
[1,2,2,3,5,6]
```

---

## Complexity Analysis

### Time Complexity
```text
O((m + n) log(m + n))
```

- Copying elements: O(n)
- Sorting merged array: O((m+n) log(m+n))

### Space Complexity
```text
O(1)
```

No extra data structure is used.

---

## Why is it Brute Force?

- It ignores the fact that both arrays are already sorted.
- Performs an unnecessary sorting operation.
- Does not utilize the sorted property efficiently.

---

## Optimal Approach

Use the **Two Pointer Technique** from the end of both arrays.

### Complexity

```text
Time Complexity: O(m + n)

Space Complexity: O(1)
```

---

## Pattern
```text
Array Manipulation + Sorting
```
