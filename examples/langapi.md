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

#### Math

````java
Math.ceil(-1.5);      // -1.0 (returns double)
Math.floor(-3.14);    // -4.0 (returns double)

Math.round(1.5);      // 2 (double -> long)
Math.round(1.5f);     // 2 (float -> int)

Math.round(-1.4999);  // -1
Math.round(-1.5000);  // -1
Math.round(-1.5001);  // -2

Math.rint(1.2);       // 1.0 (like round but returns double)
Math.rint(1.8);       // 2.0
Math.rint(1.5);       // 2.0
Math.rint(2.5);       // 2.0 (rint will round .5 to nearest even integer)
````