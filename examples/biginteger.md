# Java is weird.

## BigInteger

#### Constructor

```java
new BigInteger(8);                // (Compiler Error, private)
new BigInteger("8");              // 8
new BigInteger("11", 16);         // 17
new BigInteger(new byte[]{0, 1}); // 1
new BigInteger(new int[]{0, 1});  // (Compile Error, private)
```

#### Static variables

```java
BigInteger.NEGATIVE_ONE; // (Compile Error, private)
BigInteger.ZERO;         // 0
BigInteger.ONE;          // 1
BigInteger.TWO;          // (Compile Error, private)
BigInteger.TEN;          // 10
```

#### ProbablePrime

```java
BigInteger a = new BigInteger("1");
a.isProbablePrime(0);               // true (certainty <= 0 always is true)
a.isProbablePrime(1);               // false

BigInteger b = new BigInteger("2");
b.isProbablePrime(0);               // true
b.isProbablePrime(100);             // true

BigInteger c = new BigInteger("4");
c.isProbablePrime(0);               // true
c.isProbablePrime(100);             // false
```

#### Doing Math

```java
BigInteger a = BigInteger.ONE;
BigInteger b = BigInteger.TEN;

System.out.println(a + b);     // (Compile Error, cannot add objects)

a.add(b);                      // 11 (a and b not changed)
a;                             // 1
b;                             // 10
```