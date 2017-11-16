# Java is weird.

## Statics

#### Not a null pointer

```java
Math[] maths = new Math[10];
maths[0];                    // null
maths[0].floor(1.5);         // 1
```

#### Import

```java
import static java.lang.Math.*; // (Valid)
min(1, 3);                      // 1
```