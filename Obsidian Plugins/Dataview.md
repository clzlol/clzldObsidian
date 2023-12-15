---
due: 2023-12-16
kind: obsidian plugin func
status: To Do
urgent: 
tags:
  - note
---
***

Dataview를 쓰면 Obsidian을 Database처럼 사용할 수 있게 된다. 노트에 속성을 추가하면 SQL과 유사한 Dataview Query Language(DQL)을 사용해 데이터를 [[Query]] 할 수 있다.
```
TABLE
	kind as "kind",
	status as "status",
	urgent as "urgent"
FROM "Key Concepts"
```

해당 코드의 맨 위에 있는 ` ``` ` 뒤에 `dataview`를 붙여주면 다음과 같은 결과를 얻을 수 있다.

```dataview
TABLE
	kind as "kind",
	status as "status",
	urgent as "urgent"
FROM "Key Concepts"
```
