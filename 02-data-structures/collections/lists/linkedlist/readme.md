# LinkedLists

What are LinkedLists?
* LinkedList uses references (->). In a single linkedlist, each item stores its own data/value and has a reference to the next item. Java also implements a doubly linkedlist, where each item has additionally a reference to the previous item as well.
* LinkedLists implement 3 interfaces - List, Queue and Deque (see image below)
![collections](../../img/collections.png)
* Pros
  * We can remove items very efficiently because we only need to update the reference/pointers and we don't have to shift the other items - O(1) (however, retrieving that element will be O(N))
* Cons
  * No random access! To retrieve an element, we have to sequentially search through the whole list - O(N)
  * Not synchronised. If multiple threads manipulate the same linkedlist, we have to make some synchronisation

When to use LinkedList?
* We should use LinkedList for remove-heavy applications


### Initializing LinkedLists
```
LinkedList<String> linkedlist = new LinkedList<String>();
```


### Key methods:
* Return the number of elements of the list - `int size()`
```
llistobj.size();
```

* adding elements to the linked list `.add()`
```
linkedlist.add("Item1");
```

* Display Linked List Content
```
System.out.println("Linked List Content: " +linkedlist);
```

* Add First and Last Element - `.addFirst()` and `.addLast()`
```
linkedlist.addFirst("First Item");
linkedlist.addLast("Last Item");
```

* Remove first and last element - `.removeFirst()` and `.removeLast()`
```
linkedlist.removeFirst();
linkedlist.removeLast();
System.out.println("LinkedList after deletion of first and last element: " +linkedlist);
```

* Get and set Values - `.get()` and `.set()`
```
Object firstvar = linkedlist.get(0);
linkedlist.set(0, "Changed first item");
Object firstvar2 = linkedlist.get(0); // show new value
```

* Add to a Position and remove from a position - `.add()` and `.remove()`
```
linkedlist.add(0, "Newly added item");
linkedlist.remove(2);
System.out.println("Final Content: " +linkedlist);
linkedlist.add("hello");  // calling .add() without an integer will add it to the end of the list.
```

* All all the elements of the specified collection c to the list - `.addAll(Collection c)`
```
LinkedList<String> llistobj = new LinkedList<String>();
ArrayList<String> arraylist= new ArrayList<String>();
arraylist.add("String1");
arraylist.add("String2");
llistobj.addAll(arraylist);

Note: Calling .addAll() with an index (i.e. addAll(int index, Collection c)) adds all the elements of collection c to the list starting from a give index in the list. It throws NullPointerException if the collection c is null and IndexOutOfBoundsException when the specified index is out of the range.
```

* Remove all the elements of a list - `.clear()`
```
llistobj.clear();
```

* Return the copy of the list - .clone()

```
Object str= llistobj.clone();
System.out.println(str);
```

* Check whether the given item is present in the list or not - `contains(Object item)`
```
boolean var = llistobj.contains("TestString");
```

* Return the index of the specified item. `indexOf(Object item)` and `lastIndexOf("hello)`
```
llistobj.indexOf("bye");
llistobj.lastIndexOf("hello);
```

* Remove the first/last occurrence of the specified item - `removeFirstOccurrence(Object item)` / `removeLastOccurrence(Object item)`

```
llistobj.removeFirstOccurrence("text");
```

* Return and remove the first item of the list (`poll()` and `pollFirst()`). Another variation is `pollLast()`, which returns and removes the last element of the list.

```
Object o = llistobj.poll();
Object o = llistobj.pollFirst();
Object o = llistobj.pollLast();
```

### When to use LinkedList over ArrayList
LinkedList<E> allows for constant-time insertions or removals using iterators, but only sequential access of elements. In other words, you can walk the list forwards or backwards, but finding a position in the list takes time proportional to the size of the list. Javadoc says "operations that index into the list will traverse the list from the beginning or the end, whichever is closer", so those methods are O(n/4) on average, though O(1) for index = 0.

ArrayList<E>, on the other hand, allow fast random read access, so you can grab any element in constant time. But adding or removing from anywhere but the end requires shifting all the latter elements over, either to make an opening or fill the gap. Also, if you add more elements than the capacity of the underlying array, a new array (1.5 times the size) is allocated, and the old array is copied to the new one, so adding to an ArrayList is O(n) in the worst case but constant on average.

So depending on the operations you intend to do, you should choose the implementations accordingly. Iterating over either kind of List is practically equally cheap. (Iterating over an ArrayList is technically faster, but unless you're doing something really performance-sensitive, you shouldn't worry about this -- they're both constants.)

The main benefits of using a LinkedList arise when you re-use existing iterators to insert and remove elements. These operations can then be done in O(1) by changing the list locally only. In an array list, the remainder of the array needs to be moved (i.e. copied). On the other side, seeking in a LinkedList means following the links in O(n), whereas in an ArrayList the desired position can be computed mathematically and accessed in O(1).

Another benefit of using a LinkedList arise when you add or remove from the head of the list, since those operations are O(1), while they are O(n) for ArrayList. Note that ArrayDeque may be a good alternative to LinkedList for adding and removing from the head, but it is not a List.

### Time-complexity Comparison

| LinkedList | ArrayList |
|------------|-----------|
|`get(int index)` is O(n/4) average|`get(int index)` is O(1) <--- main benefit of ArrayList<E>|
|`add(E element)` is O(1)|`add(E element)` is O(1) amortized, but O(n) worst-case since the array must be resized and copied|
|`add(int index, E element)` is O(n/4) average (but O(1) when index = 0 <--- main benefit of LinkedList<E>)|`add(int index, E element)` is O(n/2) average|
|`remove(int index)` is O(n/4) average|`remove(int index)` is O(n/2) average|
|`Iterator.remove()` is O(1) <--- main benefit of LinkedList<E>|`Iterator.remove()` is O(n/2) average|
|`ListIterator.add(E element)` is O(1) <--- main benefit of LinkedList<E>|`ListIterator.add(E element)` is O(n/2) average|
|Note: O(n/4) is average, O(1) best case (e.g. index = 0), O(n/2) worst case (middle of list)|Note: O(n/2) is average, O(1) best case (end of list), O(n) worst case (start of list)|
