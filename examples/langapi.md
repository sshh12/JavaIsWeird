# Java is weird.

## java.lang

#### .print

```java
System.out.print(1e7);                       // 1.0E7
System.out.print(Double.POSITIVE_INFINITY);  // Infinity
System.out.print(new char[]{'a', 'b', 'c'}); // abc
System.out.print(new int[]{1, 2, 3});        // [I@15db9742
System.out.print(new Object());              // java.lang.Object@15db9742
```