# 부울

참(true) 또는 거짓(false)의 값을 가지는 자료형을 부울 자료형이라고 한다.

자료형 명칭은 boolean이다.

```java
// 예제
boolean boolTrue = true;
boolean boolFalse = false;
```

## 부울 연산

부울 연산은 참, 거짓을 판단하는 연산을 말한다.

부울 연산은 `==, !=, <, <=, >, >=`이 기본적으로 있다.

```java
// 예제
2 > 1 // 참
1 == 2 // 거짓
(3 % 2) == 1 // 참 (3을 2로 나눈 나머지는 1이므로 참)
"abcd".equals("bcde") // 거짓(String 객체에서 지원하는 '같다' 연산자)
```

위에서 `equals()` 함수 대신 `==`를 쓴 이유는 String형은 객체이기때문에 `==`를 쓰면 false를 반환한다.

객체끼리의 비교는 `==`를 쓰면 객체의 메모리값을 비교하기때문에 원하지 않는 값이 나온다.

따라서 `equals()`함수를 써서 객체의 값만 비교하는 것이다.

## 그 외 부울 자료형의 사용처

부울 자료형은 대부분 조건문, 반복문에 많이 사용된다.

이 부분들은 나중에 따로 정리하겠다.