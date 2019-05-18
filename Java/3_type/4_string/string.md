# 문자열

자바에서 문자열에 해당하는 자료형은 String이다.

문자열을 자바에서 표현하려면 다음과 같이 사용한다.

```java
String a = "Hello world!";
String b = "a";
String c = "123";
```

위 예제는 다음과 같이 사용해도 된다.

```java
String a = new String("Hello world!");
String b = new String("a");
String c = new String("123");
```

`new`라는 키워드는 객체를 만들 때 사용한다.

String형은 객체형이기 때문에 new라는 키워드를 쓴다.

보통 문자열을 표현할때 첫번째 예제와 같이 쓰는게 좋다. 가독성이 있고 컴파일 시 최적화에 도움을 주기 때문이다.

## primitive(원시) 자료형

이전에 살펴 보았던 int, long, double, float, boolean, char 등을 primitive 자료형 이라고 부른다.

이런 primitive 자료형은 `new` 키워드로 생성할 수 없다.

primitive 자료형은 다음과 같이 리터럴(literal)로 값을 세팅할 수 있다. (※ 리터럴은 계산식 없이 소스코드에 표기하는 상수 값을 의미한다.)

```java
boolean result = true;
char capitalC = 'C';
int i = 1;
```

String형은 "Hello world!"와 같이 리터럴로 표기는 가능하지만 primitive 자료형은 아니다.(리터럴 표현식을 사용할 수 있도록 자바에서 특별 대우 해 주는 자료형이다.)

## String Method

String 자료형에는 여러가지 유용한 메소드들이 있다. 자주사용되는 것들을 알아보자.

### equals

equals는 두개의 문자열이 동일한 값을 가지고 있는지 비교하여 부울값을 결과로 리턴한다.

```java
String a = "hello";
String b = "java";
String c = "hello";
System.out.println(a.equals(b)); // false
System.out.println(a.equals(c)); // true
```

String a와 String b는 같지 않다. 따라서 equals 메소드를 호출 하면 false를 리턴한다.

String a와 String c는 같다. 따라서 true를 리턴한다.

문자열 값을 비교할 때는 반드시 equals를 사용해야한다. `==` 연산자를 사용할 경우 다음 예시 같은 상황이 발생한다.

```java
String a = "hello";
String b = "hello";
System.out.println(a.equals(b)); // true
System.out.println(a == b); // false
```

a와 b는 값이 똑같지만 `==` 연산자를 사용하면 false가 리턴되는데 이유는 두 문자열 변수의 값을 비교하는 것이 아니라 객체를 비교하는 것이다. (정확히는 객체의 레퍼런스)

### indexOf

indexOf는 문자열에서 특정 문자가 시작되는 인덱스를 리턴한다.

```java
String a = "Hello world!";
```

위와 같은 a라는 문자열에서 "world!"라는 문자열이 시작되는 위치를 알고 싶은 경우에 indexOf를 다음과 같이 사용 한다.

```java
System.out.println(a.indexOf("world!")); // 결과값 6
```

문자열 a에서 "world!"라는 문자는 7번째 문자('w')부터 시작이다. 결과값이 6으로 나온 이유는 자바는 숫자를 0부터 세기 때문이다.

indexOf 메소드는 대소문자를 구분하고 문자열의 왼쪽부터 값을 찾는다.

```java
String a = "123451";
System.out.println(a.indexOf("1")); // 결과값 0
```

예를 들어 위 예시와 같이 마지막에 있는 '1'의 인덱스를 찾고싶은데 indexOf를 쓰면 왼쪽에서부터 찾기때문에 0을 리턴한다.

그래서 오른쪽부터 값을 찾고싶으면 lastIndexOf 메소드를 쓰면된다.

```java
System.out.println(a.lastIndexOf("1")); // 결과값 5
```

lastIndexOf는 indexOf 메소드와 똑같지만 문자열 오른쪽부터 값을 찾는다.

### replaceAll

replaceAll은 문자열 중 특정 문자를 다른 문자로 바꾸고 싶을 경우에 사용한다.

```java
String a = "Hello world";
System.out.println(a.replaceAll("world", "java"));
```

결과값은 다음과 같다.

```bash
Hello java
```