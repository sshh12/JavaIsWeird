# Java is weird.

## String Formatting

#### Syntax

```java
%[flags][width][.precision]character

-    // (Left justify, ex. 'Text      ')
+    // (Will display '+' for positive or '-' if negative)
0    // (Zero padding ex.  0032)
,    // (Group numbers ex. 1234567 -> 1,234,567)
     // (Space will display '-' if negative or a ' ' if positive)
(    // (Will wrap a negative number in parentheses and remove sign ex. -12 -> '(12)')
```

#### Characters

```java
%d    // (Decimal [byte, short, int, long])
%f    // (Float [float, double])
%e    // (Exponential [float, double] only ex. 1.25 -> 1.250000e+01)
%x    // (Hex/base16)
%o    // (Octal/base8)

%b    // (Boolean ex. null -> false)
%B    // (Boolean made uppercase ex. 1 -> TRUE)

%c    // (Character)
%C    // (Character made uppercase)
%s    // (String)
%S    // (String made all uppercase)

%h    // (Hashcode ex. 1b18c)

%n    // \n (Newline)
%%    // % (Just a normal % sign)
\%    // % (Same as %%)  
```

#### Precision/Rounding

```java
System.out.printf("%.2f", 22.849);   // 22.85
System.out.printf("%.2f", 22.8446);  // 22.84
System.out.printf("%.2f", 22.8);     // 22.80
```

#### Ignoring Width Digit

```java
System.out.printf("%3s", "1234567890");   // 1234567890
System.out.printf("%2.2f", 12345.67890);  // 12345.68
```

#### Padding

```java
System.out.printf("==%s==",   "abc");  // ==abc==
System.out.printf("==%8s==",  "abc");  // ==     abc==
System.out.printf("==%-8s==", "abc");  // ==abc     ==
```

#### Boolean Converter

```java
System.out.printf("%b", true);   // true
System.out.printf("%b", 0);      // true
System.out.printf("%b", "");     // true
System.out.printf("%b", "abc");  // true

System.out.printf("%b", false);           // false
System.out.printf("%b", null);            // false
System.out.printf("%b", new int[5]);      // false (Empty array is falsy)
System.out.printf("%b", new HashSet<>()); // false (Empty collection is falsy)
```

#### Valid Primitives

```java
System.out.printf("%d", 1);      // 1
System.out.printf("%d", 1.5);    // (Runtime Error, IllegalFormatConversionException)
System.out.printf("%d", 'a');    // (Runtime Error, IllegalFormatConversionException)
System.out.printf("%d", 32L);    // 32

System.out.printf("%f", 1.6f);   // 1.600000
System.out.printf("%f", 10);     // (Runtime Error, IllegalFormatConversionException)
```