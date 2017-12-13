# Java is weird.

## Syntax

#### Variable names

```java
int _ = 1;            // 1
int $ = 2;            // 2
int £ = 3;            // 3
int € = 4;            // 4
int - = 5;            // (Compile Error)
int # = 6;            // (Compile Error)
int @ = 7;            // (Compile Error)
int * = 8;            // (Compile Error)
int 1 = 9;            // (Compile Error)
int finally = 10;     // (Compile Error)

String String = "a";  // (Valid)
String.valueOf(1);    // (Compile Error, `String` is now var)

int Integer = 1;      // (Valid)
Math Math = null;     // (Valid)
Double Double = 3.14; // (Valid)
Double double = 3.14; // (Compile Error)
``` 

#### Chain casting

```java
int a = (byte) + (short) - (int) + 1; // -1
int b = (byte)(short)(int) + 1;       // 1
int c = (byte)(short)(int) * 1;       // (Compile Error)
int d = (int)(double)(int) + 1.5;     // 1
```

#### Return

```java
return;       // (Valid)
return(0);    // (Valid)
return(null); // (Valid)
``` 

#### Varargs

```java
void A(String... args){
	System.out.println(Arrays.toString(args));
}

void B(String... args, String x){              // (Compile Error)
	System.out.println(Arrays.toString(args));
}

void C(String x, String... args){
	System.out.println(Arrays.toString(args));
}
```

```java
A("i", "j", "k"); // [i, j, k]

C("i", "j", "k"); // [j, k]
```

#### Methods

```java
// (Valid)
void func() { }
static void func() { }
public static void func() { }
static public void func() { }

// (Compile Error)
func() { }
static func() { }
public void static func() { }
void public static func() { }
static void public func() { }
```

#### Keywords

```java
if(a instanceOf b) {};

boolean a;
byte b;
char c;
double d;
float e;
int f;
long g;
short h;

class a {}
enum b {}
interface c {}

class a extends b {}
class c implements d {}

abstract a();
default b();
final c();
native d();
static e();
synchronized f();
void g();
transient int h;
volatile int i;
strictfp class j {};

new a();

import a.b;
package c;

private a();
protected b();
public c();

switch(){};
case a: b();
default c() {};

break;
continue;

do {};
for() {};
while() {};

if(){};
else {};

try {};
catch {};
finally {};
throw new a();

return;

super; super();
this; this();

goto a;   // (Unused)
const b;  // (Unused)
```

#### Operator Precedence

```java
a[b]
c.d
(e)

a++
b--

++a
--b
+c
-d
!e
~f

(a)b
new c()

a * b
c / d
e % f

a + b
c - d

a >> b
c << d
e >>> f

a < b
c <= d
e > f
g >= h
i instanceof j

a == b
c != d

a & b

a ^ b

a | b

a && b

a || b

a ? b : c

a = b
c += d
e -= f
g *= h
i /= j
k %= l
m &= n
o ^= p
q |= r
s <<= t
u >>= v
w >>>= x
```

```java
// For the lulz
int x = 3;
System.out.println(~-+-~x+++-1);

System.out.println(5 +- 5); // 0
System.out.println(5 -+ 5); // 0
```