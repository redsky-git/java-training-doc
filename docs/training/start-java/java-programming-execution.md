---
sidebar_position: 1
displayed_sidebar: 'trainingDocSidebar'
title: '⋮ Java 프로그래밍'
---

# Java 프로그래밍


## HelloJava.java 파일 생성
---
```java showLineNumbers
// HelloJava.java --------------------------
public class HelloJava { // HelloJava 클래스의 범위 시작

  public static void main(String[] args) { // main() 메서드의 범위 시작
    System.out.println("hello java!");
  }

}
```

:::tip <span class="admonition-title">Java</span> 파일과 클래스 규칙
* **public 클래스**는 반드시 파일명과 같아야 하고, 파일 하나에 하나만 존재한다. 하지만 **non-public 클래스**는 여러개 정의할 수는 있다.
* main 메서드는 JVM 진입점을 쓰려면 필수. 하지만 class에 main 메서드가 없어도 됨.
:::

:::tip <span class="admonition-title">JVM / JRE / JDK</span>에 대하여
```
┌─────────────────────────────┐
│           JDK               │  ← 개발자용 (개발 + 실행 모두)
│  ┌───────────────────────┐  │
│  │         JRE           │  │  ← 실행만 할 때
│  │  ┌─────────────────┐  │  │
│  │  │      JVM        │  │  │  ← 실제 실행 엔진
│  │  └─────────────────┘  │  │
│  └───────────────────────┘  │
└─────────────────────────────┘
```

|        | 역할            | 포함 내용             |
| :----- | :-------------- | :------------------- |
| JVM    | 바이트코드 실행   | 실행 엔진              |
| JRE    | 실행 환경        | JVM + 표준 라이브러리   |
| JDK    | 개발 환경        | JRE + 컴파일러(javac) + 개발 도구 |
:::