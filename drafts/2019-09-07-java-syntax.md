---
layout: post
categories: til
tags: ["language"]
---

이것은 `inline` 코드 입니다. `A`를 `B`와 같이

```html
<!DOCTYPE html>
<html>
    <head>
        <link rel="stylesheet" type="text/css" />
    </head>
<body>
    <!-- This is a comment -->
    <p>three&amp;&amp;&amp;spaces</p>
</body>
</html>
```

```php
<?php
// This is a single-line comment
$stringvariable = "examplestring";
$intvariable = 300;
/**
 * This is a multi-line comment
 * @author Roger Dudler
 */
class Testclass {
    function test($param = "default") {
        return true;
    }
}
?>
}
```

```java
public enum Element {
    H("Hydrogen", 1, 1.008f),
    HE("Helium", 2, 4.0026f),
    // ...
    NE("Neon", 10, 20.180f);
 
    private static final Map<String, Element> BY_LABEL = new HashMap<>();
    private static final Map<Integer, Element> BY_ATOMIC_NUMBER = new HashMap<>();
    private static final Map<Float, Element> BY_ATOMIC_WEIGHT = new HashMap<>();
     
    static {
        for (Element e : values()) {
            BY_LABEL.put(e.label, e);
            BY_ATOMIC_NUMBER.put(e.atomicNumber, e);
            BY_ATOMIC_WEIGHT.put(e.atomicWeight, e);
        }
    }
 
    public final String label;
    public final int atomicNumber;
    public final float atomicWeight;
 
    private Element(String label, int atomicNumber, float atomicWeight) {
        this.label = label;
        this.atomicNumber = atomicNumber;
        this.atomicWeight = atomicWeight;
    }
 
    public static Element valueOfLabel(String label) {
        return BY_LABEL.get(label);
    }
 
    public static Element valueOfAtomicNumber(int number) {
        return BY_ATOMIC_NUMBER.get(number);
    }
 
    public static Element valueOfAtomicWeight(float weight) {
        return BY_ATOMIC_WEIGHT.get(weight);
    }
}
```

```java
public class Demo {
    private static final String CONSTANT = "String";
    private Object o;
    /**
     * Creates a new demo.
     * @param o The object to demonstrate.
     */
    public Demo(Object o) {
        this.o = o;
        String s = CONSTANT;
        int i = 1;
    }
    public static void main(String[] args) {
        Demo demo = new Demo();
    }
}
```


```java
/* Block comment */
import java.util.Date;
import static AnInterface.CONSTANT;
import static java.util.Date.parse;
import static SomeClass.staticField;
/**
 * Doc comment here for <code>SomeClass</code>
 * @param T type parameter
 * @see Math#sin(double)
 */
@Annotation (name=value)
public class SomeClass<T extends Runnable> { // some comment
  private T field = null;
  private double unusedField = 12345.67890;
  private UnknownType anotherString = "Another\nStrin\g";
  public static int staticField = 0;
  public final int instanceFinalField = 0;

  /**
   * Semantic highlighting:
   * Generated spectrum to pick colors for local variables and parameters:
   *  Color#1 SC1.1 SC1.2 SC1.3 SC1.4 Color#2 SC2.1 SC2.2 SC2.3 SC2.4 Color#3
   *  Color#3 SC3.1 SC3.2 SC3.3 SC3.4 Color#4 SC4.1 SC4.2 SC4.3 SC4.4 Color#5
   * @param param1
   * @param reassignedParam
   * @param param2
   * @param param3
   */
  public SomeClass(AnInterface param1, int[] reassignedParam,
                  int param2
                  int param3) {
    int reassignedValue = this.staticField + param2 + param3;
    long localVar1, localVar2, localVar3, localVar4;
    int localVar = "IntelliJ"; // Error, incompatible types
    System.out.println(anotherString + toString() + localVar);
    long time = parse("1.2.3"); // Method is deprecated
    new Thread().countStackFrames(); // Method is deprecated and marked for removal
    reassignedValue ++; 
    field.run(); 
    new SomeClass() {
      {
        int a = localVar;
      }
    };
    reassignedParam = new ArrayList<String>().toArray(new int[CONSTANT]);
  }
}
enum AnEnum { CONST1, CONST2 }
interface AnInterface {
  int CONSTANT = 2;
  void method();
}
abstract class SomeAbstractClass {
  protected int instanceField = staticField;
}
```
