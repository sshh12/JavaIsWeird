# Java is weird.

## Inheritance

#### Parent constructor call

```java
class A {

  A(){ System.out.println('1'); }

}

class B extends A {

  B(){ System.out.println('2'); }

}
```

```java
new B(); // 12
```
