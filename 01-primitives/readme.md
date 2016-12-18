# Primitives

8 Primitive data types

* **byte**: The byte data type is an 8-bit signed two's complement integer. It has a minimum value of -128 and a maximum value of 127 (inclusive). The byte data type can be useful for saving memory in large arrays, where the memory savings actually matters. They can also be used in place of int where their limits help to clarify your code; the fact that a variable's range is limited can serve as a form of documentation.
* **short**: The short data type is a 16-bit signed two's complement integer. It has a minimum value of -32,768 an**d a maximum value of 32,767 (inclusive). As with byte, the same guidelines apply: you can use a short to save memory in large arrays, in situations where the memory savings actually matters.
* **int**: By default, the int data type is a 32-bit signed two's complement integer, which has a minimum value of -231 and a maximum value of 231-1. In Java SE 8 and later, you can use the int data type to represent an unsigned 32-bit integer, which has a minimum value of 0 and a maximum value of 232-1. Use the Integer class to use int data type as an unsigned integer. See the section The Number Classes for more information. Static methods like compareUnsigned, divideUnsigned etc have been added to the Integer class to support the arithmetic operations for unsigned integers.
* **long**: The long data type is a 64-bit two's complement integer. The signed long has a minimum value of -263 and a maximum value of 263-1. In Java SE 8 and later, you can use the long data type to represent an unsigned 64-bit long, which has a minimum value of 0 and a maximum value of 264-1. Use this data type when you need a range of values wider than those provided by int. The Long class also contains methods like compareUnsigned, divideUnsigned etc to support arithmetic operations for unsigned long.
* **float**: The float data type is a single-precision 32-bit IEEE 754 floating point. Its range of values is beyond the scope of this discussion, but is specified in the Floating-Point Types, Formats, and Values section of the Java Language Specification. As with the recommendations for byte and short, use a float (instead of double) if you need to save memory in large arrays of floating point numbers. This data type should never be used for precise values, such as currency. For that, you will need to use the java.math.BigDecimal class instead. Numbers and Strings covers BigDecimal and other useful classes provided by the Java platform.
* **double**: The double data type is a double-precision 64-bit IEEE 754 floating point. Its range of values is beyond the scope of this discussion, but is specified in the Floating-Point Types, Formats, and Values section of the Java Language Specification. For decimal values, this data type is generally the default choice. As mentioned above, this data type should never be used for precise values, such as currency.
* **boolean**: The boolean data type has only two possible values: true and false. Use this data type for simple flags that track true/false conditions. This data type represents one bit of information, but its "size" isn't something that's precisely defined.
* **char**: The char data type is a single 16-bit Unicode character. It has a minimum value of '\u0000' (or 0) and a maximum value of '\uffff' (or 65,535 inclusive).

* **String** In addition to the eight primitive data types listed above, the Java programming language also provides special support for character strings via the java.lang.String class. Enclosing your character string within double quotes will automatically create a new String object.

Converting data types:
* Integer.parseInt(String s) (convert to int)
* Double.parseDouble(String s) (convert to double)
* Long.parseLong(String s) (convert to long value)

### Integer methods

### String methods
Usage:

```
String str = "some kind of string";
str.someMethod(someArgs);
```

* `char charAt(int index)`: It returns the character at the specified index. Specified index value should be between 0 to length() -1 both inclusive. It throws IndexOutOfBoundsException if index<0||>= length of String.
* `int codePointAt(int index)`: It is similar to the charAt method however it returns the Unicode code point value of specified index rather than the character itself.
* `void getChars(int srcBegin, int srcEnd, char[] dest, int destBegin)`: It copies the characters of src array to the dest array. Only the specified range is being copied(srcBegin to srcEnd) to the dest subarray(starting fromdestBegin).
* `boolean equals(Object obj)`: Compares the string with the specified string and returns true if both matches else false.
* `boolean contentEquals(StringBuffer sb)`: It compares the string to the specified string buffer.
* `boolean equalsIgnoreCase(String string)`: It works same as equals method but it doesn’t consider the case while comparing strings. It does a case insensitive comparison.
* `int compareTo(String string)`: This method compares the two strings based on the Unicode value of each character in the strings.
* `int compareToIgnoreCase(String string)`: Same as CompareTo method however it ignores the case during comparison.
* `boolean regionMatches(int srcoffset, String dest, int destoffset, int len)`: It compares the substring of input to the substring of specified string.
* `boolean regionMatches(boolean ignoreCase, int srcoffset, String dest, int destoffset, int len)`: Another variation of regionMatches method with the extra boolean argument to specify whether the comparison is case sensitive or case insensitive.
* `boolean startsWith(String prefix, int offset)`: It checks whether the substring (starting from the specified offset index) is having the specified prefix or not.
* `boolean startsWith(String prefix)`: It tests whether the string is having specified prefix, if yes then it returns true else false.
* `boolean endsWith(String suffix)`: Checks whether the string ends with the specified suffix.
* `int hashCode()`: It returns the hash code of the string.
* `int indexOf(int ch)`: Returns the index of first occurrence of the specified character ch in the string.
* `int indexOf(int ch, int fromIndex)`: Same as indexOf method however it starts searching in the string from the specified fromIndex.
* `int lastIndexOf(int ch)`: It returns the last occurrence of the character ch in the string.
* `int lastIndexOf(int ch, int fromIndex)`: Same as lastIndexOf(int ch) method, it starts search from fromIndex.
* `int indexOf(String str)`: This method returns the index of first occurrence of specified substring str.
* `int lastindexOf(String str)`: Returns the index of last occurrence of string str.
* `String substring(int beginIndex)`: It returns the substring of the string. The substring starts with the character at the specified index.
* `String substring(int beginIndex, int endIndex)`: Returns the substring. The substring starts with character at beginIndex and ends with the character at endIndex.
* `String concat(String str)`: Concatenates the specified string “str” at the end of the string.
* `String replace(char oldChar, char newChar)`: It returns the new updated string after changing all the occurrences of oldChar with the newChar.
* `boolean contains(CharSequence s)`: It checks whether the string contains the specified sequence of char values. If yes then it returns true else false. It throws NullPointerException of ‘s’ is null.
* `String replaceFirst(String regex, String replacement)`: It replaces the first occurrence of substring that fits the given regular expression “regex” with the specified replacement string.
* `String replaceAll(String regex, String replacement)`: It replaces all the occurrences of substrings that fits the regular expression regex with the replacement string.
* `String[] split(String regex, int limit)`: It splits the string and returns the array of substrings that matches the given regular expression. limit is a result threshold here.
* `String[] split(String regex)`: Same as split(String regex, int limit) method however it does not have any threshold limit.
* `String toLowerCase(Locale locale)`: It converts the string to lower case string using the rules defined by given locale.
* `String toLowerCase()`: Equivalent to toLowerCase(Locale. getDefault()).
* `String toUpperCase(Locale locale)`: Converts the string to upper case string using the rules defined by specified locale.
* `String toUpperCase()`: Equivalent to toUpperCase(Locale.getDefault()).
* `String trim()`: Returns the substring after omitting leading and trailing white spaces from the original string.
* `char[] toCharArray()`: Converts the string to a character array.
* `static String copyValueOf(char[] data)`: It returns a string that contains the characters of the specified character array.
* `static String copyValueOf(char[] data, int offset, int count)`: Same as above method with two extra arguments – initial offset of subarray and length of subarray.
* `static String valueOf(data type)`: This method returns a string representation of specified data type.
* `byte[] getBytes(String charsetName)`: It converts the String into sequence of bytes using the specified charset encoding and returns the array of resulted bytes.
* `byte[] getBytes()`: This method is similar to the above method it just uses the default charset encoding for converting the string into sequence of bytes.
* `int length()`: It returns the length of a String.
* `boolean matches(String regex)`: It checks whether the String is matching with the specified regular expression regex.


https://docs.oracle.com/javase/7/docs/api/java/lang/String.html

#### StdOut.printf()
To print out a string that has mixed data types, you can use string format:
* %f - floating points
* %d - integers
* %s - strings
* %c - characters
Example:
```
System.out.printf("hello %3.9f, %d, %s, and %c", Math.PI, 100, "hello", 'ho');
```
