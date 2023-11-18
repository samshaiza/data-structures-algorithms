# Bubble Sort

How do we know an array is sorted?

It's a really simple formula that applies to an entire data set. `x[i] <= x[i + 1]`

## How bubble sort works

An element looks at the the element next to it and checks if that element is bigger then itself. If true swap positions. If not don't swap positions. Afterwards move on to the next element and run the same check.

With this algorithm we know that the number at the end of the data set will be the largest number of the set. This means when we iterate through the array, we can ignore the last number of the set.

We loop through the entire data set and begin again at the start of the data set. The data set we iterate through should decrease in length by 1 everytime wecycle through it. Only when there were no swaps done in the itereation of a bubble sort, we know that the array is completely sorted.

## Implementation

```typescript
export default function bubble_sort(arr: numbers[]): {
    let swapped: boolean;
    for (let j = 0; )
    
}
```

## Big O

O(n^2)