---
sidebar_position: 1
displayed_sidebar: 'trainingDocSidebar'
title: '⋮ 연산자'
---

# Java 연산자


## 산술 연산자
---
* 산술 연산자는 숫자 값을 계산하는 데 사용됩니다.
* 산술 연산자는 다음과 같습니다.
  - 덧셈: `+`
  - 뺄셈: `-`
  - 곱셈: `*`
  - 나눗셈: `/`
  - 나머지: `%`


:::info[그 외 연산자]

* 증감 연산자: `++`, `--`
* 비교 연산자: `==`, `!=`, `>`, `<`, `>=`, `<=`
* 논리 연산자: `&&`, `||`, `!`
* 대입 연산자: `=`, `+=`, `-=`, `*=`, `/=`, `%=`
* 삼항 연산자: `? :`

:::

```java showLineNumbers
package operator;
public class Operator1 {
    public static void main(String[] args) {
        // 변수 초기화
        int a = 5;
        int b = 2;
        // 덧셈
        int sum = a + b;
        System.out.println("a + b = " + sum);  // 출력: a + b = 7
        // 뺄셈
        int diff = a - b;
        System.out.println("a - b = " + diff);  // 출력: a - b = 3
        // 곱셈
        int multi = a * b;
        System.out.println("a * b = " + multi);  // 출력: a * b = 10
        // 나눗셈
        int div = a / b;
        System.out.println("a / b = " + div);  // 출력: a / b = 2
        // 나머지
        int mod = a % b;
        System.out.println("a % b = " + mod);  // 출력: a % b = 1
    }
}
```

* **주의! `0` 으로 나누기**
  - `10 / 0` 과 같이 숫자는 0으로 나눌 수 없다. (수학에서 허용하지 않음) - 오류가 발생함.
    ```java
    Exception in thread "main" java.lang.ArithmeticException: / by zero
    ```




## 문자열 더하기
---
```java showLineNumbers
package operator;

public class Operator2 {
    static void main(String[] args) {
        //문자열과 문자열 더하기1
        String result1 = "hello " + "world";
        System.out.println(result1);

        //문자열과 문자열 더하기2
        String s1 = "string1";
        String s2 = "string2";
        String result2 = s1 + s2;
        System.out.println(result2);

        //문자열과 숫자 더하기1
        String result3 = "a + b = " + 10;
        System.out.println(result3);

        //문자열과 숫자 더하기2
        int num = 20;
        String str = "a + b = ";
        String result4 = str + num;
        System.out.println(result4);
    }
}
```

* 자바는 문자열인 `String`타입에 다른 타입을 더하는 경우 대상 타입을 문자열로 변경한다. 쉽게 이야기해서 문자열에 더하는 것은 다 문자열이 된다.




## 연산자 우선순위
---
* 연산자 우선순위는 다음과 같습니다.

:::tip[연산자 우선순위]

1. **[괄호 ()]**
2. **[단항 연산자]**(예: `++`, `--`, `!`, `~`, `new`, `(type)`)
3. **[산술 연산자]**(`*`, `/`, `%`(우선, 그 다음에 `+`, `-`))
4. **[Shift 연산자]**(예: `<<`, `>>`, `>>>`)
5. **[비교 연산자]**(예: `<`, `<=`, `>`, `>=`, `instanceof`)
6. **[등식 연산자]**(예: `==`, `!=`)
7. **[비트 연산자]**(예: `&`, `|`, `^`)
8. **[논리 연산자]**(예: `&&`, `||`, `!`)
9. **[삼항 연산자]**(예: `? :`)
10. **[대입 연산자]**(예: `=`, `+=`, `-=`, `*=`, `/=`, `%=`)

:::

  - 곱셈 * / %(우선순위 높음)   →   덧셈 + - (우선순위 낮음)
  - 괄호()는 우선순위 가장 높음
  - 복잡한 연산자는 그냥 괄호를 넣어서 가독성을 넣는게 좋다. 
  - 연산자 우선순위는 외우는게 아니라 헷갈리면 괄호를 넣고, 상식선에서 우선 순위를 생각하면 된다.






## 증감 연산자
---
* 증감 연산자는 변수의 값을 1씩 증가 또는 감소시키는 연산자입니다.
* 증감 연산자는 다음과 같습니다.
  - 증가: `++`
  - 감소: `--`


```java showLineNumbers
package operator;

public class Operator3 {
    static void main() {
        // 증감 연산자
        int a = 0;
        System.out.println("a = " + a);

        a = a + 1;
        System.out.println("a = " + a);

        ++a; // a = a + 1; 와 같음
        System.out.println("a = " + a);

        --a; // a = a - 1; 와 같음
        System.out.println("a = " + a);
    }
}
```
* **전위, 후위 증감연산자**  
증감 연산자는 피연산자 앞에 두거나 뒤에 둘 수 있으며, 연산자의 위치에 따라 연산이 수행되는 시점이 달라진다.
  - `++a`: 증감 연산자를 피연산자 앞에 둘 수 있다. 이것을 앞에 있다고 해서 전위(Prefix) 증감 연산자라 한다.
    - `b = ++a`: `a`를 1 증가시킨 후 `b`에 할당한다.
  - `a++`: 증감 연산자를 피연산자 뒤에 둘 수 있다. 이것을 뒤에 있다고 해서 후위(Postfix) 증감 연산자라 한다.
    - `b = a++`: `a`를 `b`에 할당한 후 `a`를 1 증가시킨다.






## 비교 연산자
---
* 비교 연산자는 두 값을 비교하는 연산자입니다. 결과는 **boolean** 타입으로 반환된다.
* 문자열 비교는 `==` 또는 `!=` 연산자를 사용하지 않고, `equals()` 메서드를 사용한다.
* 비교 연산자는 다음과 같습니다.
  - 같음(동등성): `==`
  - 같지 않음(불일치): `!=`
  - 크다(Greater than): `>`
  - 작다(Less than): `<`
  - 크거나 같다(Greater than or equal to): `>=`
  - 작거나 같다(Less than or equal to): `<=`


```java showLineNumbers
package operator;

public class Operator4 {
    static void main() {
        int a = 10;
        int b = 20;

        System.out.println(a == b); // false
        System.out.println(a != b); // true
        System.out.println(a > b); // false
        System.out.println(a < b); // true
        System.out.println(a >= b); // false
        System.out.println(a <= b); // true

        // 결과를 boolean 변수에 저장할 수 있다.
        boolean result = a == b;

        // 문자열 리터럴 비교
        boolean result2 = "hello".equals("hello"); // true
    }
}
```





## 논리 연산자
---
* 논리연산자는 `boolean` 타입인 `true`, `false`를 비교하는데 사용한다.
* 논리연산자는 다음과 같습니다.
  - 논리곱(AND): `&&`
  - 논리합(OR): `||`
  - 논리부정(NOT): `!`


```java showLineNumbers
package operator;

public class Operator5 {
    static void main() {
        boolean a = true;
        boolean b = false;

        System.out.println(true && true); // true
        System.out.println(true && false); // false
        System.out.println(false && false); // false
        System.out.println(true || true); // true
        System.out.println(true || false); // true
        System.out.println(false || false); // false
        System.out.println(!true); // false
        System.out.println(!false); // true
        // 변수 활용
        System.out.println(a && b); // false
        System.out.println(a || b); // true
    }
}
```


## 대입 연산자
---
* 값을 변수에 할당하는 연산자 `=`
* 축약(복합) 연산자: `+=`, `-=`, `*=`, `/=`, `%=`


```java showLineNumbers
package operator;

public class Operator6 {
    static void main() {
        int a = 10;
        a += 10; // a = a + 10;
        System.out.println(a);
        a -= 10; // a = a - 10;
        System.out.println(a);
        a *= 10; // a = a * 10;
        System.out.println(a);
        a /= 10; // a = a / 10;
        System.out.println(a);
        a %= 10; // a = a % 10;
        System.out.println(a);
    }
}
```