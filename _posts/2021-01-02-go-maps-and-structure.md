---
layout: post
date: 2021-01-02
title:  "[Go 도전기] 7. Map & Structure"
excerpt: "Go"
categories: go
---

Go 에서는 타 언어에서 주로 사용하던 Class 와 Object 가 없다.  
그래서 이제 알아야 할 `Structure` 가 중요한데, 그 전에 `Map` 에 대해서도 알아보자.

### 1. Map
 기본적으로 `key - value` 의 형태를 가지고 있고, key 와 value 도 타입이 필요하다.
```go 
den := map[string]string{"name: "den", "age": "31"}
```
위의 예제처럼 대괄호 `[]` 안에 key에 대한 타입을 명시해주고, 그 뒤에 value에 대한 타입도 지정해준다.  
그러면 사실 나이는 `int` 형이어야 하고, 실질적으로는 유동적으로 여러 타입이 가진게 유용할텐데, 그런 것들은 어떻게 해야할까?  

### 2. Structure
 위의 문제를 해결해줄 수 있는 것이 `Structure` 이다.  
코드로 살펴보자
```go 
type person struct {
  name string
  age int
  favFood []string
}

favFood := []string{"sujebi", "spicy"}
den := person{
  "den"
  31,
  favFood,
}

for key, value := range den {
  fmt.Println(key, value)
}

den2 := person{
  name: "den2",
  age: 31,
  favFood: favFood,
}

fmt.Println(den2)
```
Structure 안에 여러 타입을 지정해서 마치 오브젝트 처럼 사용해줄 수 있다,  
또한, 위에 변수를 지정해준 방식처럼 2가지 방식으로 가능한데,  
- 하나는 value 만 쓰는 것,
- 다른 하나는 key 와 value 를 모두 쓰는 것,  

개인적으로는 후자의 방법을 더 좋아한다.  
굳이 위의 선언문을 보지 않아도, 명시직이기때문이다.


