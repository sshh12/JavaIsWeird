# Java is weird.

## Lists

#### asList

```java
Integer[] a = new Integer[]{1, 2, 3};
List<Integer> b = Arrays.asList(a);   // [1, 2, 3]

b.add(4);                             // (UnsupportedOperationException)

a[0] = 5;
b.get(0);                             // 5

b.set(1, 6);
a[1];                                 // 6
```

#### Remove

```java
List<Integer> list = new ArrayList<>();
list.add(1);                 // true, [1]
list.add(2);                 // true, [1, 2]
list.add(3);                 // true, [1, 2, 3]

list.remove(1);              // 2,    [1, 3]
list.remove(new Integer(1)); // true, [3]

list.remove(10);             // (IndexOutOfBoundsException)
list.remove(new Integer(10)) // False
```
