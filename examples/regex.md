# Java is weird.

## Regex

#### Split

```java
"aaaa".split("a");           // []
"aaaa".split(".");           // []

"abababa".split("a");        // [, b, b, b]
"abababa".split("a", -1);    // [, b, b, b, ]

"ababaaaaa".split("a");      // [, b, b]
"ababaaaaa".split("a", -1);  // [, b, b, , , , , ]
"ababaaaaa".split("a*");     // [, , b, , b]
"ababaaaaa".split("a?");     // [, , b, , b]
"ababaaaaa".split("a?", -1); // [, , b, , b, , , , , , ]
```

#### Replace

```java
"a-b--c".replaceAll("[a-z]", "~$0~");                   // ~a~-~b~--~c~
"...123..890.".replaceAll("(\\d)(\\d)(\\d)", "$3$2$1"); // ...321..098.
```
