# 숫자

## 정수

정수형은 아래 표와 같이 4가지가 있다.

|데이터 타입|메모리의 크기|표현 가능 범위|
|---|---|---|
|byte|1 byte|-128 ~ 127|
|short|2 byte|-32,768 ~ 32,767|
|int|4 byte|-2,147,483,648 ~ 2,147,483,647|
|long|8 byte|-9,223,372,036,854,775,808 ~ 9,223,372,036,854,775,807|

여기서 int, long이 많이 쓰이므로 두가지를 설명 하겠다.

```java
int a = 10;
long b = 10000000000L;
```

long 변수에 값을 대입할 때는 대입하는 숫자 값이 int 자료형의 최대값인 2147483647 보다 큰 경우 `10000000000L`과 같이 `L` 접미사(또는 `l`)를 뒤에 붙인다.(안 붙이면 오류)

## 실수

자바의 실수를 표현하는 자료형은 float, double이 있다.

차이는 위 정수의 데이터 타입 같이 표현할 수 있는 숫자의 범위다.

아래와 같이 사용한다.

```java
float pi = 3.14F;
double morePi = 3.14159265358979323846;
```

자바에서 실수형은 디폴트가 double이므로 위의 예에서 보듯이 float 변수에 값을 대입할 때에는 3.14F 와 같이 `F`접미사(또는 `f`)를 붙여 주어야 한다.(안붙이면 오류)

그리고 과학적 지수 표현식으로 아래와 같이 사용 가능하다.

```java
double d1 = 1.234e2
double d2 = 123.1e-1
```

여기서 `double d1 = 1.234e2`에서 `e2`는 `10^2 = 100`을 의미하며 `123.4`가 된다.

마찬가지로 `d2 = 123.1e-1`에서 `e-1`은 `10^(-1) = 1 / 10`이므로 12.31이된다.

## 2, 8, 16진수

2진수, 8진수, 16진수는 int형 자료형을 사용하여 표기할 수 있다.

0b로 시작하면 2진수 0으로 시작하면 8진수 0x로 시작하면 16진수가 된다.

```java
int bin = 0b111; // 십진수: 7
int octal = 023;    // 십진수: 19
int hex = 0xC;     // 십진수: 12
```

## 사칙연산

자바에서는 `+, -, *, /` 기호를 이용하여 사칙 연산을 수행한다.
각각 더하기, 빼기, 곱하기, 나누기를 의미한다.

```java
int a = 10;
int b = 4;
System.out.println(a + b); // 14
System.out.println(a - b); // 6
System.out.println(a * b); // 40
System.out.println(a / b); // 2
System.out.println((double)a / b) // 2.5
```

위에서 `a / b` 가 원래 수학 사칙연산에서는 `2.5` 이지만 
a, b가 둘다 int형 이기 때문에 몫 값이 출력된다.
따라서 소수점을 포함해서 원하는 값을 얻으려면 마지막 줄처럼 `(double)`을
명시해주거나 변수 타입이 한개라도 double형 이여야한다.

위 사칙연산 이외에도 연산자가 하나 더있는데 `%` 이다.
`%` 기호는 나머지를 계산한다.

## 증감연산(++, --)

```java
int a = 0;
int b = 10;
a++;
b--;
System.out.println(a); // 1
System.out.println(b); // 9
```

위 예시와 같이 `++` 는 값을 1씩 증가시키는 연산, `--` 는 값을 1씩 감소하는 연산이다.

이외에도 증감연산의 위치에따라 연산 순서가 정해진다. 아래 예시를 보자

```java
int i = 0;
System.out.println(i++); // 0
System.out.println(i);   // 1

i = 0; // 0으로 다시 초기화
System.out.println(++i) // 1
System.out.println(i)   // 1
```

위와 같이 `++` 를 앞에 명시하면 값이 먼저 증가된후 참조된다 즉 정리하자면

* `i++` : i의 값이 먼저 참조된 후 증가
* `++i` : i의 값이 참조 되기 전 증가 

`--` 연산자도 마찬가지로 위 규칙과 같다.