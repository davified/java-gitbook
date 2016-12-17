# Arrays

An array is a fixed-size sequential collection of elements of the same type. An array is used to store a collection of data, but it is often more useful to think of an array as a collection of variables of the same type.

### Declaring an array

```
dataType[] arrayRefVar;   // preferred way
dataType[] arrayRefVar = new dataType[arraySize];
dataType[] arrayRefVar = {value0, value1, ..., valuek};
```

### Class (static) methods in the Array class
To use Array static methods, you must import the Array class
```
import java.util.Arrays
```

#### Arrays.toString(arr)
This is useful in printing the array to stdout:
```
System.out.println(Arrays.toString(arr));
```

#### public static int binarySearch(Object[] a, Object key)
Searches the specified array of Object ( Byte, Int , double, etc.) for the specified value using the binary search algorithm. The array must be sorted prior to making this call. This returns index of the search key, if it is contained in the list; otherwise, it returns ( – (insertion point + 1)).

#### public static boolean equals(long[] a, long[] a2)
Returns true if the two specified arrays of longs are equal to one another. Two arrays are considered equal if both arrays contain the same number of elements, and all corresponding pairs of elements in the two arrays are equal. This returns true if the two arrays are equal. Same method could be used by all other primitive data types (Byte, short, Int, etc.)

#### public static void fill(int[] a, int val)
Assigns the specified int value to each element of the specified array of ints. The same method could be used by all other primitive data types (Byte, short, Int, etc.). Example:

```
int[] arr = new int[3];
Arrays.fill(arr, 10);
```

#### public static void sort(Object[] a)
Sorts the specified array of objects into an ascending order, according to the natural ordering of its elements. The same method could be used by all other primitive data types ( Byte, short, Int, etc.)
