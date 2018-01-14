# Java is weird.

## Arrays and Collections

#### Abstractions

```
                                        <Collection>

              +------------------------------------------------------------+
              +                                     +                      +

            <Set>                                <List>                 <Queue>

    +------------------+                 +---------------------+    +------------+
    +                  +                 +          +          +    +            +

  HashSet         <SortedSet>       ArrayList     Vector     LinkedList    PriorityQueue

    +                  +
    +                  +

LinkedHashSet    <NavigableSet>

                       +
                       +

                    TreeSet

```

#### asList

```java
Integer[] a = new Integer[]{1, 2, 3};
List<Integer> b = Arrays.asList(a);   // [1, 2, 3]

b.add(4);                             // (UnsupportedOperationException)

a[0] = 5;
b.get(0);                             // 5

b.set(1, 6);
a[1];                                 // 6
```

#### toArray

```java
List<String> items = new ArrayList<>();
items.add("a"); items.add("b"); items.add("c");

String[] a1 = new String[]{};
String[] a2 = items.toArray(a1);
a1;                                 // []
a2;                                 // [a, b, c]

String[] b1 = new String[]{"1", "2", "3"};
String[] b2 = items.toArray(b1);
b1;                                 // [a, b, c]
b2;                                 // [a, b, c]

String[] c1 = new String[]{"1", "2", "3", "4", "5"};
String[] c2 = items.toArray(c1);
c1;                                 // [a, b, c, null, 5]
c2;                                 // [a, b, c, null, 5]
```

#### Remove

```java
List<Integer> list = new ArrayList<>();
list.add(1);                 // true, [1]
list.add(2);                 // true, [1, 2]
list.add(3);                 // true, [1, 2, 3]

list.remove(1);              // 2,    [1, 3]
list.remove(new Integer(1)); // true, [3]

list.remove(10);             // (IndexOutOfBoundsException)
list.remove(new Integer(10)) // False

LinkedList<Integer> items = new LinkedList<>();
items.add(1); items.add(2); items.add(3);

items.remove();              // 1 (LinkedList only)
items.removeFirst();         // 2 (LinkedList only)
items.removeLast();          // 3 (LinkedList only)
```

#### Declaration

```java
int[][] a = {{}}; // [[]] (Valid)
int[] b[] = {{}}; // [[]] (Valid)
int c[][] = {{}}; // [[]] (Valid)
```

#### Collection Methods

```java
Set<Integer> a = new HashSet<>();
a.add(1); a.add(2); a.add(3);

Set<Integer> b = new HashSet<>();
b.add(3); b.add(4); b.add(5);
```

```java
// Examples are not chained
a.retainAll(b);
a;               // [3]

a.removeAll(b);
a;               // [1, 2]

a.addAll(b);
a;               // [1, 2, 3, 4, 5] (only one `3` b/c set)
```

#### Recursive Collection

```java
List<Object> items = new ArrayList<>();

items.add(1);
items.add("abc");
items.add(new ArrayList<>());
items.add(items);

System.out.println(items);         // [1, abc, [], (this Collection)]
System.out.println(items.get(3));  // [1, abc, [], (this Collection)]

((List)items.get(3)).add(3.14);

System.out.println(items);         // [1, abc, [], (this Collection), 3.14]

List<Object> stuff = new ArrayList<>();
stuff.add(items); items.add(stuff);

System.out.println(items);         // (Runtime Error, StackOverflowError)
```

#### Constructors

```java
Collection data = new ArrayList<>();

new Stack<Integer>();          // (Valid)
new Stack<Integer>(data);      // (Compile Error)

new ArrayList<Integer>();      // (Valid)
new LinkedList<Integer>();     // (Valid)
new ArrayList<Integer>(data);  // (Valid)
new LinkedList<Integer>(data); // (Valid)

new HashSet<Integer>();        // (Valid)
new HashSet<Integer>(data);    // (Valid)
```
