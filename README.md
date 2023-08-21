# Candidate Exercise / Backend Engineer for honei

> Max. duration: 48 hours

## Exercice 1: Highest Occurrence (optional)

Write a function called `highestOccurrence`. Given an array of `string` and/or `number`, this function should return the array item with the highest frequency. The time complexity of the solution should be inferior or equal to O(n).

Signature:

```ts
type highestOccurrence = (input: Array<string | number>) => Array<string | number>;
```

Example:

```ts
highestOccurrence([2, 3, 2, 2, 2, 4, 2]);
// [2]

highestOccurrence([2, 3, 2, 3, 2, 3, 4]);
// [2, 3]

highestOccurrence(['a', 'b', 'c', 'a', 'a', 'a', 'a']);
// ['a']

highestOccurrence(['a', 'a', 2, 2, 2, 'a', 4]);
// ['a', 2]
```

## Exercice 2: Maximum Sub Array Sum (optional)

Write a function called `maxSubarraySum` which accepts an array of integers and a number called n. The function should calculate the maximum sum of n consecutive elements in the array. The time complexity of the solution should be inferior or equal to O(n).

Signature:

```ts
type maxSubarraySum = (input: Array<number>, num: number) => number;
```

Example:

```ts
maxSubarraySum([1,2,5,2,8,1,5], 4)
// 17

maxSubarraySum([1,2,5,2,8,1,5], 2)
// 10

maxSubarraySum([4,2,1,6], 1)
// 6

maxSubarraySum([4,2,1,6,2], 4)
// 13

maxSubarraySum([], 4)
// null
```

## Exercice 3: Average Pair (optional)

Write a function called `averagePair`. Given a sorted array of integers and a target average, determine if there is a pair of values in the array where the average of the pair equals the target average. There may be more than one pair that matches the average target. The time complexity of the solution should be inferior or equal to O(n).

Signature:

```ts
type averagePair = (input: Array<number>, target: number) => boolean;
```

Example:

```ts
averagePair([1,2,3], 2.5)
// true

averagePair([1,3,3,5,6,7,10,12,19], 8)
// true

averagePair([-1,0,3,4,5,6], 4.1)
// false

averagePair([], 4)
// false
```


## Exercice 4: Parallel Processing (mandatory)

### Objective:

Create a service in Node.js that generates a set of random numbers and then sums up these numbers efficiently using parallel processing. Through this task, you'll learn about leveraging multiple "threads" to process data more swiftly.

### Steps:

1.  **Random Number Generation**:
We're providing you with this function that generates a set of random numbers:

```ts
function generateRandomArray(length: number): Array<number> {
    return Array.from({ length }, () => Math.floor(Math.random() * 1000));
} 
```

2.  **Why Use Parallel Processing?**:
Imagine you have to sum up 100,000 numbers. If you sum them up one at a time, it would take a while. But if you split those numbers into smaller groups and sum up several groups at the same time (in parallel), you could get the total much faster. This is the idea behind parallel processing.

3.  **Create the Service**:
-   Build a service with a POST endpoint named `/generate-and-sum`.
-   This endpoint should accept a number called `count` that decides how many random numbers you want to generate.
-   Generate the numbers using the `generateRandomArray` function.
-   Divide this large set of numbers into smaller batches. For instance, if you have 100,000 numbers, you might have 10 batches of 10,000 numbers each.
-   Use "worker threads" in Node.js to sum each batch in parallel.
-   As you sum up, display progress messages like "Summing up batch 1...", so we can see that your program is making progress.
-   Once all batches are summed, add up the totals from each batch to get the final sum and return it.

4.  **Tips**:
-   If you've never heard of "worker threads," don't worry. Look for documentation or tutorials on how to use them in Node.js. They're a tool to enable parallel processing.
-   Think about how you can efficiently split and sum the numbers.

### What We're Looking For:
-   **Functionality**: Your program should generate numbers and sum them up.
-   **Efficiency**: Can you make the sum faster using parallel processing?
-   **Communication**: We like to see progress messages to know how the program is doing.

### Submission:
-   Submit all the code you wrote.
-   Include clear instructions on how to run your program.
