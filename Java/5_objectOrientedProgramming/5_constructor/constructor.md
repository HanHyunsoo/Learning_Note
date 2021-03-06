# 생성자

다음과 같은 Person 클래스가 있다고 하자.

```java
class Person {
    String name;
}
```

클래스이 준비가 되었다면 이제 Person 클래스의 main메소드를 다음과 같이 수정한 후 실행 해 보자.

```java
    public static void main(String[] args) {
        Person p = new Person();
        System.out.println(p.name);
    }
```

name 객체 변수에 아무런 값도 설정하지 않았기 때문에 null이 출력될 것이다.

이렇듯 Person 클래스는 코딩하기에 따라 객체 변수 name에 값을 설정할 수도 있고 설정 안할 수도 있다. 그렇다면 name 이라는 객체 변수에 값을 무조건 설정해야만 객체가 생성될 수 있도록 강제할 수 있는 방법은 없을까?

**생성자(Constructor)** 를 이용하면 된다.

클래스 가장 상단에 다음과 같은 메소드를 추가해 보자.

```java
    public Person(String name) {
        this.name = name;
    }
```

위 메소드처럼 메소드명이 클래스명과 동일하고 리턴 자료형이 없는 메소드를 생성자(Constructor)라고 말한다.

***생성자의 규칙***

1. 클래스명과 메소드명이 동일하다.
2. 리턴타입을 정의하지 않는다.

생성자는 객체가 생성될 때 호출된다. 객체가 생성될 때는 new라는 키워드로 객체가 만들어질 때이다.

즉, 생성자는 다음과 같이 new라는 키워드가 사용될 때 호출된다.

```java
new 클래스명(입력항목, ...)
```

생성자는 메소드와 마찬가지로 입력을 받을 수 있다.

우리가 만든 생성자는 입력값으로 문자열을 필요로 하는 생성자이다.

따라서 다음과 같이 new 키워드로 객체를 만들때 문자열을 전달해야만 한다.

```java
Person p = new Person("HanHyunSoo")   // 생성자 호출 시 문자열을 전달해야 한다.
```

만약 다음처럼 코딩하면 컴파일 오류가 발생할 것이다.

```java
Person p = new Person();
```

오류가 발생하는 이유는 객체 생성 방법이 생성자의 규칙과 맞지 않기 때문이다. 생성자가 선언된 경우 생성자의 규칙대로만 객체를 생성할 수 있다.

다음은 생성자가 적용된 완성된 Person 클래스이다.

```java
class Person {
    String name;

    public Person(String name) {
        this.name = name;
    }

    public static void main(String[] args) {
        Person p = new Person("HanHyunSoo")
        System.out.println(p.name);
    }
}
```

이제 main메소드를 실행하면 다음의 결과가 출력되는 것을 확인 할 수 있다.

```java
HanHyunSoo
```

이렇듯 생성자를 사용했을 때 얻게 되는 이득은 객체 생성과 동시에 객체의 인스턴스 값들을 설정할 수 있으므로 코드가 보다 간결해지고 편해진다.

## default 생성자

이번에는 default 생성자에 대해서 알아보자.

다음의 코드를 보자.

```java
public Person {
    String name;
}
```

그리고 다음 코드를 보자.

```java
public Person {
    String name;

    public Person() {
    }
}
```

첫번째 코드와 두번째 코드의 차이점은 무엇일까? 두번째 코드에는 생성자가 구현되어 있다. 생성자의 입력 항목이 없고 생성자 내부에 아무 내용이 없는 위와 같은 생성자를 default 생성자라고 부른다.

위와 같이 디폴트 생성자를 구현하면 new Person() 로 Person 객체가 만들어 질 때 위 디폴트 생성자가 실행된다.

만약 클래스에 생성자가 하나도 없다면 컴파일러는 자동으로 위와같은 디폴트 생성자를 추가한다. 하지만 사용자가 작성한 생성자가 하나라도 구현되어 있다면 컴파일러는 디폴트 생성자를 추가하지 않는다.

※ 이러한 이유로 위에서 살펴본 Person 클래스에 name을 입력으로 받는 생성자를 만든 후에 new Person() 는 사용할 수 없게 되는 것이다. (Person클래스에 이미 생성자를 만들었기 때문에 컴파일러는 디폴트 생성자를 자동으로 추가하지 않는다.)

## 생성자 오버로딩

하나의 클래스에 여러개의 입력항목이 다른 생성자를 만들 수 있다.

즉, 다음과 같은 것이 가능하다.

```java
class Person {
    String name;

    public Person() {
        this.name = "없음";
    }

    public Person(String name) {
        this.name = name;
    }

    public static void main(String[] args) {
        Person unknown = new Person();
        Person person = new Person("HanHyunSoo");
        System.out.println(unknown.name);
        System.out.println(person.name);
    }
}
```

위 Person 클래스는 두 개의 생성자가 구현되어 있다. 하나는 String 자료형을 입력으로 받는 생성자이고 다른 하나는 입력을 받지 않는 생성자이다. 두 생성자의 차이는 입력 항목이다. 이렇게 입력 항목이 다른 생성자를 여러 개 만들 수 있는데 이런 것을 생성자 오버로딩(Overloading) 이라고 말한다. (※ 메소드 오버로딩과 마찬가지 개념이다.)

이제 Person 객체는 다음과 같이 두 가지 방법으로 생성이 가능하다.

```java
Person unknown = new Person();
Person person = new Person("HanHyunSoo");
```

main메소드를 실행하면 다음과 같은 결과가 출력될 것이다.

```bash
없음
HanHyunSoo
```
