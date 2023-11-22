#data-structure  
## Definition

An array is a contiguous structure in which data is stored together in memory (RAM).

Each element in an array is located next to one or two other elements. This makes them fixed in size and unable to grow.

This implies that array's size (memory allocated) must be set on initialize.
p
## Memory Layout

```typescript
let a: int = new Array[3](); // Create 3 integers in contiguous space
```

Let's say `a[0]` is at memory location 1000. An integer takes up 4 bytes of memory, so my second element `a[1]` will be located at 1004. `a[2]` is at 1008, etc.

To access an element in an array, we use the index of that element.

## What is an index?

The index is an integer that represents the position of the element in the array, which in turn is used to calculate the memory address of the element so we can access it directly.

`memory address = base address + (index * size of data type)`

## Getting at specific index

Take the size of the data type and multiply it by the offset. Put it at the memory address and grab the element.

```typescript
a[0]; // Go to the memory address of 'a' then multiply the offset of zero multipied by how big this array's type.
```

The data type of the `a` array is an integer.

1. Integers use 4 bytes of data.
2. The offset (index) is zero.
3. Multiply the the size (4 bytes) and the offset (0) to get 0.
4. The position of `a` in memory is at 1000 so to find the element add 0 to 1000 to find `a[0]` and return it's value.

## Insertion at specific index

Overwrite at index by finding the address of the element and replacing the value by the target value.

## Deletion at specific index

Like insertion, except we overwrite with a null or 0 value.

## What's the Big O time complexity of getting a value from an array?

Does getting at a specific index grow from the size of an array?

## Big O

Time complexity: O(1) (constant time).

Accessing an element's index is done in constant time using the subscript of the element.
