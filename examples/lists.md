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
