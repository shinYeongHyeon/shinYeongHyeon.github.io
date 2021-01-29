---
layout: post
date: 2021-01-30
title:  "[Go 도전기] 9. Channel"
excerpt: ""   
categories: go
comments: true
---

Channel 은 데이터를 주고 받는 통로라고 볼 수 있다.  
make 를 통해 선언을 한다

```go
type job struct {
	title    string
	salary   int
}

func main() {
  c := make(chan job)
}
```

채널로 값을 전달해준고 받는다고 보면 된다.

```go
// 넘기기 (받기전용) chan<- {type}
func receive(channel chan<- job) {

  // 전달
  channel <- job{
    title: "test",
    salary: 1000000
  }
} 
```

```go
// goroutine
go receive(c)

// 데이터 받기
received <-c
```

for 문으로도 쓸 수 있다.  