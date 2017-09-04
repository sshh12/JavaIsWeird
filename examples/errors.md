# Java is weird.

## Errors

#### Finally

```java
System.out.print('a');
try {

    int b = 1 / 0;

} catch(NullPointerException c){

    System.out.print('d');

} finally {

    System.out.print('e');

}                              // ae and (ArithmeticException)

System.out.print('a');
try {

    int b = 1 / 0;

} catch(ArithmeticException c){

    System.out.print('d');

} finally {

    System.out.print('e');

}                              // ade
```

#### Return finally

```java
boolean getValue(){

  try {

    return true;

  } finally {

    return false;

  }

}
getValue();          // false
```
