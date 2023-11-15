# Time and Space Complexity

## Big O

Big O is a way to categotize your algorithms time and space requirements based on input. not an exact measurement.
(As input grows how fast does computation or memory grow?)

## Why

Helps us make decisions on what data structures and algorithms to use.

## Example 1

```
function sum_char_codes(n: string): number {
    let sum = 0;
    for (let i = 0; i < n.length; ++i) {
        sum += n.charCodeAt(i);
    }

    return sum;
}
```

We have a _O(n)_ time complexity

Look for the **loops!**
We are traversing the length of _n_. The complexity of the program is dependent on the size of _n!_

## Concepts

1. Growth is with respect to the input
2. Constants are dropped

O(2n) -> O(n). Big O is meant to describe the upper bound of the algorithm (growth). The constant eventually becomes irrelevent

n = 1, O(10n) = 10, O(n^2) = 2

n = 5, O(10n) = 50, O(n^2) = 25

n = 1000, O(10n) = 10,000, O(n^2) = 1,000,000 // 100x bigger

n = 10000, O(10n) = 100,000, O(n^2) = 100,000,000 // 1000x bigger
_and so on..._

```
function sum_char_codes(n: string): number {
    let sum = 0;
    for (let i = 0; i < n.length; ++i) {
        const charCode = n.charCodeAt(i)
        // Capital E
        if (charCode === 69) {
            return sum;
        }

        sum += charCode;
    }

    return sum;
}
```

In BigO we often consider the worst case scenario

The example above is _O(n)_

![Big-O Complexity Chart](https://paper-attachments.dropbox.com/s_2D428973624E7FC84C7D69D11421DE762BEA6B6F3361231FCDCAE0425D14526F_1664885448372_Untitled.drawio+17.png)

### O(n^2)

```
function sum_char_codes(n: string): number {
    let sum = 0;
    for (let i = 0; i < n.length; ++i) {
        for(let j = 0; j < n.length; ++j) {
            sum += 1;
        }
    }

    return sum;
}
```

### O(n^3)

```
function sum_char_codes(n: string): number {
    let sum = 0;
    for (let i = 0; i < n.length; ++i) {
        for(let j = 0; j < n.length; ++j) {
            for(let k = 0; k < n.length; ++k) {
                sum += 1;
            }
        }
    }
    return sum;
}
```

### O(n log n)

Quicksort

### O(log n)

Binary search trees

### O(sqrt(n))
