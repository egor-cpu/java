# Практика #21


## Практика #1

Приведите пример кода, демонстрирующего невозможность переопределять в подклассе final-метод суперкласса.

```java
class SuperClass {
    // Этот метод не может быть переопределён, так как он final
    public final void display() {
        System.out.println("Метод display() в SuperClass");
    }
}

class SubClass extends SuperClass {
    // Попытка переопределить final-метод вызовет ошибку компиляции
    @Override
    public void display() {
        System.out.println("Метод display() в SubClass");
    }
}

public class TestFinalMethod {
    public static void main(String[] args) {
        SuperClass superClass = new SuperClass();
        superClass.display();  // Выведет: Метод display() в SuperClass

        SubClass subClass = new SubClass();
        subClass.display();    // Это невозможно, так как компилятор выдаст ошибку
    }
}

```

## Практика #2: 

Приведите пример кода, демонстрирующего невозможность использовать наследование для final-класса.

```java
// Финальный класс
final class FinalClass {
    public void display() {
        System.out.println("Это финальный класс.");
    }
}

// Попытка наследования от финального класса вызовет ошибку компиляции
class SubClass extends FinalClass {
    public void show() {
        System.out.println("Это подкласс.");
    }
}

public class TestFinalClass {
    public static void main(String[] args) {
        FinalClass finalClass = new FinalClass();
        finalClass.display();  // Выведет: Это финальный класс.
        
        SubClass subClass = new SubClass(); // Ошибка компиляции: нельзя наследовать от final класса
        subClass.show();
    }
}

```
