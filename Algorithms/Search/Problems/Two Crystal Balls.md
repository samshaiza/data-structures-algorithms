#dsa 
# Problem

Given two crystal balls prone to breaking from a sufficient height, find the exact spot of breakage in the most optimized way.

## What's problem asking?

Determine the first occurrence of `true` in an array that transitions from `false` to `true.`

Which is a better algorithm to solve this problem? [[Linear search]] or [[binary search]]?

## How to solve

In linear search we have to traverse our array from the beginning to the end until we reach our desired result. This would work well to find the first instance of true, but it will be O(n) time.

Well how about binary search?! Our data is ordered, from false to true, so we run a binary search we can find the first instance of true.

While our data set is indeed ordered, a problem occurs. What if we grab the midpoint of the array and it returns true? Though that is the value we want how do we know that it's the first one? If it isn't, which sub-array would we go to? The left or the right?

What if we could combine both the benefits from linear search and binary search? If we find a point in where we find a true value then we can linear search through the lo and hi bounds.

## Optimized approach

That's a really good idea! But, we don't really get any added benefit with the binary search addition. Because we have linear search it'd still be constant time.

Combine benefits of both linear search and binary search.

**Idea**: Jump through the array, navigate sub-array linearly, and find the first true.

Let's do the square root of n.

## Implementation

```typescript
export default function two_crystal_balls(breaks: boolean[]): number {
   const jmpAmount = Math.floor(Math.sqrt(breaks.length));
   let startAmount = jmpAmount;

   for (; startAmount < breaks.length; startAmount += jmpAmount) {
      if (breaks[startAmount]) {
         break;
      }
   }
   startAmount -= jmpAmount;

   for (
      let j = 0;
      j < jmpAmount && startAmount < breaks.length;
      ++j, ++startAmount
   ) {
      if (breaks[startAmount]) {
         return startAmount;
      }
   }
   return -1;
}
```

## Big O

O(sqrt(n)).

If we could jump through the array, walk through the sub-array and find the first true value, we'd find our first true.
