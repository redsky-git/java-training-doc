---
sidebar_position: 1
displayed_sidebar: 'trainingDocSidebar'
title: '⋮ 변수'
---

# Java 변수

## 변수 선언
---
```java showLineNumbers
package variable;

public class Var1 {
    static void main(String[] args) {
        // highlight-start
        int a;
        a = 20;
        // highlight-end
        System.out.println(a);
        System.out.println(a);
        System.out.println(a);
    }
}
```

## 변수 사용
---
* 값 변경
```java showLineNumbers
package variable;

public class Var1 {
    static void main(String[] args) {
        int a;
        // highlight-start
        a = 10;
        // highlight-end
        System.out.println(a);
        // highlight-start
        a = 50;
        // highlight-end
        System.out.println(a);
    }
}
```
* 변수 선언, 초기화
  - 지역변수는 내가 반드시 초기화 해줘야함.(초기화를 하지 않으면 오류발생). 지역변수 외에 다른 변수는 java 가 자동으로 초기화 해줌.
```java showLineNumbers
package variable;

public class Var2 {
    static void main() {
        int a; // 변수 선언
        a = 1; // 변수 초기화
        System.out.println(a);
        int b; // 변수 선언
        b = 2; // 변수 초기화
        System.out.println(b);

        int c = 3; // 변수 선언, 초기화 한번에
        System.out.println(c);

        int d = 4, e = 5; // 여러 변수를 한꺼번에 선언, 초기화
        System.out.println(d);
        System.out.println(e);

        int f; // 변수는 선언하고 초기화를 필수로 해야 함
        System.out.println(f); // 오류발생 (java: variable f might not have been initialized)
    }
}
```

* 변수의 타입
  - **리터럴**: 변수에 직접 고정된 값을 할당(코드에 직접)하는 것
```java showLineNumbers
package variable;

public class Var3 {
    static void main() {
        int a = 100; // 정수
        double b = 10.5; // 실수
        boolean c = true; // 불리언(boolean) true, false
        char d = 'A'; // 문자 하나
        String e = "Hello Java!!"; // 문자열, 문자열을 다루기 위한 특별한 타입

        System.out.println(a);
        System.out.println(b);
        System.out.println(c);
        System.out.println(d);
        System.out.println(e);
    }
}
```
:::info[변수의 타입]

* 정수: int, long
* 실수: float, double
* 불리언: boolean
* 문자: char (작은 따옴표로 감싸야 함 ex: 'A')
* 문자열: String (큰 따옴표로 감싸야 함 ex: "Hello Java!!")

:::

* 다양한 숫자 타입 변수 (기본형)
```java showLineNumbers
package variable;

public class Var4 {
    static void main() {
        // 정수
        byte b = 127; // -128 ~ 127
        short s = 32767; // -32767 ~ 32767
        int i = 2147483647; // -2147483647 ~ 2147483647 (대부분 int를 씀, 넘어가면 long)
        long l = 9223372036854775807L; // -9223372036854775808 ~ 9223372036854775807

        // 실수
        float f = 10.0f; // 거의 사용하지 않음. 정밀도가 떨어짐.
        double d = 10.0; // 기본적으로 이것을 많이 씀.
    }
}
```

| 분류    | 타입      | 크기       | 범위                      | 기본값      |
| :------ | :-------- | :--------- | :---------------------- | :---------- |
| 정수    | byte      | 1byte     | -128 ~ 127                | 0          |
| 정수    | short     | 2byte     | -32,768 ~ 32,767          | 0          |
| 정수    | int       | 4byte     | -2,147,483,648 ~ 2,147,483,647 | 0          |
| 정수    | long      | 8byte     | -9.2 × 10¹⁸ ~ 9.2 × 10¹⁸     | 0L  // L 접미사 필수       |
| 실수    | float     | 4byte     | ±3.4 × 10³⁸ (소수 7자리)    | 0.0f  // f 접미사 필수     |
| 실수    | double    | 8byte     | ±1.7 × 10³⁰⁸ (소수 15자리)  | 0.0        |
| 문자    | char      | 2byte     | 0 ~ 65,535 (유니코드)       | '\u0000'   |
| 논리    | boolean   | 1byte     | true / false                | false      |

:::tip[변수 타입 정리]

* 실무에서 거의 사용하지 않는 변수
  - byte는 거의 사용하지 않음. 대신 파일을 바이트 단위로 다루기 때문에 파일 전송, 파일 복사 등에 주로 사용됨.
  - int를 많이 사용.
  - short는 표현 길이가 너무 작다. 그냥 int를 사용하는게 좋다. 거의 사용안함.
  - float은 정밀도가 떨어짐. 그냥 double을 사용하는게 좋다. 거의 사용안함.
  - char는 문자 하나를 표현할일이 거의 없음. 그냥 String을 사용하는게 좋다. 거의 사용안함.
* 사용 빈도가 높은 변수
  - 정수: int, long 사용.
  - 실수: double 사용.
  - 불린: boolean을 사용.
  - 문자열: String 사용.

:::







## 변수 명명 규칙
---
* **규칙**은 필수, **관례**는 필수는 아니지만 거의 따름. 사실상 규칙. 
* **규칙**
  - 숫자로 시작하지 않음 (예: 1num, 1st)
  - 이름에 공백이 들어갈 수 없음.
  - 자바 `예약어`는 변수 이름으로 사용 불가. (예: int, double, boolean, char, String, ...)
  - 변수 이름에는 영문자(a-z, A-Z), 숫자(0-9), 언더바(_), 달러($)만 사용 가능.

* **관례**
  - 변수 이름은 소문자로 시작. (예: num, name, age, ...)
  - 변수 복합 단어는 소문자로 시작. (예: studentName, studentAge, ...) -> 카멜케이스
  - 상수는 대문자로 시작. (예: MAX_VALUE, MIN_VALUE, ...)
  - 클래스 이름은 대문자로 시작. (예: Student, Person, ...) -> 파스칼케이스
  - 인터페이스 이름은 대문자로 시작. (예: MyInterface, MyInterface2, ...)
  - 추상 클래스 이름은 대문자로 시작. (예: MyAbstractClass, MyAbstractClass2, ...)
  - 열거 타입 이름은 대문자로 시작. (예: MyEnum, MyEnum2, ...)
  - 패키지 이름은 모두 소문자로 작성. (예: com.example.myapp, ...)