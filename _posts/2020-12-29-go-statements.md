---
layout: post
date: 2020-12-29
title:  "[Go 도전기] 4. For, If, Switch Statement"
excerpt: "Go"
categories: go
---

## For
Go 에서는 다른 언어에서의 forEach, for in 같은 것은 존재 하지 않고 오직 for 만이 있다.
그리고 range 와 보통 사용하는데, go 만의 특색있는 for 문을 살펴보도록 하자
```go
func add(numbers ...int) int {

  // with range
  for index, number := range numbers {
    // execute
  }

  // ignore index
  for _, number := range numbers {
    // execute
  }

  // normal for
  for i := 0; i < len(numbers); i++ {
    // execute
  }

  ...생략
}
```

## If / Switch
너무 익숙한 If / Switch 문, 그런데 Go 에서는 If / Switch 문 안에서만 사용할 수 있는 변수를 만들어 낼 수 있다.
```go
func canIDrink(age int) bool {
  if (age < 18) {
    return false
  } else {
    return true
  }
}

func canIDrinkInKorea(age int) bool {
  if koreanAge := age + 2; koreanAge < 18 {
    return false
  } else {
    return true
  }
}

func canIDrinkSwitchVer(age int) bool {
  switch age {
    case 16:
      return false
    case 18:
      return true
  }

  return false
}

func canIDrinkSwitchVer2(age int) bool {
  switch {
    case age < 18:
      return false
    case age == 18:
      return true
  }
}

func canIDrinkInKoreaSwitchVer(age int) bool {
  switch koreanAge := age + 2; koreanAge {
    case 16:
      return false
    case 18:
      return true
  }
}
```


