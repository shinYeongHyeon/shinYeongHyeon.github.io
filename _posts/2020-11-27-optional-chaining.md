---
layout: post
date: 2020-11-27
title:  "(JavaScript) Optional chaining"
excerpt: "Optional chaining"
categories: javascript
---

한 Object 가 많은 Depth 를 가지고 있고, 특정한 데이터를 가져오려면 많은 Depth 를 지나서 가져온다고 가정하자.  
그렇다면, 개발자라면 보통 해당 Depth 들이 존재하는지 체크를 보통 한다, 그러나 이게 여간 귀찮은 일이 아니다.  
예를 들어  아래와 같은 Object 가 있다고 보자.
```javascript
const test = {
  depth1: {
    depth2: {
      depth3: "test"
    }
  }
};
```
test 의 depth1 의 depth2 의 depth3 에 접근하려면, 일단 test 있는지, 있다면 그 안에 depth1 이 있는지 .... 계속 해나가야 한다.  
근데 이것을 한번에 아름답게 해결해줄 수 있는 것이 *Optional Chaining* 이다.  
있는지 확인하고 싶은 것을 dot(.) 으로 연결하기 전에 *?* 만 붙여주면 끝.  
거두절미하고 아래 스크린 샷을 보면 이해 될 것이다.  
단 데이터가 없는 경우 *undefined* 로 리턴이 오니 참고할 것!  

~~아름다워~~

![](/assets/optionalchaning.png)

MDN : [https://developer.mozilla.org/ko/docs/Web/JavaScript/Reference/Operators/Optional_chaining](https://developer.mozilla.org/ko/docs/Web/JavaScript/Reference/Operators/Optional_chaining)
