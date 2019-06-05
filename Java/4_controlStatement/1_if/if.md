# if 문

`돈이 있으면 택시를 타고 가고 돈이 없으면 걸어 간다.`

위와 같은 상황은 우리 주변에서 언제든지 일어 날 수 있는 상황중의 하나이다. 프로그래밍도 위처럼 조건을 판단해서 그 상황에 맞게 처리해야 할 경우가 생기게 된다. 이렇듯 조건을 판단하여 해당 조건에 맞는 상황을 수행하는데 쓰이는 것이 바로 if문이다.

위와 같은 상황을 자바에서는 다음과 같이 만들 수 있다.

```java
boolean money = true;
if (money) {
    System.out.println("택시를 타고 가라");
} else {
    System.out.println("걸어가라");
}
```

## if문의 기본 구조

다음의 구조가 if와 else를 이용한 기본적인 구조이다.

```java
if (조건문) {
    <수행할 문장1>
    <수행할 문장2>
    ...
} else {
    <수행할 문장A>
    <수행할 문장B>
    ...
}
```

조건문을 테스트 해서 참이면 if문 바로 다음의 문장들을 수행하고 조건문이 거짓이면 else문 다음의 문장들을 수행하게 된다.

**조건문이란 무엇인가?**

if (조건문) 에서 사용되는 조건문이란 참과 거짓을 판단하는 문장을 말한다.

따라서 위의 예에서 보았던

```java
boolean money = true;
if (money) {
...
```

에서 조건문은 money가 되고 money는 true이기 때문에 if문 다음의 문장을 수행하게 되는 것이다.

## 비교연산자

조건판단을 하는 경우 true 또는 false와 같이 boolean 자료형을 쓰는 것 보다 비교 연산자(<, >, ==, !=, >=, <=)를 쓰는 경우가 훨씬 많다.

다음 표는 비교연산자의 종류와 설명이다.

|비교연산자|설명|
|---|---|---|
|x < y|x가 y보다 작다|
|x <= y|x가 y보다 작거나 같다|
|x > y|x가 y보다 크다|
|x >= y|x가 y보다 크거나 같다|
|x == y|x와 y가 같다|
|x != y|x와 y가 같지 않다|

예시

```java
int x = 3;
int y = 1;
System.out.println(x < y); // false
System.out.println(x > y); // true
System.out.println(x == y); // false
System.out.println(x != y); // true
```

위 예시와 같이 비교연산자를 사용하면 boolean 자료형(true 또는 false)이 반환된다.

`만약 3000원 이상의 돈을 가지고 있으면 택시를 타고 그렇지 않으면 걸어가라`

위 상황이 있다면 다음과 같이 코드를 만들 수 있을 것이다.

```java
int money = 2000;
if (money >= 3000) {
    System.out.println("택시를 타고 가라");
} else {
    System.out.println("걸어가라");
}
```

위에서 money는 2000인데 money >= 3000 에서 false가 반환 되기때문에 else구문으로 간다.

## and(&&), or(||), not(!)

또 다른 조건 판단에 쓰이는 것으로 and, or, not이란 것이 있다.

각각의 연산자는 다음처럼 동작을 한다.

* x || y - x와 y 둘 중 적어도 하나가 참이면 참이다
* x && y - x와 y 모두 참이어야 참이다
* !x - x가 거짓이면 참이다

"돈이 3000원 이상 있거나 카드가 있다면 택시를 타고 그렇지 않으면 걸어가라"

위 예시를 통해 자바 코드를 만들어 보면 아래와 같다.

```java
int money = 2000;
boolean hasCard = true;

if (money >= 3000 || hasCard) {
    System.out.println("택시를 타고 가라");
} else {
    System.out.println("걸어가라");
}
```

money는 2000이지만 hasCard가 true이기 때문에 `money >= 3000 || hasCard`라는 조건문이 참이 되어 if문 다음의 문장이 수행된다.

## contains

List 자료형에는 해당아이템이 있는지 조사하는 contains라는 메소드가 있다. contains메소드는 조건문에 많이 활용되는데 어떻게 활용이 되는지 살펴보도록 하자.

다음의 경우를 예제에 적용시켜 보자.

`만약 주머니에 돈이 있으면 택시를 타고, 없으면 걸어가라`

```java
ArrayList<String> pocket = new ArrayList<String>();
pocket.add("paper");
pocket.add("handphone");
pocket.add("money");

if (pocket.contains("money")) {
    System.out.println("택시를 타고 가라");
} else {
    System.out.println("걸어가라");
}
```

pocket 리스트에 안에 'money'가 있으므로 pocket.contains("money")는 참이 되어서 if문 다음의 문장이 수행되었다.
