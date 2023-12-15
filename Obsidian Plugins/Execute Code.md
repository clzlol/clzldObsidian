---
due: 2023-12-31
kind: obsidian plugin func
status: To Do
urgent: true
tags:
  - note
---
***

Obsidian도 [[MarkDown]]을 지원하는데, 코드 블록을 작성했을 때 실행까지 시켜주는 플러그인이 있다.

## 일반적인 코드 블록

보통은 이렇게 코드만 강조되어 표시되기만 한다.
```python
print("hello")
```

```javascript
console.log(1+1)
```

## Execute Code를 사용하는 코드 블록

Execute Code를 사용하려면, ` ```run-(언어) ` 이런 식으로 사용하는 언어 앞에 `run-`을 붙여주면 된다. 

python
```run-python

print("hello")

```

javascript
```run-javascript

console.log(1+1)
```

## Execute Code 설정

대신 이를 제대로 활용하려면 Execute Code 플러그인의 설정에서 각 프로그래밍 언어의 경로를 추가해야 한다.
![[execute code.png]]

***

python은 별다른 설정 없이도 실행이 되는 거 같은데, javascript는 제대로 출력이 나오지 않는 거 같다. 말고도 다른 언어도 문제가 있을 거 같으니 나중에 고쳐봐야겠다.