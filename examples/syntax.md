# Java is weird.

## Syntax

#### Variable names

```java
int _ = 1; // 1
int $ = 2; // 2
int £ = 3; // 3
int € = 4; // 4
int - = 5; // (Compile Error)
int # = 6; // (Compile Error)
int @ = 7; // (Compile Error)
int * = 8; // (Compile Error)
int 1 = 9; // (Compile Error)
```

#### Chain casting

```java
int a = (byte) + (short) - (int) + 1; // -1
int b = (byte)(short)(int) + 1;       // 1
int c = (byte)(short)(int) * 1;       // (Compile Error)
int d = (int)(double)(int) + 1.5;     // 1
```

#### Arrays

```java
int[][] a = {{}}; // [[]]
int[] b[] = {{}}; // [[]]
int c[][] = {{}}; // [[]]
```
