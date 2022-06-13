# TreeMap

## Learning Goals

- Explain a `TreeMap`
- Use common `TreeMap` methods

## What is a TreeMap?

A `TreeMap` is a data structure that guarantees the order of elements in the
structure. The sorting order is determined similar to the TreeSet discussed
previously. It’s determined by their natural order (`Comparable` interface
implementation) or a specific `Comparator` implementation.

## Common Methods

The `TreeMap` extends the `SortedMap` interface which extends the `Map`
interface and provides these additional methods:

- `E firstKey()`: returns the lowest key in the map.
- `E lastKey()`: returns the highest key in the map.
- `SortedMap<K, V> headMap(K toKey)`: returns a sub view of the map with
  elements whose keys are strictly less than `toKey`.
- `SortedMap<K, V> tailMap(fromKey)`: returns a sub view of the map with
  elements whose keys are greater than or equal to `fromKey`.
- `SortedMap<K, V> subMap(K fromKey, E toKey)`: returns a sub view of the map
  with elements whose keys are in the range `fromKey` (inclusive) to `toKey`
  (exclusive).

## Example

Let’s look at an example to better understand the `TreeMap`.

```java
import java.util.Comparator;
import java.util.TreeMap;

public class Example {
    public static void main(String[] args) {
        TreeMap<String, Integer> map = new TreeMap<>();
        map.put("Dragon Fruit", 4);
        map.put("Apple", 3);
        map.put("Cherry", 5);
        map.put("Banana", 8);

        System.out.println(map);
    }
}
```

```
{Apple=3, Banana=8, Cherry=5, Dragon Fruit=4}
```

The keys are fruit names and the values are the total cost of the fruits. The
map is sorted according to the natural order of the keys (alphabetical).

We can also create a map that stores elements in the reverse order:

```java
import java.util.Comparator;
import java.util.TreeMap;

public class Example {
    public static void main(String[] args) {
        TreeMap<String, Integer> map = new TreeMap<>(Comparator.reverseOrder());
        map.put("Dragon Fruit", 4);
        map.put("Apple", 3);
        map.put("Cherry", 5);
        map.put("Banana", 8);

        System.out.println(map);
    }
}
```

```plaintext
{Dragon Fruit=4, Cherry=5, Banana=8, Apple=3}
```
