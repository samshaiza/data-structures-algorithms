# Problem

Given two crystal balls that will break if dropped from a high enough distance, determine the exact spot in which it will break in the most optimized way.

## What's problem asking?

We're given an array of `falses` up until a point that is `true`, and from that point onwards it will always return `true`. Find the first instance of true.

Which is a better algorithm to solve this problem? Linear search or binary search?

## How to solve

In linear search we have to traverse our array from the beginning to the end until we reach our desired result. This would work well to find the first instance of true, but it will be O(n) time.

Well how about binary search?! Our data is ordered, from false to true, so we run a binary search we can find the first instance of true.

While our data set is indeed ordered, a problem occurs. What if we grab the midpoint of the array and it returns true? Though that is the value we want how do we know that it's the first one? If it isn't, which subarray would we go to? The left or the right?

What if we could combine both the benefits from linear search and binary search? If we find a point in where we find a true value then we can linear search through the lo and hi bounds.

That's a really good idea! But, we don't really get any added benefit with the binary search addition. Because we have linear search it'd still be constant time.

If we could jump through the array, walk through the subarray and find the first true value, we'd find our first true.

Let's do the square root of n

## Big O

O(sqrt(n))