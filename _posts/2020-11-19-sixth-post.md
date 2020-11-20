---
title:  "(ReactJS) 컴포넌트 생명주기 2"
excerpt: "React JS 컴포넌트 생명주기 2"
last_modified_at: 2020-11-19
reference: https://ko.reactjs.org/docs/react-component.html
categories:
  - Blog
tags:
  - Blog
  - ReactJS
---

이전 포스팅에서 ReactJS 의 Class Component 를 살펴보면서 가장 기초적인 부분들을 확인해 보았다.  
이번에는 **Updating**과 **State** 에 대해 알아보도록 하자.  

ReactJS 에서는 **State** 라는 것을 가지고 있는데, 이 아이는 유동적인 데이터를 사용할 때 써먹는다.  
기본적으로 
```javascript
this.state = {};
```
위와 같이 사용을 하는데, 이는 private 처럼 사용해야한다, 직접 조작해서는 안되는 뜻!  
변경이 필요할 때는 마치 다른 클래스의 setter 를 사용하듯 **setState** 메소드를 활용해주어야 한다.  
그 이유는 **Updating**과 관련이 있는데, state 가 변경될때마다 ReactJS는 렌더링을 다시 하는데,  
**setState** 메소드를 사용하지 않는다면 이 부분을 감지 못하므로 re-렌더링이 이뤄지지 않는다.

그래서 위 설명에서 말했 듯, **Updating**은 **State** 혹은 **props**가 변화할때 이뤄진다.  
이때 기타 메소드들이 호출 된 후 ([자세한 것은 이리로](https://ko.reactjs.org/docs/react-component.html))  
**render()** 과 호출되고 **componentDidUpdate()** 가 호출된다.  
**componentDidUpdate()**는 유용하게 사용 가능한 **props** 들을 제공해주는데,  
**prevProps, prevState, snapshot** 을 제공해준다.  
전 상태를 비교할 수 있다는 것!
개인적으로는 이것을 제공해주는게 너무 감사하다..
