---
description: Short-Circuit Evaluation
---

# 단락평가\(SCE\)

## 개념

* 논리 연산자 && 혹은 \|\|를 포함한 연산 결과 True/False에서 앞의 연산을 통해서 뒤의 연산 결과 전에 판단을 완료하는 것
* **"나머지 연산을 수행할 필요가 없을 때 사용된다"**

## &&

```java
//&& 조건
if (vo != null && vo.getUserName() == "유저") {
    System.Out.Println("ㅋ")
}
```

* **&& 조건\(false를 만났을 시 뒤의 연산 X\)** "vo != null"이라는 조건에서 vo == null가 false라면 vo.getUserName\(\) == "유저"의 연산을 실행하지 않고 결과 도출

## \|\|

```java
//|| 조건
if (vo == null || vo.getUserId() < 5) {
    System.Out.Println("ㅋ")
}
```

* **\|\| 조건\(True를 만났을 시 뒤의 연산 X\)** "vo != null"이라는 조건에서 vo == null가 true라면 vo.getUserId\(\) &lt; 5의 연산을 실행하지 않고 결과 도출

## 정리

```java
true && true // true
true && false // false
true || false // true
false || true // true
```

