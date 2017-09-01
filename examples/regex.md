# Java is weird.

## Regex

#### Split

```java
"aaaa".split("a");       // []
"abababa".split("a");     // [, b, b, b]
"abababa".split("a", -1); // [, b, b, b, ]
```

#### Replace

```java
"a-b--c".replaceAll("[a-z]", "~$0~");                   // ~a~-~b~--~c~
"...123..890.".replaceAll("(\\d)(\\d)(\\d)", "$3$2$1"); // ...321..098.
```
