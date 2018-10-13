### Q1: What is the difference between ArrayList and LinkedList.

When will you use ArrayList and when will you use LinkedList?

### Q2: Please correct all the compiling errors in the following code.

```java
public abstract class AbstractClassTest {
    private static final int _value;

    AbstractClassTest()
    {
        _value = 1;
    }
    
    abstract int add(int value);

    abstract int minus(int value);

    public static void printMe() {
        System.out.println(_value);
    }
}

public class TestClass1 implements AbstractClassTest {
    @Override
    private int add(int v) {
        _value += v;
        printMe();
        return _value;
    }

    @Override
    public int minus(int v) {
        _value -= v;
        printMe();
        return _value;
    }
}
```

### Q3: Please identify and solve all the potential issues related to multithreading.

```java
/*
 * (DO NOT delete any of the locks or threads)
 */
public final class ThreadTest {
    private int _counter1 = 0;
    private int _counter2 = 0;

    private final Object _lock1 = new Object();
    private final Object _lock2 = new Object();
    private final Map<String, Integer> threadSteps = new HashMap<>();

    public void function1() {
        for (int i = 0; i < 10000; i++) {
            synchronized (_lock1) {
                _counter1 += 1;
                System.out.println(String.format("Thread1[%d]: counter1=%d", i, _counter1));
                synchronized (_lock2) {
                    _counter2 += _counter1;
                    System.out.println(String.format("Thread2[%d]: counter2=%d", i, _counter2));
                }
            }
            threadSteps.put("Thread1-" + i, _counter1 * _counter2);
        }
    }

    public void function2() {
        for (int i = 0; i < 10000; i++) {
            synchronized (_lock2) {
                _counter2 -= _counter1;
                System.out.println(String.format("Thread2[%d]: counter2=%d", i, _counter2));
                synchronized (_lock1) {
                    _counter1 -= 1;
                    System.out.println(String.format("Thread1[%d]: counter1=%d", i, _counter1));
                }
            }
            threadSteps.put("Thread2-" + i, _counter1 * _counter2);
        }
    }

    public static void main(String[] args) {
        final ThreadTest threadTest = new ThreadTest();
        final Thread thread1 = new Thread(new Runnable() {
            @Override
            public void run() {
                threadTest.function1();
            }
        });
        final Thread thread2 = new Thread(new Runnable() {
            @Override
            public void run() {
                threadTest.function2();
            }
        });
        thread1.start();
        thread2.start();
    }
}
```

### Q4: Please make the following class immutable

```java
public class Book {
    public int pageCount;
    public Map<Integer, String> pageContents;

    public Book() {
        this.pageCount = 0;
        this.pageContents = new HashMap<>();
    }

    public void addPage(String content) {
        pageCount++;
        pageContents.put(pageCount, content);
    }
    
    public Map<Integer, String> getAllPages()
    {
        return pageContents;
    }
}
```

### Q5: Please study Software design pattern 'State Pattern' (https://en.wikipedia.org/wiki/State_pattern).

Then implement simple state transition among play state, pause state, stop state.
