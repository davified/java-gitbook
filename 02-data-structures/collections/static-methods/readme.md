# Static methods in the Collections API

Here is a list of commonly used static methods in the Collections API (e.g. sort, binarySearch, min, max, etc). Please refer to the official [Collections API documentation](https://docs.oracle.com/javase/7/docs/api/java/util/Collections.html) for the full list of static methods.

* Swapping the position of two elements in an ArrayList
`Collections.swap(List list, int i1, int i2) `
```
This method swaps the element of index i1 with the element of index i2.
// Example:
Collections.swap(list, 1, 4);
```

* Adding all the specified elements to the specified collection. - `Collections.addAll(Collection<? super T> c, T... elements)`
```
List list = new ArrayList(Arrays.asList(1,2,3));
boolean b = Collections.addAll(list, 4,5,6);      
System.out.println(list); // returns 1,2,3,4,5,6
```

* Binary Search - `Collections.binarySearch(List<? extends T> list, T key)` or `binarySearch(List<? extends T> list, T key, Comparator<? super T> c)`

```
List<Integer> list = Arrays.asList(1,2,3,4,5,6,7,8,9,10);
    System.out.println(Collections.binarySearch(list, 5)); // returns index of number 5, which is 4.

// if you are searching through objects based on a given attribute, you will need to pass in a Comparator as the third argument
```

* Sort - `Collections.sort(List<T> list)` and `Collections.sort(List<T> list, Comparator<? super T> c)`
  * If we pass in a list as the only argument, this will sort the specified list into ascending order, according to the natural ordering of its elements.
  * If we pass in a comparator, it will sort the specified list according to the order induced by the specified comparator.
  * Example:

```
import java.util.Comparator;
public class Student  {
    private String studentname;
    private int rollno;
    private int studentage;

    public Student(int rollno, String studentname, int studentage) {
        this.rollno = rollno;
        this.studentname = studentname;
        this.studentage = studentage;
    }

    /*Comparator for sorting the list by Student Name*/

    public static Comparator<Student> StuNameComparator = new Comparator<Student>() {

	public int compare(Student s1, Student s2) {
	   String StudentName1 = s1.getStudentname().toUpperCase();
	   String StudentName2 = s2.getStudentname().toUpperCase();

	   //ascending order
	   return StudentName1.compareTo(StudentName2);

	   //descending order
	   //return StudentName2.compareTo(StudentName1);
    }};

    /*Comparator for sorting the list by roll no*/
    public static Comparator<Student> StuRollno = new Comparator<Student>() {

	public int compare(Student s1, Student s2) {

	   int rollno1 = s1.getRollno();
	   int rollno2 = s2.getRollno();

	   /*For ascending order*/
	   return rollno1-rollno2;

	   /*For descending order*/
	   //rollno2-rollno1;
   }};
    @Override
    public String toString() {
        return "[ rollno=" + rollno + ", name=" + studentname + ", age=" + studentage + "]";
    }
}


// having defined the comparator, we can then, in our main(), call the sort function with the comparators:
	   /*Sorting based on Student Name*/
	   System.out.println("Student Name Sorting:");
	   Collections.sort(arraylist, Student.StuNameComparator);

	   for(Student str: arraylist){
			System.out.println(str);
	   }

	   /* Sorting on Rollno property*/
	   System.out.println("RollNum Sorting:");
	   Collections.sort(arraylist, Student.StuRollno);
```

* Min and max - `Collections.max(Collection<? extends T> coll)`, `Collections.min(Collection<? extends T> coll)`, `Collections.max(Collection<? extends T> coll, Comparator<? super T> comp)` and `Collections.min(Collection<? extends T> coll, Comparator<? super T> comp)`
  * If we pass in just the collection as an argument, it returns the maximum element of the given collection, according to the natural ordering of its elements.
  * If we pass in a comparator, it will return the maximum element of the given collection, according to the order induced by the specified comparator.


* Copy all of the elements from one list into another - `Collections.copy(List<? super T> dest, List<? extends T> src)`
```
List<Integer> listDestination = new ArrayList();
List<Integer> listSource = new ArrayList(Arrays.asList(1,2,3));
Collections.copy(listDestination, listSource);
```

* Check if two specified collections have no elements in common - `Collections.disjoint(Collection<?> c1, Collection<?> c2)`
```
// Returns true if the two specified collections have no elements in common.
List<Integer> list1 = new ArrayList(Arrays.asList(4,5,6));
List<Integer> list2 = new ArrayList(Arrays.asList(1,2,3));
Collections.disjoint(list1, list2);
```

* Returns an iterator that has no elements - `Collections.emptyIterator()`

* Return empty immutable collections - `Collections.emptyList()`, `Collections.emptyMap()`, `Collections.emptySet()`

* Replace all of the elements of the specified list with the specified element. `Collections.fill(List<? super T> list, T obj)`

* Return the number of elements in the specified collection equal to the specified object. - `Collections.frequency(Collection<?> c, Object o)`

* Replace all occurrences of one specified value in a list with another - `Collections.replaceAll(List<T> list, T oldVal, T newVal)`

* Reverse the order of the elements in the specified list - `Collections.reverse(List<?> list)`
