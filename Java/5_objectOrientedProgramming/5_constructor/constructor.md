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
