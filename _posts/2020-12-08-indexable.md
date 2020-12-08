---
layout: post
date: 2020-12-08
title:  "(TypeScript) Indexable"
excerpt: "Optional chaining"
categories: typescript
---
TypeScript 를 사용할 때, 들어오는 인자 중 Object 가 any 인 경우들이 있는데,

이것들이 interface 로 정의를 하고 싶을때가 있다.

아니면 정의하는 척이라도 ~~any는 보기 좀 그래..~~

그럴 때 사용할 수 있는 것이 Indexable 이다.

코드부터 보고 시작하자.

```typescript
interface Indexable {
  [key: string]: any;
}
```

~~결국은 any..~~
이렇다 하더라도 유용하게 쓰일 곳이 많다.

```typescript
const indexable: Indexable = {
  test1: 1,
  test2: 2,
  test3: 3,
};

Object.keys(indexable).forEach((k) => console.log(indexable[k])); // 1, 2, 3
```

해당 문법이 javascript 에서는 그냥 되는거 아니였나 ? 하지만, typescript 에서는 type 이 괄호 동적 접근을 하려고 하면 오류를 뱉어낸다.
그렇기 때문에 typescript 에서 동적으로 key 를 받아내려면 위와 같이 사용해야 한다.

