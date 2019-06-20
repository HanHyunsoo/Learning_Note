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

## 메소드

자, 이제 객체변수에 접근하는 방법과 현재 값이 할당되어 있지 않은 상태에 대해서 알게 되었다. 이제 객체 변수에 값을 대입하는 것에 대해서 알아보도록 하자.

객체 변수에 값을 대입하는 방법에는 여러가지가 있을 수 있지만 여기서는 가장 보편적인 방법인 메소드를 이용하는 방법에 대해서 알아보자.

클래스에는 객체 변수와 더불어 **메소드(Method)** 라는 것이 있다. 메소드는 클래스 내에 구현된 함수를 의미하는데 보통 함수라고 말하지 않고 메소드라고 말한다.

이제 메소드를 이용하여 Animal 클래스의 객체 변수인 name 에 값을 대입해 보도록 하자.

아래와 같이 setName 메소드를 추가 해 보자.

```java
public class Animal {
    String name;

    public void setName(String name) {
        this.name = name;
    }

    public static void main(String[] args) {
        Animal cat = new Animal();
        System.out.println(cat.name);
    }
}
```

Animal클래스에 추가된 setName메소드는 다음과 같은 형태의 메소드이다.

* 입력: String name
* 출력: void (리턴값 없음)

즉, 입력으로 name이라는 문자열을 받고 출력은 없는 형태의 메소드이다.

이번에는 setName 메소드의 내부를 살펴보자. setName 메소드는 다음의 문장을 가지고 있다.

```java
this.name = name;
```

여기서 `this`에 대해서 이해하는 것은 꽤 중요하다. 이 문장에 대한 설명은 잠시 보류하고 일단은 우선 이 메소드를 호출 하는 방법에 대해서 먼저 알아보자.

객체 변수에 접근하기 위해서 `객체.변수` 와 같이 도트연산자(.)로 접근할 수 있었던 것과 마찬가지로 객체가 메소드를 호출하기 위해서는 `객체.메소드` 로 호출할 수 있다.

즉, 우리가 만든 setName메소드를 호출하려면 다음과 같이 호출해야 한다.

```java
cat.setName("boby");
```

여기서 setName메소드의 입력으로 문자열을 전달해야 한다. 왜냐하면 setName메소드는 입력항목으로 문자열을 필요로 하기 때문이다.

setName메소드를 호출할 수 있도록 main메소드를 다음과 같이 수정해 보자.

```java
public static void main(String[] args) {
    Animal cat = new Animal();
    cat.setName("boby");  // 메소드 호출
    System.out.println(cat.name);
}
```

이렇게 수정하고 다시 실행하면 이제 setName메소드가 호출 될 것이다.

자, 이제 아까 설명을 잠시 보류한 setName메소드의 다음 문장을 다시 보도록 하자.

```java
this.name = name;
```

main메소드에서 `cat.setName("boby")` 와 같이 "boby"라는 입력값으로 setName 메소드를 호출했기 때문에 setName함수의 입력항목 name에는 "boby"라는 문자열이 전달될 것이다.

따라서 setName 메소드의 `this.name = name;` 문장은 다음과 같이 해석되어 질 것이다.

```java
this.name = "boby";
```

setName 메소드 내부에 사용된 `this`는 Animal 클래스에 의해서 생성된 객체를 지칭한다. 만약 `Animal cat = new Animal()` 과 같이 cat이라는 객체를 만들고 `cat.setName("boby")` 와 같이 cat객체에 의해 setName 메소드를 호출하면 setName 메소드 내부에 선언된 this는 바로 cat 객체를 지칭하게 된다.

만약 `Animal dog = new Animal()`로 dog 객체를 만든 후 `dog.setName("happy")` 와 같이 호출한다면 setName 메소드 내부에 선언된 this는 바로 dog 객체를 가르키게 된다.

따라서 `this.name = "boby";` 문장은 다시 다음과 같이 해석되어 진다.

```java
cat.name = "boby";
```

`cat.name` 과 같이 하면 객체 변수에 접근할 수 있음을 우리는 알고 있다. 객체 변수에 값을 대입하는 방법은 아주 쉽다. 그냥 변수에 값을 대입하는 것과 마찬가지 방법이다.

```java
객체.객체변수 = 값
```

따라서 `cat.name = "boby"`라는 문장은 객체 cat의 객체변수 name에 "boby"라는 값을 대입하게 된다.

Animal 클래스를 다시 실행 해 보자.

다음과 같은 문자열이 출력되는 것을 확인할 수 있을 것이다.

```bash
boby
```

cat.name은 이제 null이 아니라 "boby"임을 확인할 수 있다.
