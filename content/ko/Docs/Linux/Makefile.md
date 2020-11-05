---
title: "Makefile"
linkTitle: "Makefile"
type: docs
weight: 3
date: 2020-11-05T22:25:46+09:00
draft: flase
---

### **[정의]**

 linux상에서 반복적으로 발생하는 컴파일을 쉽게하기위해서 사용하는 make 프로그램의 설정 파일

Makefile을 통하여 library 및 컴파일 환경을 관리 가능

### **[기본구조]**

```bash
<Target> : <Depend> ?... [ [;] <Command> ]
		<TAB>  <Command>
```

Target(대상) : 빌드 대상 이름 (생성하고자 하는 목적물 / 명령에 의해 생성되는 결과파일 / 오브젝트 파일이나 실행파일)

Depend(의존관계) : Target을 만들 때 의존되는 파일 (Target을 만들기 위해서 필요한 요소 기술)

Command(명령) : 빌드 대상을 생성하는 명령 (일반 Shell 명령)

### **[변수]**

CC : 컴파일러

CFLAGS : 컴파일 옵션

OBJS : 중간산물 / object 파일 목록

TARGET : 빌드 대상(실행파일) 이름

LDFLAGS : 링커 옵션

LDLIBS : 링크 라이브러리

### **[자동 변수]**

$@ : 현재 target 이름

$^ :  현재 target이 의존하는 대상들의 전체목록

$? : 현재 target이 의존하는 대상들 중 변경된 것들의 목록

$< : 현재의 target보다 더 최근에 갱신된 파일 이름 ($?와 비슷함)

$% : 대상의 이름(현재 규칙 대상이 아카이브인 경우)

### **[문법]**

$(addprefix [prefix], [names]...) : prefix의 값은 각 개별 이름의 앞에 붙고, 그들 사이에 단일 스페이스로 채워 연결된 커다란 이름을 만듦

	ex) $(addprefix src/, foo bar) => 'src/foo src/bar'


$([MACRO_NAME] : [OLD] = [NEW]) : 매크로 치환, OLD 가 NEW로 치환

	ex) $(SRCS : .c = .o) -> SRCS목록의 .c를 .o로 치환


### **[참고]**

[http://doc.kldp.org/KoreanDoc/html/GNU-Make/GNU-Make-3.html](http://doc.kldp.org/KoreanDoc/html/GNU-Make/GNU-Make-3.html)

[http://korea.gnu.org/manual/4check/make-3.77/ko/make_8.html](http://korea.gnu.org/manual/4check/make-3.77/ko/make_8.html)

[https://bowbowbow.tistory.com/12](https://bowbowbow.tistory.com/12)

[https://doitnow-man.tistory.com/100](https://doitnow-man.tistory.com/100)
