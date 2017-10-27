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

#### Accessing Instance Vars

```java
class A {

  private   int x = 1;
  protected int y = 2;
  public    int z = 3;

  A(){ }

}

class B extends A {

  B(){ }
  
  void set(){ x = 99; }          // (Compile Error)
  
  void set2(){ super.x = 99; }   // (Valid)
  
  void set3(){  
	y = 99; z = 99;              // (Valid)
  }
  
  void set4(){ 
    super.y = 99; super.z = 99;  // (Valid)
  }

}
```

```java
B test = new B();
test.x;            // (Compile Error, private)
test.y;            // 2
test.z             // 3

test.set();
test.set2();
test.set3();
test.set4();
```

#### Changing Instance Vars

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