---
layout: post
title: "javascript2"
description: "자바스크립트 문법을 공부해보자"
date: "2016-12-28 15:01"
tag: []
comments: true
share: true
---

### 자바스크립트(javascript) 문법

와! 어제에 이어서 자바스크립트(javascript) 공부 & 포스팅
아직 3일이 되진 않음.. 매일매일 공부한 내용을 포스팅 할 예정이다.

#### 3.1 문법

##### 3.1.1 대소문자 구분
일단 자바스크립트(javascript)는 대소문자를 구분합니다.
(변수, 함수이름, 연산자 모두 대소문자 구분함!)

* example
  * typeof = 키워드
  * typeOf = 변수명(유효한 함수 이름)

##### 3.1.2 식별자

* 식별자란? 변수나 함수, 프로퍼티, 함수 매개변수의 이름. 식별자는 다음 형식을 따른다.

1. 첫 번째 문자는 반드시 글자나 밑줄( _ ), 달러 기호( $ ) 중에 하나여야 한다.
2. 다른 문자에는 글자나 밑줄, 달러기호, 숫자를 자유롭게 사용할 수 있다.

글자에는 확장 아스키코드나 유니코드 문자를 쓸 수 있지만, 권장하지는 않는다.
자바스크립트(javascript)는 관습적으로 식별자를 `카멜 케이스`로 쓴다.

```javascript
firstSecond
myCar
doSomethingImportant
```

꼭! 카멜 케이스로 해야하는건 아니지만, 자바스크립트(javascript)의 내장 함수와 객체가 카멜 케이스로 표기 되어있다.
(그렇다면 이 형식을 따라야겠지??)

##### 3.1.3 주석

자바스크립트(javascript)의 한 줄 주석과 블록 주석 모두 C 언어 스타일로 표기한다.
한 줄 주석은 다음과 같이 슬래시( / )문자 두개로 나타낸다.  ` // 한 줄 주석 `

블록 주석은 ` /* */ ` 로 끝난다.

##### 3.1.4 스트릭트(strict) 모드

엥? 스트릭트 모드가 뭘까. 하고 봤는데 5 부터 새로 도입된 개념이라고 한다.
스트릭트 모드 = 기존과 다른 방식으로 자바스크립트를 파싱하고 실행하라고 지시하는 것. 안전하지 않은 동작에는 에러를 반환한다.

전체 스크립트에 스트릭트를 적용하려면 스크립트 맨 위에 `"use strict"` 를 적어주면 된다.

그런데 함수 단 하나만 스트릭트 모드로 실행하려면?

```javascript
function doSomething(){
  "use strict";
  //  함수 본문
}
```
근데 그래서 스트릭트가 뭐냐... 어떻게 달라지는지는 앞으로 책에서 얘기해준답니다.

##### 3.1.5 문장

자바스크립트(javascript)의 문자는 세미콜론(;)으로 끝난다.
물론 세미콜론이 없어도 유효하긴 하지만, 권장하는 방법이 절대 아니다.
왜냐고? 세미콜론으로 끝내지 않고 압축했을 때 문법 에러가 발생할 수 있기 때문이다.

```javascript
var sum = a + b;
var diff = a -b;
```

자바스크립트(javascript)는 여러 문장을 코드 블록으로 합칠 수 있다.
코드 블록은 { ... } 의 형태로 끝난다.

```javascript
if (test){
  test = false;
  alert(test);
}
```

다른 언어들처럼 제어문에서 실행하는 문장이 하나라면 코드 블록으로 쓰지 않아도 되지만, 항상 블록을 쓰는 것을 권장한다.
왜냐면 제어문에 코드 블록을 쓰면 의도를 더 명확하게 표현할 수 있고, 나중에 수정할 때 에러가 생길 가능성도 적기 때문이다.

#### 3.2 키워드와 예약어

우리가 모두 아는 그.. 그거 키워드 & 예약어

예약어
`abstract	arguments	boolean	break	byte
case	catch	char	class*	const
continue	debugger	default	delete	do
double	else	enum*	eval	export*
extends*	false	final	finally	float
for	function	goto	if	implements
import*	in	instanceof	int	interface
let	long	native	new	null
package	private	protected	public	return
short	static	super*	switch	synchronized
this	throw	throws	transient	true
try	typeof	var	void	volatile
while	with	yield `

일단 뭐 이런 것들은 알아서 검색하면 다 나온다. 그리고 기초 개념으로 아는거니까..!

#### 3.3 변수

생각해보면, 자바스크립트(javascript)는 데이터 타입에 대해 자유롭다.
var 하나로 모든 것을 퉁칠 수 있으니...
var 연산자 다음에 변수 이름을 씁니다. <- 이러면 변수 선언 완료!

`var message;
 var maessage1 = "hi";
`

여기서 보면 `message1`
의 변수 값을 "hi"로 정의했다.
그런데 이렇게 초기화 했다고 변수에 문자열 타입을 지정한건 아니다.
"단순히 값을 변수에 할당했을 뿐"이다.
변수에 저장된 값과 타입을 바꾸고 있다!

`var message = "hi";
 message = 100;   //  유효하지만 권장하지 않습니다.   
`
