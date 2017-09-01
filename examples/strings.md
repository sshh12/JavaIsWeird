# Java is wierd.

## Strings

#### Equals (==)

```java
String a = "abc";
String b = "abc";
String c = new String("abc");
String d = new String("abc");
a == b;                       // true
a == c;                       // false
c == d;                       // false

String getString(){
    return "abc";
}

a == getString();             // true
```

#### Compare similar strings

```java
"abcdefg".compareTo("abc"); // 4
```