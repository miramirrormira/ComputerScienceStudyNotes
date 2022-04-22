# Swift Language

## Array
In other languages, slicing an array will create a new array. But in swift, slicing an array will create an ArraySlice. ArraySlice is a view on arrays, it's backed by the original array. As a result, creating a slice is cheap, the array elements doesn't get copied.
