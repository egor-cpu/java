# Практика #22


## Практика #1

Приведите пример кода, демонстрирующего все три варианта использования ключевого слова super.

```java
// Суперкласс
class Animal {
    String name = "Животное";

    // Конструктор суперкласса
    public Animal() {
        System.out.println("Конструктор Animal");
    }

    // Метод в суперклассе
    public void speak() {
        System.out.println("Животное издает звук");
    }
}

// Подкласс
class Dog extends Animal {
    String name = "Собака";

    // Конструктор подкласса
    public Dog() {
        // Вызов конструктора суперкласса с помощью super()
        super();
        System.out.println("Конструктор Dog");
    }

    // Переопределённый метод speak()
    @Override
    public void speak() {
        // Вызов метода speak() суперкласса с помощью super
        super.speak();
        System.out.println("Собака лает");
    }

    // Метод для демонстрации использования переменной super
    public void showName() {
        // Используем переменную name из суперкласса через super
        System.out.println("Имя из суперкласса: " + super.name);
        System.out.println("Имя из подкласса: " + this.name);
    }
}

public class TestSuper {
    public static void main(String[] args) {
        // Создаем объект подкласса Dog
        Dog dog = new Dog();
        dog.speak();  // Выведет: Животное издает звук, Собака лает

        // Демонстрация использования переменной super
        dog.showName();  // Выведет: Имя из суперкласса: Животное, Имя из подкласса: Собака
    }
}
```

## Практика #2
Что случится при вызове метода method() объекта класса C, если переменная a и метод method() не будут определены в классе B, а будут определены только в классе A?
```java
class A {
  int a;
  void method() {
    ...
  }

}

class B extends A {
  ...
}

class C extends B {
  ...
  void method() {
    ...
    int a = super.a;
    super.method();
  }
  ...
}
```
В классе C, при вызове метода method(), доступ к переменной a и вызов метода method() будет корректным, поскольку оба они определены в классе A, а класс B не переопределяет их.

## Практика #3
Перепешите следующий код с использованием конструкции this(). Помните, что в каждом конструкторе вызов this() должен быть единственным и первым среди всех операций.
```java
class A {
  int a;
  int b;
  int c;
  int z;

  public A() {
    this(0, 0, 0);  // Вызов конструктора с тремя параметрами
    z = 1;
  }

  public A(int a) {
    this(a, 0, 0);  // Вызов конструктора с тремя параметрами
    z = 1;
  }

  public A(int a, int b) {
    this(a, b, 0);  // Вызов конструктора с тремя параметрами
    z = 1;
  }

  public A(int a, int b, int c) {
    this.a = a;
    this.b = b;
    this.c = c;
    z = 1;
  }
  ...
}
```
