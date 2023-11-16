# Linear Search

The most simple form of search

## How does it work?

A linear search traverses an array to _search_ for a target value. One by one, we check whether or not an element of an index is that target value. If not, move to the next index.

The `indexOf()` function in JavaScript and Java does this, as does the `index()` method in Python as well.

## Big O

O(n)

As the array grows, so does the time it takes to run (in the worst-case scenario).

## Implementation

```typescript
export default function linearSearch(
  haystack: number[],
  needle: number
): boolean {
  for (let i = 0; i < haystack.length; ++i) {
    if (haystack[i] === needle) {
      return true;
    }
  }

  return false;
}
```
