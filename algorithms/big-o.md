# Big-O Notation

## Time Complexity

### Example 1

```js
function summation(n) {
    let sum = 0
    for (let i = 1; i <= n; i++) {
        sum += i
    }

    return sum
}

console.log(summation(4)) // 10
// 1 + 2 + 3 + 4
```

We count the number of times a statement executes based on the input size.

```js
// n = 4
function summation(n) {
    let sum = 0 // executes only once (1)
    for (let i = 1; i <= n; i++) {
        sum += i // executes 4 times (4)
    }

    return sum // executes only once (1)
}

console.log(summation(4)) // 10
// 1 + 2 + 3 + 4
```

We can generalize this to `n + 2`, say `n` is equal to `10` then the total
count is `10 + 2`. Our time complexity is dependent on the input size.

However, time complexity focuses on the bigger picture without getting caught
up in the minute details.

```
n = 100 => 100 + 2
n = 1000 => 1000 + 2
n = 10000 => 10000 + 2
.
.
.
n = 100000000 => 100000000 + 2
```

The `+2` is very insignificant we can actually drop it. `n + 2` can be
approximated to just `n` since `n` contributes the most to the total value and
not the additional `2` extra steps.

So the time complexity of our `summation` function is `O(n) - Linear` (As the
size of the input increases, the time complexity also increases).

### Example 2

```js
function summation(n) {
    return (n * (n + 1)) / 2 // executes only once
}
```

The time complexity of this algorithm is `O(1) - Constant`.

### Example 3

```js
for (let i = 1; i <= n; i++) {
    for (let j = 1; j <= i; j++) {
        // ...
    }
}
```

The time complexity of this algorithm is `O(n^2) - Quadratic`.

### Example 4

```js
for (let i = 1; i <= n; i++) {
    for (let j = 1; j <= i; j++) {
        for (let k = 1; k <= j; k++) {
            // ...
        }
    }
}
```

The time complexity of this algorithm is `O(n^3) - Cubic`.

## Space Complexity

The idea remains the same. If the algorithm doesn't need extra memory or the
memory needed doesn't dependent on the input size, the space complexity is
`O(1) - Constant` (ex: Sorting algorithms which sort within the array without
utilizing additional arrays).

You can also have algorithms with linear space complexity where the extra space
needed grows as the input size grows (`O(n) - Linear`) and you can also have a
logarithmic space complexity in which case the extra space needed grows but not
at the same rate as the input size (`O(log n)`).

## Notes 📝

-   Multiple algorithms exist for the same problem and there is no one right
    solution. Different algorithms work well under different constraints.
-   The same algorithm with the same programming language can be implemented in
    different ways.
-   When writing programs at work, don't lose sight of the big picture. Rather
    than writing clever code, write code that is simple to read and maintain.
