# Introduction to Big O

If you already understand Big O, you can skip this article.

Before we talk about Big O, it's important to first understand what exactly an **algorithm** is, especially in the context of LeetCode.

An **algorithm** can be seen as a recipe for a computer to follow. It's a set of instructions that a computer will execute step-by-step to solve a problem. Algorithms take an **input** and produce an **output**. The output will answer a question regarding the input.

For example, let's say you have a non-empty array of positive integers called `nums`, and you want to answer the question: "What is the largest number in `nums`?"

To answer this question, you would write an algorithm that takes `nums` as input and outputs the largest number in `nums`.

### Example Algorithm

```java
// Create a variable maxNum and initialize it to 0
int maxNum = 0;

// Iterate over each element num in nums
for (int num : nums) {
    // If num is greater than maxNum, update maxNum
    if (num > maxNum) {
        maxNum = num;
    }
}

// Output maxNum
System.out.println(maxNum);
```

Here, we have written a set of instructions that, when followed, will solve the problem. We can now implement these instructions in code so that a computer can quickly solve the problem.

There are some important requirements for algorithms, particularly in the context of LeetCode:

- **Algorithms should be deterministic**: Given the same input, the algorithm should always produce the same output. There shouldn't be any randomness.
- **The algorithm should be correct for any valid input**: For example, if `nums` is a non-empty array of positive integers, our algorithm works for all such arrays. However, if `nums` contained negative numbers, our algorithm would break because we initialized `maxNum` to 0, which would incorrectly result in an output of 0.

## What is Big O?

Big O is a notation used to describe the computational complexity of an algorithm. The computational complexity of an algorithm is divided into two parts:

1. **Time complexity**: The amount of time the algorithm takes to run relative to the input size.
2. **Space complexity**: The amount of memory allocated by the algorithm when run relative to the input size.

### Common Time Complexities

When written, the complexity function is wrapped by a capital O. Here are some example complexities:

- **O(n)**: Linear time
- **O(n²)**: Quadratic time
- **O(2ⁿ)**: Exponential time
- **O(log n)**: Logarithmic time
- **O(n log n)**: Linearithmic time
- **O(n ⋅ m)**: Denotes complexity based on two inputs

### Calculating Complexity

For example, in the algorithm above for finding the largest number in `nums`, we have a time complexity of `O(n)`. The algorithm iterates over each element in `nums`, so if we define `n` as the length of `nums`, our algorithm uses approximately `n` steps.

```java
// Given an integer array "arr" with length n
for (int num : arr) {
    System.out.println(num);
}
```

This algorithm has a time complexity of **O(n)**. In each iteration of the `for` loop, we are performing a print operation, which costs **O(1)**. The `for` loop iterates `n` times, so the total complexity is **O(n)**.

### More Examples

```java
// Given an integer array "arr" with length n
for (int num : arr) {
    for (int i = 0; i < 500,000; i++) {
        System.out.println(num);
    }
}
```

This algorithm also has a time complexity of **O(n)**. Even though there’s an inner loop running 500,000 times, that’s a constant value and doesn't depend on `n`. Thus, we ignore constants in Big O notation.

```java
// Given an integer array "arr" with length n
for (int num : arr) {
    for (int num2 : arr) {
        System.out.println(num * num2);
    }
}
```

This algorithm has a time complexity of **O(n²)** because the inner loop runs `n` times for each iteration of the outer loop, resulting in **n ⋅ n = n²** total operations.

---

## Logarithmic Time

A logarithm is the inverse operation to exponents. The time complexity **O(log n)** is called logarithmic time and is extremely fast. A common time complexity is **O(n log n)**, which is reasonably fast for most problems and is the time complexity of efficient sorting algorithms like Merge Sort or Quick Sort.

A good example of logarithmic time complexity is binary search, where we reduce the search space by half at each step, resulting in **O(log n)** operations.

---

## Space Complexity

Space complexity measures the amount of memory an algorithm allocates. Here’s an example:

```java
// Given an integer array "arr" with length n
int[] doubledNums = new int[arr.length];

for (int num : arr) {
    doubledNums.add(num * 2);
}
```

This algorithm has a space complexity of **O(n)** because we store `n` integers in the `doubledNums` array.

```java
// Given integer arrays "arr" with length n and "arr2" with length m
int[][] grid = new int[arr.length][arr2.length];

for (int i = 0; i < arr.length; i++) {
    for (int j = 0; j < arr2.length; j++) {
        grid[i][j] = arr[i] * arr2[j];
    }
}
```

This algorithm has a space complexity of **O(n ⋅ m)** because we are creating a grid with dimensions `n ⋅ m`.

---

## Summary

- **Big O** notation helps describe the time and space complexity of an algorithm.
- **Time complexity** measures how the runtime grows as the input size increases.
- **Space complexity** measures the memory usage relative to the input size.
- Common complexities include **O(1)**, **O(n)**, **O(log n)**, **O(n²)**, and **O(n log n)**.

Understanding Big O is crucial for optimizing algorithms and explaining them in technical interviews.
