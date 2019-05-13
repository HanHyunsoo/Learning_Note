# 자바 시작

## 변수

```java
int a;
double b;
```

위와 같이 a, b를 변수(variable)라고 한다.

## 변수 명명 규칙

* 변수명은 숫자로 시작할 수 없다.
* _와 $ 문자 이외의 특수문자는 사용할 수 없다.
* 자바의 키워드는 변수명으로 사용할 수 없다. (예: int, class, return 등)
* 자바의 변수는 대소문자를 구별한다. (예: int a 와 int A는 다름.)

```java
int if; // if는 자바의 키워드명이므로 불가능
int 1a; // 숫자부터 시작하므로 불가능
int _$; // 변수명에서 허락한 특수문자는 _, $ 두개이므로 가능(비추천함)
```

그리고 변수명을 정할 때 의미에 맞는 변수명을 정하면 소스코드를 보기가 편하다. (예: 값을 저장하는 변수 이름을 정할때 int a 대신 int getValue로 지정하면 보기가 더 간편하다.)

 또 변수명에서 띄어쓰기가 필요할 때 _를 쓰거나 대문자로 구분한다. (get_value 또는 getValue)

## 변수 값 대입

 ```java
 int a;
 String b;

 a = 1; // int 자료형 a 변수에 1이라는 값을 대입.
 b = "Hello world!"; // String 자료형 b 변수에 b에 "Hello world!"를 대입.
 ```

 변수에 값을 대입할 때는 위 예시와 같이 = 기호를 사용하여 값을 대입한다.

위 소스코드는 초기화를 한 후 값을 집어넣는 방법인데 아래 코드와 같이 초기화와 값 대입을 동시에 할 수 있다.

```java
int a = 1;
String b = "Hello world!";
```

만약 int 자료형 변수 a에 문자열을 집어넣으면 어떻게 될까?

```java
int a = "Hello java";
```

VScode에서는 이런 오류가 뜬다.

```code
Type mismatch: cannot convert from String to int
```

오류메시지는 String자료형을 int자료형으로 변환할 수 없다는 오류이다.

## 자료형 종류

* int
* long
* double
* boolean
* char
* String
* 등등

## 주석

프로그램 소스코드에 프로그래머의 의견이나 설명을 적을 수 있는데 이런것을 주석(Comment)이라고 한다. 주석은 프로그램 소스에 삽입하더라도 프로그램 수행에 전혀 영향을 끼치지 않는다. 왜냐하면 컴파일 시 주석은 자동으로 제외되기 때문이다.

자바에서 주석은 두가지 종류가 있다.

1. 블록 주석

    ```java
    /* 메롱
    바보
    멍청이 */
    public class Main {
        ...
    }
    ```

    /* 가 블록 주석의 시작이고 */ 가 끝이다.

    보통 여러줄로 설명할 때 블록주석을 많이 사용한다.

2. 라인 주석

    ```java
    int cm; // 사람의 키
    ```

    // 기호를 사용하면 시작된 부분부터 라인이 끝나는 부분까지 주석 처리된다.

    한 줄로 주석을 할 때 많이 사용한다.

## 주석은 필요할 때만 달자

주석이 많다고 좋은 코드는 아니다.

```java
int a = 0;
a++; // a의 값을 증가.
```

위 코드를 보면 `a++;`에서 주석을 달았는데 자바 프로그래밍을 공부한 사람이라면 누구나 알 수 있는 부분이다.

따라서 주석은 다른사람이 보기에 이해가 안되는 부분이거나 헷갈리는 부분 즉 상황에 맞춰서 다는 것이 중요하다.

## main 함수

main 메소드는 프로그램의 시작을 의미한다. 만약 main 메소드가 없다면 프로그램을 단독으로 수행시킬 수 없다.

> main 함수를 사용하는 예제

```java
public class Test {
    public static void main(String[] args) {
        System.out.println("Hello World");
    }
}
```

위 코드에서 public, static, void 부분은 후에 다룰 예정이다.

main 메소드는 실행시 파라미터를 입력받을 수 있는데 이 입력받은 것은 띄어쓰기 기준으로 String[] args 배열에 저장된다.

위 Test 클래스를 작성후 cmd에 아래 명령어를 쓴다면

```bash
$ java Test a b c
Hello World
```

이와 같이 실행하면 `String[] args` 에는 입력으로 전달한 a b c 가 순서대로 저장되게 된다.