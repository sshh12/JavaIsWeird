# Java is weird.

## Strings

#### Equals (==)

```java
"abc" == "abc";               // true

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

a += "."; b += ".";
a == b;                       // false

"abc" + "." == "abc" + ".";   // true
String e = "abc" + ".";
String f = "abc.";
e == f;                       // true

String g = a.substring(0);
g == a;                       // true (substring(0) -> this)
```

#### Compare similar strings

```java
"abcdefg".compareTo("abc"); // 4
"abc".compareTo("abcdefg"); // -4
```

#### Combining

```java
1 + 2 + "3" + 4 + 5; // 3345

1 + "2" == "3" + 4;  // false
1 + "2" == "1" + 2;  // true
```

#### Substring

```java
"".substring(0);       // ""
"".substring(0, 0);    // ""
"".substring(1);       // (StringIndexOutOfBoundsException)
"".substring(0, 1);    // (StringIndexOutOfBoundsException)
"abc".substring(3);    // ""
"abc".substring(3, 3); // ""
"abc".substring(3, 4); // (StringIndexOutOfBoundsException)
```
