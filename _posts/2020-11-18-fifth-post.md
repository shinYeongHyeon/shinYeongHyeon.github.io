---
title:  "(ReactJS) 컴포넌트 생명주기"
excerpt: "parseInt(1) === +1"
last_modified_at: 2020-11-18
reference: https://ko.reactjs.org/docs/react-component.html
categories:
  - Blog
tags:
  - Blog
  - ReactJS
---

블로그까지 만들면서 제대로 공부를 시작하기로 했고, 그 일련의 작업들로 기초부터 다지고 있다.
그래서, ReactJS 를 공부를 시작했는데 그 시작에 앞서 ReactJS 에서 가장 많이 사용되는 거로 알고 있는 **Component**의 생명주기에 대해서 알아보자.

핵심은 **render()** 함수 인데, 이 함수가 *가상돔에 HTML 코드를 써준다* 라고 생각하면 된다. <- *ReactJS 의 개념? 이라고 이해했다.*

**render()** 를 기준으로 전/후로 나뉘고, 간략하게 표현하자면 `mount -> render -> mounted` 와 같다. *(unmount 는 제외하고.)*

이를 함수로 자세히보자면 마운트되면서 **constructor()** 가  **render()** 되기전에 실행되며, **render()** 되고 나면 **componentDidMount()**가 실행된다.
글자 그대로 **마운트 되고 나서~** 이다.

가장 기초적인 것들을 알아보았고, 이후에는 **Updating** 과 관련된 이야기를 풀어보면서, **State**에 대해서도 알아보도록 하자.
