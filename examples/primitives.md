# Java is wierd.

## Primitives

#### Divide by zero

```java
double a = 1. / 0;    // Infinity
float  b = 1f / 0;    // Infinity
int    c = 1  / 0;    // (ArithmeticException)
short  d = 1; d /= 0; // (ArithmeticException)
byte   e = 1; e /= 0; // (ArithmeticException)
```

#### Upcasting

```java
byte a = Byte.MAX_VALUE;   // 127
a + 3;                     // 130

int b = Integer.MAX_VALUE; // 2147483647
b + 1.;                    // 2.147483648E9
```