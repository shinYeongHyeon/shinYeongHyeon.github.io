---
layout: post
date: 2021-01-01
title:  "[Go 도전기] 6. Array & Slice"
excerpt: "Go"
categories: go
---

## Happy New Year 

 새해에도 Go 와 함께 시작 !  

### 1. Array
 Go 에서 Array 는 그 크기를 제한해주어야 한다. 또한, 그 타입도 지정해야 하며,  
 그 안에 값들을 세팅하는 것도 나로서는 좀 색달랐다.  
 코드로 살펴보자

 ```go
 names := [5]string{"shin", "yeong", "hyeon"} // Define
 
 names[3] = "den"
 names[4] = "den-shin"
 ```

첫 번째 라인과 같이 대괄호`[]` 안에 Array 의 크기를 넣어주고 대괄호 뒤에 타입을 지정해준다.  
그리고 값들을 중괄호`{}` 안에 넣어서 정의 해준다.  
그 후에 추가하는 것들은 그 아래 라인들과 같이 진행해주고, 만약  
`names[5] = "anything"` 을 해준다면 컴파일 에러가 난다.  

그런데, 크기 지정은 사실 실무에서 그렇게 사용하지 않는다,  
크기가 없는 Array 는 어떻게 지정할까 ?

### 2. Slice
 크기가 없는 Array 는 Slice 라 불리며 Array 와 정의한다.
 ```go 
 names := []string{"shin", "yeong", "hyeon"} // Define
 
 names = append(names, "den")
 ```
 선언부는 거의 똑같다, 크기 지정만 빼면.  
 그런데 추가하는 부분이 다른데, `append` 라는 함수를 이용해주어야 하며,  해당 함수는
 인자로 넘긴 첫번째 `Slice` -예제에서의 `names`- 를 변화시키는게 아니라, 값을 추가해서 `Return` 해준다.  
 이와 같은 형태는 개발을 하다보면 실질적으로 도움이 된다.  
 원래 값을 변화시키지 않고, 리턴하는 것이 디버깅에도 조금 더 효율적이니까,