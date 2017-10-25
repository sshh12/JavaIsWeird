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

#### Instance Vars

```java
class A {

  int x = 1;

  A(){ }

}

class B extends A {

  int x = 2;

  B(){ }

}
```

```java
B test = new B(); test.x; // 2
A test = new A(); test.x; // 1
A test = new B(); test.x; // 1

B test = new B();
test.x;                   // 2
((A)(test)).x;            // 1
((A)(test)).x = 3;
text.x;                   // 2
A test2 = text;
test2.x;                  // 3
```