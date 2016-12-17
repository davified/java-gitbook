# Hashmap

### Creating a HashMap
```HashMap<Integer, String> myHashMap = new HashMap<Integer, String>();
```

### Key class methods

* `put(KeyType key, ValueType value)` add key value pair
```hmap.put(12, "Chaitanya");
```
* `get(key)` retrieve value by key

```hmap.get(2);
// or
hmap.get(myKey);
```

* `remove(key)` remove key-value pair by key

```hmap.remove(3);
```

* `void clear()` It removes all the key and value pairs from the specified Map.
* `Object clone()` It returns a copy of all the mappings of a map and used for cloning them into another map.
* `boolean containsKey(Object key)` It is a boolean function which returns true or false based on whether the specified key is found in the map.
* `boolean containsValue(Object Value)` Similar to containsKey() method, however it looks for the specified value instead of key.
* `Value get(Object key)` It returns the value for the specified key.
* `boolean isEmpty()` It checks whether the map is empty. If there are no key-value mapping present in the map then this function returns true else false.
* `Set keySet()` It returns the Set of the keys fetched from the map.
* `value put(Key k, Value v)` Inserts key value mapping into the map. Used in the above example.
* `int size()` Returns the size of the map – Number of key-value mappings.
* `Collection values()` It returns a collection of values of map.
* `Value remove(Object key)` It removes the key-value pair for the specified key. Used in the above example.
void putAll(Map m): Copies all the elements of a map to the another specified map.

### Displaying content (using iterator)
```
import java.util.Iterator;
/* Display content using Iterator*/
      Set set = hmap.entrySet();
      Iterator iterator = set.iterator();
      while(iterator.hasNext()) {
         Map.Entry mentry = (Map.Entry)iterator.next();
         System.out.print("key is: "+ mentry.getKey() + " & Value is: ");
         System.out.println(mentry.getValue());
      }
```
