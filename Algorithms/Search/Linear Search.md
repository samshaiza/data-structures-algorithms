# Linear Search

The most simple form of search

## Process

- Check each element of the array one by one.

- If the element at the current index is the target value, the search is successful.

- Move to the next index if the target value is not found.

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
