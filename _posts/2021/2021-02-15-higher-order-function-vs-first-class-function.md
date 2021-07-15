---
published: true
toc: true
categories:
  - terminology
tags:
  - terminology
---
## Higher order function
HIgher order function 은 2가지 특성을 가지고 있다.  
1. function 을 파라미터로 전달가능하다.  
2. function 을 리턴할 수 있다.

예제
```kotlin
fun printMe(s: String) {
  println(s)
}

fun higherfunc( str : String, myfunc: (String) -> Unit) {
  myfunc(str)
}

@Test
fun higherOrder_test() {
  higherfunc("higher order function example", ::printMe)
}
```

## First class function
First class function 은 다음 3가지 특성을 가지고 있다.  
1. function 을 파라미터로 전달가능하다.
2. function 을 리턴할 수 있다.
3. __function 을 변수에 할당 가능하다.__

위예제에 아래같이 변수에 할당 특성이 추가됨
```kotlin
val f = printMe("print this")
```

## 정리
비슷한 개념이긴 하지만 Higher order function 개념은 First class function 개념의 하위라고 볼 수 있다.  
programming language 에서 First class citizen 의 개념이 파라미터 전달/리턴/변수에 할당 이며, 이를 만족하는 function 을 first class function 이라고 보면 된다.

[First class citizen](https://en.wikipedia.org/wiki/First-class_citizen)








