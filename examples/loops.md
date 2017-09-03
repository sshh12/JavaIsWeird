# Java is weird.

## Loops

#### Syntax

```java
for(;;){                       // a (x1)
    System.out.println('a');
    break;
}

for(;;){ }                     // (Infinite loop)

for(){ }                       // (Compile Error)

for(int i = 0; i < 10; i++)    // a (x10)
    System.out.println('a');

for(int i = 0; i < 10; i++);   // a (x1)
    System.out.println('a');
```

#### Goto and labels

```java
int goto = 1;                       // (Compile Error)

label: {                            // (Valid)
    if (condition) {
        break label;
    }
}

label: do {                         // (Valid)
    if (condition) continue label;
    break label;
} while(true);
```
