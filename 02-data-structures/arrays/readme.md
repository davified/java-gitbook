# Arrays

An array is a fixed-size sequential collection of elements of the same type. An array is used to store a collection of data, but it is often more useful to think of an array as a collection of variables of the same type.

### Declaring an array

```
dataType[] arrayRefVar;   // preferred way
dataType[] arrayRefVar = new dataType[arraySize];
dataType[] arrayRefVar = {value0, value1, ..., valuek};

// nested arrays
dataType[][] arrayRefVar = {{value0, value1}, {value0, value1} ..., {value0, value1}};
```

#### Class (static) methods in the Array class
To use Array static methods, you must import the Array class
```
import java.util.Arrays
```

##### Commonly used methods
Here are some commonly used methods. Note that the application of each method will differ according to the type and number of arguments passed in. I have only included one particular application for each method, for brevity. For a full list of methods and implementations, please refer to [java docs](https://docs.oracle.com/javase/7/docs/api/java/util/Arrays.html).

* Arrays.toString(arr)
  * This is useful in printing the array to stdout:
```
System.out.println(Arrays.toString(arr));
```

* Arrays.binarySearch(Object[] a, Object key)
  * Searches the specified array of Object ( Byte, Int , double, etc.) for the specified value using the binary search algorithm. The array must be sorted prior to making this call. This returns index of the search key, if it is contained in the list; otherwise, it returns ( – (insertion point + 1)).

* Arrays.equals(long[] a, long[] a2)
  * Returns true if the two specified arrays of longs are equal to one another. Two arrays are considered equal if both arrays contain the same number of elements, and all corresponding pairs of elements in the two arrays are equal. This returns true if the two arrays are equal. Same method could be used by all other primitive data types (Byte, short, Int, etc.)

* Arrays.deepEquals(Object[] a1, Object[] a2)
  * Returns true if the two specified arrays are deeply equal to one another. Unlike the equals(Object[],Object[]) method, this method is appropriate for use with nested arrays of arbitrary depth
  * Two array references are considered deeply equal if both are null, or if they refer to arrays that contain the same number of elements and all corresponding pairs of elements in the two arrays are deeply equal.

* Arrays.fill(int[] a, int val)
  * Assigns the specified int value to each element of the specified array of ints. The same method could be used by all other primitive data types (Byte, short, Int, etc.). Example:

```
int[] arr = new int[3];
Arrays.fill(arr, 10);
```

* Arrays.sort(Object[] a)
  * Sorts the specified array of objects into an ascending order, according to the natural ordering of its elements. The same method could be used by all other primitive data types ( Byte, short, Int, etc.)

* Arrays.copyOf(boolean[] original, int newLength)
  * Copies the specified array, truncating or padding with zeros (if necessary) so the copy has the specified length. For all indices that are valid in both the original array and the copy, the two arrays will contain identical values. For any indices that are valid in the copy but not the original, the copy will contain 0. Such indices will exist if and only if the specified length is greater than that of the original array.

* Arrays.copyOfRange(int[] original, int from, int to)
  * `original` - the array from which a range is to be copied; `from` - the initial index of the range to be copied, inclusive; `to` - the final index of the range to be copied, exclusive. (This index may lie outside the array.)
  * Copies the specified range of the specified array into a new array. The initial index of the range (from) must lie between zero and original.length, inclusive. The value at original[from] is placed into the initial element of the copy (unless from == original.length or from == to). Values from subsequent elements in the original array are placed into subsequent elements in the copy. The final index of the range (to), which must be greater than or equal to from, may be greater than original.length, in which case 0 is placed in all elements of the copy whose index is greater than or equal to original.length - from. The length of the returned array will be to - from.

* Arrays.asList("Larry", "Moe", "Curly");
  * Returns a fixed-size list backed by the specified array. (Changes to the returned list "write through" to the array.) This method acts as bridge between array-based and collection-based APIs, in combination with Collection.toArray(). The returned list is serializable and implements RandomAccess.
