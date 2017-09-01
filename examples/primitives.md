# Java is weird.

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

#### Valid shifting

```java
double a = 1; a <<= 2; // (Compile Error)
float  b = 1; b <<= 2; // (Compile Error)
int    c = 1; c <<= 2; // 4
short  d = 1; d <<= 2; // 4
byte   e = 1; e <<= 2; // 4
```

#### Infinity

```java
double a = 1. / 0; // Infinity
a * -1;            // -Infinity
a / 2;             // Infinity
a - 5;             // Infinity
a / a;             // NaN
a - a;             // NaN
```
