## Can we get a faster search?

Are we searching in a data set that's ordered? If our data set is ordered we can have new advantages.

If we have an ordered data set, we don't have to go element by element to find our desired target.

Because our data set is ordered, we have some hints as to where out target value is at.

# Binary Search

Choose the value in the middle of the data set. If that value equals our target value we win. Yay! Otherwise, If our target value is more then the middle value then we know that the first half of the data set has no relevence for our search and we will ignore it. If it's less then the middle value. The same goes, the right half of the data set will be ignored.

With our halved data set we'll do the same thing. Get the middle value. Compare it with our target value. Target value is more then the middle value? Move to the right side of the set. Less then? Left side.

## Pseudocode
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

We can do this recursively until either there is no more entries to halve, or we found our value.

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

O(log n)

Until we find our value, we'll half the the data set.

We are halving a log * the length of the data set amount of times.

**If the input halves at each step, it's likely O(log n) or O(n log n)**