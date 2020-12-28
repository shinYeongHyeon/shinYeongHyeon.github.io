---
layout: post
date: 2020-12-28
title:  "[Go 도전기] 3. Functions"
excerpt: "Go"
categories: go
---

## Function
Go 에서는 꽤 유용한 기능들이 많고 Go 만의 특이점도 많다.  
아래에서 천천히 살펴보자.

### 1. 모든 타입 설정
정적 언어이다 보니 당연하게도 파라미터 타입과 리턴 타입을 설정해 주어야 한다.
그런데 만약, `multiply` 와 같은 곱셈 함수처럼 모든 파라미터가 같을 때 어느 정도 생략이 가능하다.
```go
func multiply(a int, b int) int {
  return a * b
}

function multiply2(a, b int) int {
  return a * b
}
```

### 2. 여러 값 반환
다른 언어에서 여러 값들을 반환 하려면 보통 Array / Object 를 이용해서 반환하며,  
리턴 타입이 Array / Object 가 된다.  
그러나 Go 에서는 여러 값 반환이 가능하다! (OMG ?)
```go
func lenAndUpper(name string) (int, string) {
  return len(name), strings.ToUpper(name)
}

func main() {
  stringLength, upperName := lenAndUpper("den")
  
  fmt.Println(stringLength) // 3
  fmt.Println(upperName)  // DEN
}
```

### 3. Args 받기
갯수를 알 수 없는 파라미터들을 받을 때는 타입에 `...`을 사용한다.  
계속해서 코드로 알아보자
```go
func repeatPrint(words ...string) {
  fmt.Println(words)
}

func main() {
  repeatPrint("den", "shin", "garlic") // [den shin yeong]
}
```

### 4. 리턴 타입에 변수 지정 후 아무 것도 리턴하지 않기
제목을 어떻게 지어야 할지 애매한데, 아무것도 리턴하지 않았는데 리턴이 되는 magic 이 있다.  
타입에 변수명을 미리 지정하기만 하면 되는데, 코드로 알아보자
```go
func lenAndUpper(name string) (length int, uppercase string) {
  length = len(name)
  uppercase = strings.ToUpper(name)
  
  return
}

func main() {
  stringLength, upeprName := lenAndUpper("den")
  
  fmt.Println(stringLength) // 3
  fmt.Println(upperName)  // DEN
}
```
신기해... ~~근데 사용은 안 할 듯~~

### 5. 끝날때 까지 끝난게 아니다
함수가 끝난 뒤에 실행이 되어야 하는 것들이 있다면 보통은 리턴 받고 나서 로직을 넣는데,
이거를 함수 내에서 설정할 수 있다, 즉 함수 자체에서 "내가 끝난 뒤에는 이것을 실행할거야!" 같은 건데,,,  
너무 멋있다... 코드로 보자
```go
func lenAndUpper(name string) (length int, uppercase string) {
	defer fmt.Println("I'm Done")

	length = len(name)
	uppercase = strings.ToUpper(name)

	return
}

func main() {
	totalLength, upperName := lenAndUpper("den")

	fmt.Println(totalLength)
	fmt.Println(upperName)
}

// I'm Done
// 3
// DEN
```
이거 너무 멋있지 않나 ? 이거 때문이라도 go 에 빠질듯...

