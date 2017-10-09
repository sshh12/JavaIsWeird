# Java is weird.

## Loops and Conditionals

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

#### Labels

```java
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

#### Short Circuit

```java
boolean doStuff(){

  System.out.println("1");
  return true;

}

if(false || doStuff()){}   // 1
if(true  || doStuff()){}   // (Nothing)
if(false && doStuff()){}   // (Nothing)
if(true  && doStuff()){}   // 1
```
