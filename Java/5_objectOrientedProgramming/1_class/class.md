# 클래스

"동물"이라는 클래스는 다음과 같이 만들 수 있다.

```java
public class Animal {
}
```

위 Animal 클래스는 가장 간단한 형태의 클래스이다. 클래스의 선언만 있고 내용이 없는 껍데기뿐인 클래스이다. 하지만 이 껍데기뿐인 클래스도 아주 중요한 기능을 가지고 있다. 그 기능은 바로 객체(object)를 만드는 기능이다.

객체는 다음과 같이 만들 수 있다.

```java
Animal cat = new Animal();
```

new 는 객체를 생성할 때 사용하는 키워드이다. 이렇게 하면 Animal 클래스의 인스턴스(instance)인 cat, 즉 Animal의 객체가 만들어진다.

다른 예시를 들어보면 과자가 있다.

과자를 만들기 위해서는 먼저 과자의 모양을 잡을 과자틀과 과자틀에 의해서 만들어진 과자들이 있다. 정리하면 아래와 같다.

* 과자틀 → 클래스 (Class)
* 과자틀에 의해서 만들어진 과자들 → 객체 (Object)

즉 위를 참고해서 동물 객체를 만든다면 다음과 같이 무수히 많은 동물 객체(cat, dog, horse, ...)들을 Animal 클래스로 만들 수 있는 것이다.

```java
Animal cat = new Animal();
Animal dog = new Animal();
Animal horse = new Animal();
...
```

## 객체와 인스턴스

클래스에 의해서 만들어진 객체를 인스턴스라고도 한다. 그렇다면 객체와 인스턴스의 차이는 무엇일까? 이렇게 생각 해 보자. `Animal cat = new Animal()` 이렇게 만들어진 cat은 객체이다. 그리고 cat이라는 객체는 Animal의 **인스턴스(instance)** 이다. 즉 인스턴스라는 말은 특정 객체(cat)가 어떤 클래스(Animal)의 객체인지를 **관계** 위주로 설명할 때 사용된다. 즉, "cat은 인스턴스" 보다는 "cat은 객체"라는 표현이 "cat은 Animal의 객체" 보다는 "cat은 Animal의 인스턴스" 라는 표현이 훨씬 잘 어울린다.

## 객체 변수 (Instance variable)

```java
public class Animal {
    String name;
}
```

Animal 클래스에 name 이라는 String 변수를 추가했다. 이렇게 클래스에 선언된 변수를 **객체 변수** 라고 부른다. 또는 인스턴스 변수, 멤버 변수, 속성이라고도 말한다.

클래스에 의해 생성되는 것은 객체, 그리고 그 클래스에 선언된 변수는 객체 변수라고 생각하면 쉽다.

객체 변수를 만들었으니 이제 객체 변수를 사용해 보도록 하자. 먼저 객체 변수는 변수이므로 값을 대입할 수 있을 것이다. 대입하기 전에 객체 변수는 현재 어떤 값을 가지고 있는지 먼저 출력 해 보도록 하자.

객체 변수를 출력하려면 객체 변수에 어떻게 접근해야 하는지를 먼저 알아야 한다.

객체 변수는 다음과 같이 도트연산자(.)를 이용하여 접근할 수 있다.

```java
객체.객체변수
```

즉, Animal cat = new Animal() 처럼 cat 이라는 객체를 생성했다면 이 cat 객체의 객체 변수 name에는 다음과 같이 접근할 수 있다.

```java
cat.name   // 객체: cat, 객체변수: name
```

이제 객체 변수에 어떤 값이 대입되어 있는지 다음과 같이 출력해 보자.

```java
public class Animal {
    String name;

    public static void main(String[] args) {
        Animal cat = new Animal();
        System.out.println(cat.name);
    }
}
```

실행해 보면 다음과 같은 결과가 출력된다.

```bash
null
```

cat.name을 출력한 결과값으로 null이 나왔다. null이라는 것은 값이 할당되어 있지 않은 상태를 말한다. 객체 변수로 name 을 선언했지만 아무런 값도 대입을 하지 않았기 때문에 null 이라는 값이 출력된 것이다.
