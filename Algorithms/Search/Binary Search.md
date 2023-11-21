#algorithm
## Can we get a faster search?

Are we searching in a data set that's ordered? If our data set is ordered we can search faster then in an unordered set.

That's because we can potentially eliminate the need to go element by element.

# Binary Search

## Process

- Choose the middle value of the data set.

- If it equals the target value, the search is successful.

- If the target value is greater, ignore the left half; if less, ignore the right half.

- Repeat the process with the halved data set until the target is found or no more entries to halve.

## Pseudo-code

```typescript
arr = data set to search
target = value to find

search(arr, target)
    lo = 0
    hi = arr.length

    do this:
        midpoint = lo + Math.floor((hi - lo) / 2); // subtract the hi bound by the lo bound

        v = arr[midpoint];

        if target = v // if we find the target...
            return midpoint; // return the index where we found the target

        else if target < then v // if the elemen is smaller than the midpoint...
            lo = midpoint + 1; // then the target could only exist in the left subarray

        else // else...
            hi = midpoint; // it has to exist in the right subarray
        
    then, while lo < hi, loop this block of code // if lo is more than or equal to hi then we couldn't find the target!

    return 0;
```

We could also recursively divide the data set until either the target value is found or there are no more entries to halve.

## Implementation

```typescript
export default function bin_search(haystack: number[], needle: number): number{
    let lo = 0
    let hi = haystack.length;
    do {
        const midpoint = lo + Math.floor((hi - lo) / 2);
        const v = haystack[midpoint];

        if (v === needle) {
            return midpoint;
        } else if (v > needle) {
            hi = midpoint;
        } else {
            lo = midpoint + 1;
        }
    } while (lo < hi);

    return 0;
}
```

## Big O

O(log n). The data set is halved a logarithmic number of times until the value is found.

The input is halved at each step, indicating a time complexity of O(log n) or O(n log n). The efficiency of the binary search lies in reducing the search space exponentially.

### Note

**If the input halves at each step, it's likely O(log n) or O(n log n)**

The success of binary search relies on the ordered nature of the data set, enabling efficient elimination of irrelevant portions.