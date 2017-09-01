# Java is weird.

## BigInteger

#### Constructor

```java
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
BigInteger a = new BigInteger("2");
a.isProbablePrime(0);               // true (certainty <= 0 always is true)
a.isProbablePrime(100);             // true (2 is the only prime w/100% certainty)

BigInteger b = new BigInteger("4");
b.isProbablePrime(0);               // true
b.isProbablePrime(100);             // false
```
