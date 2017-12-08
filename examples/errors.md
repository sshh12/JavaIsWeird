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

#### Finally return

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

#### Error Inheritance

```java
interface A {
    void func() throws ArithmeticException, ArrayIndexOutOfBoundsException;
}

interface B {
    void func() throws ArrayIndexOutOfBoundsException, IllegalArgumentException;
}

interface C extends A, B {
    void func() throws ArrayIndexOutOfBoundsException;           // Throws intersection of exceptions
}

class D implements C {
    @Override
    public void func() throws ArrayIndexOutOfBoundsException { } // Throws intersection of exceptions
}
```