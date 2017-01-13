# ArrayList

Why we should love ArrayLists:
* random access / accessing items by the index (e.g. list.get(0)) - O(1)
* All operations run at O(N) time approximately

But there are some downsides to using ArrayLists:
* But if we want to remove items, we'd have to shift each item in our list - O(N)
  * If our application is just about adding elements to a list and getting elements with known indexes, then ArrayList is perfect for the job.

When to use ArrayLists?
  * We should use ArrayLists for "add-heavy" applications
### Initializing ArrayLists
Method 1: Initialization using Arrays.asList

```

ArrayList<Type> obj = new ArrayList<Type>(
        Arrays.asList(Object o1, Object o2, Object o3, ....so on));
```

Method 2: Anonymous inner class method to initialize ArrayList
```
ArrayList<T> obj = new ArrayList<T>(){{
		   add(Object o1);
		   add(Object o2);
		   add(Object o3);
                   ...
                   ...
		   }};
```

Method 3: Normal way of ArrayList initialization (use `.add(‘x’)` after initializing the array)

Method 4: Use Collections.ncopies  (`ArrayList<T> obj = new ArrayList<T>(Collections.nCopies(count, element));`)

```
public class Details {
   public static void main(String args[]) {
	   ArrayList<Integer> intlist = new ArrayList<Integer>(Collections.nCopies(10, 5));
	  System.out.println("ArrayList items: "+intlist);
   }
} // → ArrayList items: [5, 5, 5, 5, 5, 5, 5, 5, 5, 5]
```


### Key methods:
* Retrieving length of ArrayList `.size()`
```
int numberofitems = obj.size();
```

* Retrieving values by index `.get(i)`
```
String str= obj.get(2);
```

* Checking if element exists `.contains()`
```
obj.contains("Steve"); //returns a boolean value
```

* Adding and removing elements
```
obj.add(‘x’)
obj.remove(‘x’)
```

* Adding/Removing element by index

```
obj.add(0, "Rahul");
obj.remove(3); When given an integer, .remove() will read it as an index
obj.set(2, "Tom"); this replaces the element at the given index
```

* Getting index of element
```
int pos = obj.indexOf("Tom");
```

* Emptying the arraylist
```
obj.clear(); //remove everything from the arraylist
```

### Looping
Apart from for, forEach and while, we can also use the iterator

```
Iterator iter = arrlist.iterator();
      while (iter.hasNext()) {
         System.out.println(iter.next());
      }
```

We can also use the Enumerator interface
```
import java.util.Enumeration;
// Get the Enumeration object
      Enumeration<String> e = Collections.enumeration(arrayList);

      // Enumerate through the ArrayList elements
      System.out.println("ArrayList elements: ");
      while(e.hasMoreElements())
      System.out.println(e.nextElement());

```
### Sorting

* Sorting strings and numbers - `.sort()`
* Reversing the sort: call .sort() and then .reverse()
* Sorting objects using Comparable:

```
public class Student implements Comparable {
    private String studentname;
    private int rollno;
    private int studentage;

    public Student(int rollno, String studentname, int studentage) {
        this.rollno = rollno;
        this.studentname = studentname;
        this.studentage = studentage;
    }
    //getter and setter methods same as the above example

    @Override
    public int compareTo(Student comparestu) {
        int compareage=((Student)comparestu).getStudentage();
        /* For Ascending order*/
        return this.studentage-compareage;

        /* For Descending order do like this */
        //return compareage-this.studentage;
    } // after doing this, we can then call Collections.sort(arraylist);

    @Override
    public String toString() {
        return "[ rollno=" + rollno + ", name=" + studentname + ", age=" + studentage + "]";
    }

}

```

* Sorting objects based on multiple properties with Comparator

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

    ...

    //Getter and setter methods same as the above examples

    ...

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

### Comparing two ArrayLists
You have to loop through one array and use the .contains(Object o) method within the for loop
.contains(...) returns true if the list contains the Object o else it returns false.
```
for (String temp : al1)
              al3.add(al2.contains(temp) ? "Yes" : "No");
          System.out.println(al3);
```

### Other frequently-used Collections class methods:

* Swapping the position of two elements in an ArrayList `Collections.swap(ist list, int i1, int i2) `
```
This method swaps the element of index i1 with the element of index i2.
// Example:
Collections.swap(al, 1, 4);
```

* toString()
When we are dealing with ArrayList of Objects then it is must to Override the `toString()` method in order to get the output in desired format.
Otherwise, using toString() will return this: `loremipsum.com.Student@10b28f30`

* Join/combine two ArrayLists `.addAll()`
```
arraylist3.addAll(arraylist1);
arraylist3.addAll(arraylist2);
```

* Clone an ArrayList to another ArrayList
```
ArrayList<String> al = new ArrayList<String>();
// add stuff to it
ArrayList<String> al2 = (ArrayList<String>)al.clone();
```

* Empty an arraylist

```
ArrayList.clear() // Method 1. recommended. Time complexity O(N)
al1.clear();

ArrayList.removeAll()  // Method 2. Time complexity O(N2)
al2.removeAll(al2);
```

* Check if an array is empty - `al2.isEmpty();`

* Memory optimisation - `al.trimToSize() `
If the array had the initial size of 50, but only has 5 elements now, you can call trimToSize() to free up the memory
Converting ArrayList to String[]

* synchronize() ArrayList (i skipped this)
