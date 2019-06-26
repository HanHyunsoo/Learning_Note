# 상속

이번엔 자바의 상속(Inheritance)에 대해서 알아보자. 상속은 말 그대로 자식이 부모로부터 무언가를 물려받는 것이다.

Animal 클래스를 상속하는 Dog 클래스를 만들어 보자.

***Animal.java***

```java
public class Animal {
    String name;

    public void setName(String name) {
        this.name = name;
    }
}
```

***Dog.java***

```java
public class Dog extends Animal {

}
```

클래스 상속을 위해서는 extends 라는 키워드를 사용한다.

자식클래스 extends 부모클래스
이제 Dog 클래스는 Animal 클래스를 상속하게 되었다.

Dog 클래스에 name 이라는 객체변수와 setName 이라는 메소드를 만들지 않았지만 Animal클래스를 상속을 받았기 때문에 그대로 사용이 가능하다. Dog 클래스에 다음과 같은 main 메소드를 구현하고 실행시켜 보자.

```java
public class Dog extends Animal {
    public static void main(String[] args) {
        Dog dog = new Dog();
        dog.setName("poppy");
        System.out.println(dog.name);
    }
}
```

실행해보면 "poppy"라는 문자열이 출력되는것을 확인할 수 있다.

이번에는 Dog 클래스에 sleep이라는 메소드를 추가 해 보자.

```java
public class Dog extends Animal {
    public void sleep() {
        System.out.println(this.name+" zzz");
    }

    public static void main(String[] args) {
        Dog dog = new Dog();
        dog.setName("poppy");
        System.out.println(dog.name);
        dog.sleep();
    }
}
```

이제 Dog 클래스는 Animal 클래스보다 좀 더 많은 기능(sleep메소드가 추가되었다.)을 가지게 되었다. 이렇듯 보통 부모 클래스를 상속받은 자식 클래스는 부모 클래스의 기능에 더하여 좀 더 많은 기능을 갖도록 설계한다.
