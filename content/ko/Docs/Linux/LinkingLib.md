---
title: "외부 라이브러리를 사용하여 gcc로 컴파일하는 방법"
linkTitle: "외부 라이브러리 컴파일하기"
weight: 4
type: docs
date: 2020-11-06
description: >-

---

```bash
gcc -L[디렉토리명] -l[파일명] *.c
```
`-L` 
	
&nbsp;&nbsp;&nbsp;&nbsp;외부 라이브러리를 사용한다는 의미. 라이브러리의 위치를 정해주는 옵션.

`-l`

&nbsp;&nbsp;&nbsp;&nbsp;링크할 라이브러리를 명시하는 옵션. 정적 라이브러리를 링크시키는데 사용되며 대상 라이브러리 파일 이름앞에서 lib과 .a를 제외하고 인식. (POSIX시스템에서 라이브러리 파일명 앞에 lib을 붙이기로한 일종의 약속 떄문)

&nbsp;&nbsp;&nbsp;&nbsp; ex) -lftprintf > libftprintf.a파일을 사용.
