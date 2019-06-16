# for each 문

for each는 J2SE 5.0 부터 추가되었다. for each 라는 키워드가 따로 있는 것은 아니고 동일한 for를 이용한다. 하지만 조건식 부분이 조금 다르다. 보통 다른 언어에서 for each 라고 많이 하므로 자바에서도 보통 for each문이라고 말한다.

다음은 이전에 공부했던 평범한 for 문장이다.

```java
String[] numbers = {"one", "two", "three"};
for (int i = 0; i < numbers.length; i++) {
    System.out.println(numbers[i]);
}
```

for each 구조로 변경하면 다음과 같다.

```java
String[] numbers = {"one", "two", "three"};
for (String number: numbers) {
    System.out.println(number);
}
```

for each 문은 딱 보기에도 매우 직관적이지 않은가?

for each 문의 구조는 다음과 같다.

```java
for (type var: iterate) {
    body-of-loop
}
```

위 iterate는 루프를 돌릴 객체이고 iterate 객체에서 한개씩 순차적으로 var에 대입되어 for문을 수행하게 된다. iterate부분에 들어가는 타입은 루프를 돌릴수 있는 형태인 배열 및 ArrayList등이 가능하다.

다음은 위 예제를 ArrayList 로 재 구현한 예제이다. for문의 사용법은 String[] 배열을 사용했을 때와 완전히 동일하다.

```java
ArrayList<String> numbers = new ArrayList<String>();
numbers.add("one");
numbers.add("two");
numbers.add("three");

for (String number: numbers) {
    System.out.println(number);
}
```

단, foreach문은 따로 반복회수를 명시적으로 주는 것이 불가능하고, 1스탭씩 순차적으로 반복될때만 사용가능하다는 제약이 있다.
