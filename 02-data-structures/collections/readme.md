# Collections

![collections](/img/collections.png)
*interfaces are denoted in yellow*

### Java Collections in a nutshell

The Java Collections Framework is a collection of interfaces and classes which helps in storing and processing the data efficiently. This framework has several useful classes which have tons of useful functions which makes a programmer task super easy.

The Java Collections Framework has a data structure that should work for virtually anything you'll ever need to do (no need to write your own implentation of quicksort!). Want to keep a list that you can easily keep adding to? Want to find something by name? Want to create a list that automatically takes out all the duplicates? Collections API gives us tried and tested methods for these!

The Collections Framework gives us three main interfaces (List, Set and Map) and nine classes:
List:
  * ArrayList: the collection that you’ll probably use most often.
  * LinkedList: Designed to give better performance when you insert or delete elements from the middle of the collection. (In practice, an ArrayList is still usually what you want.)
  * Vector: Vectors implements the list interface and it has all the same methods as ArrayLists, except for two differences: (1) Vectors are synchronised, so multiple threads can manipulate the content of a Vector without any inconsistency; (2) Vectors contain many legacy methods that are not part of the Collections framework (e.g. capacityIncrement, which automatically increments the size of a Vector everytime it fails and is re-instantiated)
    * Stack (extends Vector class): Stack is a Vector, List, Collection and Iterable all at once! A stack is a data structure where you can add/remove elements to/from the top of the "stack". (LIFO - last in first out). Stacks can be used in graph traversal with depth-first search

Queue (FIFO):
  * PriorityQueue
  * ArrayDeque
  * [LinkedList]


Set:
  * HashSet: Prevents duplicates in the collection, and given an element, can find that element in the collection quickly. Use this when it’s important to ensure that there are no duplicates. (not efficient for large N because the hashing algorithm could result in multiple objects having the same hashCode. Not good.) (For a full explanation of the weaknesses of Hash Sets, see p. 563 of Head First Java)
  * TreeSet: keeps the collection sorted and prevents duplicates
  * LinkedHashSet: LinkedHashSet is similar to the HashSet and TreeSet except for 3 differences:
    * LinkedHashSet maintains the insertion order. Elements gets sorted in the same sequence in which they have been added to the Set.
    * HashSet doesn’t maintain any kind of order of its elements.
    * TreeSet sorts the elements in ascending order.

Map:
  * HashMap: like an object/dictionary. Lets you store and access elements as key-value pairs
  * LinkedHashMap: Like a regular HashMap, except it can remember the order in which elements (name/value pairs) were Inserted, or it can be configured to remember the order In which elements were last accessed.

The collections framework was designed to meet several goals, such as −
* The framework had to be high-performance. The implementations for the fundamental collections (dynamic arrays, linked lists, trees, and hashtables) were to be highly efficient.
* The framework had to allow different types of collections to work in a similar manner and with a high degree of interoperability.
* The framework had to extend and/or adapt a collection easily.

Towards this end, the entire collections framework is designed around a set of standard interfaces. Several standard implementations such as LinkedList, HashSet, and TreeSet, of these interfaces are provided that you may use as-is and you may also implement your own collection, if you choose.

A collections framework is a unified architecture for representing and manipulating collections. All collections frameworks contain the following −
* Interfaces − These are abstract data types that represent collections. Interfaces allow collections to be manipulated independently of the details of their representation. In object-oriented languages, interfaces generally form a hierarchy.
  * For example, the Collections framework extends the java.lang.Iterable interface (that's why we can use the foreach loop). This is what going on behind the scenes in a foreach loop:
  ```
  List<String> list = Arrays.asList("Joe", "Adam");
  Iterator<String> iterator = list.iterator();
  while (iterator.hasNext()) {
    System.out.println(iterator.next());
  }
  ```
* Implementations, i.e., Classes − These are the concrete implementations of the collection interfaces. In essence, they are reusable data structures.
* Algorithms − These are the methods that perform useful computations, such as searching and sorting, on objects that implement collection interfaces. The algorithms are said to be polymorphic: that is, the same method can be used on many different implementations of the appropriate collection interface.

In addition to collections, the framework defines several **map interfaces and classes**. Maps store key/value pairs. Although maps are not collections in the proper use of the term, but they are fully integrated with collections.
