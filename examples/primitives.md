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

#### Casting

```java
byte a = Byte.MAX_VALUE;   // 127
a + 3;                     // 130

int b = Integer.MAX_VALUE; // 2147483647
b + 1.;                    // 2.147483648E9

int c = 1.5;               // (Compile Error)
int d = 0; d += 1.5;       // 1
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

#### Lack of precision

```java
double a = 1e30;
double b = a + 10;
a == b; // true
```

#### Zero

```java
-0 == 0; // true
```

#### Objects

```java
5 == 5;                           // true
new Integer(5) == 5;              // true
new Integer(5) == new Integer(5); // false

Integer a = 5;
Integer b = 5;
Integer c = new Integer(5);
Integer d = new Integer(5);
a == b;                           // true
c == d;                           // false
c == a;                           // false

Integer e = 128;
Integer f = 128;
e <= f;                           // true
e >= f;                           // true
e == f;                           // false
```

#### Ternary

```java
int    a = true ? 1 : 1.0;    // (Compile Error)
Object b = true ? 1 : 2.5;    // 1.0

Integer c = null;
double  d = 2.0;
Object  e = true ? null : d;  // null
Object  f = true ?    c : d;  // (NullPointerException)
```

#### Literals

```java
int a = 05;     // 5
int b = 010;    // 8
int c = 08;     // (Compile Error)

int d =  x10;   // (Compile Error)
int e = 0x10;   // 16

int    f = 1e2; // (Compile Error)
double g = 1e2; // 100.0
```
