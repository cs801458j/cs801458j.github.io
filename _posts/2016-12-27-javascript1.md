---
layout: post
title: "JavaScript1"
description: "자바스크립트(JavaScript)란 무엇인가 & HTML 속의 자바스크립트"
date: "2016-12-27 15:06"
tag: []
comments: true
share: true
---


#자바스크립트(JavaScript)란 무엇인가 & HTML 속의 자바스크립트  
---
###본 내용은 프론트엔드 개발자를 위한 자바스크립트에 기반합니다.
그 동안 실컷 미뤄두었던 자바스크립트 공부 시작(이라고 쓰고 딴 공부 하다가 뭐 설치 안되니까 갈아탐ㅋ)

##자바스크립트(JavaScript)의 역사 요약

자바스크립트(JavaScript)의 첫 등장 = 1995년(10여년 정도밖에 안된..!)
유효성 검사를 위한 언어(유효성 검사기로 그 역사가 시작됨)

역사 끝!

##HTML 속의 자바스크립트(JavaScript)

HTML 명세에 공식적으로 문서화된 녀석.

###2.1 <script>요소

HTML에 삽입할 때 <script></script> 이런 형태로 삽입된다.
<script>옵션의 종류는 6 가지가 있다는데 여기서는 생략.
이것 보다는 <script>의 두 가지 사용법에 대해 적겠다.

####1) 인라인 자바스크립트 코드
스크립트 요소 내부에 직접 작성한 코드를 의미한다.
해석은 위->아래 순서로 해석된다.

<script type="text/javascript">
function sayHi(){
  alert("Hi");
}
</script>


####2) 외부 파일 불러오기
자바스크립트를 외부 파일에서 불러오려면 src 속성을 사용하면 된다.
src속성에 파일의 URL을 지정해주면 간단하게 불러올 수 있다.

<script type="text/javascript" src="example.js"></script>

(이 파일 내부에는 스크립트 태그를 사용하면 안된다!)
인라인 코드처럼 코드를 해석하는 동안에는 페이지 처리가 멈춤.

자바스크립트의 확장자명 = "js"


앗, 그런데 인라인으로 <script></script> 태그도 쓰고 src로 외부 파일도 불러왔다면,
어떤 파일을 실행하게 될까??

정답은 "인라인 코드가 무시되고 외부 파일이 실행된다."

####강력한 기능, src
src속성에 다른 HTML 페이지가 존재하는 도메인 외부의 완전한 URL을 사용할 수 있다.

<script type="text/javascript" src="http://wwww.somewhere.com/afile.js">
</script>

위 처럼 외부 도메인의 js파일을 src에 지정해도 마치 원래 페이지의 파일인 것 처럼 불러와서 해석한다.

###2.2 <script> 태그의 위치
<head>태그 안에 쓰는 것이 일반적이다.
그냥 CSS파일이랑 JS파일 같이 외부 파일 참조를 한번에 관리하기 위해 이런 형식을 취한것이다.

하지만, 외부 파일을 이렇게 <head>에서 모두 불러오게 된다면 문제점이 발생한다.
자바스크립트를 전부 내려받고, 파싱하고, 해석을 끝낼 때까지 렌더링이 멈추게 된다는 점이다.
그런데 브라우저는 <body>태그를 만나면서 부터 렌더링을 시작한다...
(이렇게 되면 페이지 뜨는데 시간이 엄청나게 걸리겠지?? 그리고 넌 빈 화면을 보게 되겠지ㅋ)

이런 이유로 최신 웹 어플리케이션에서는 자바스크립트 코드를 모두 <body> 요소 안에 사용한다.
(페이지 콘텐츠 마지막에 써준다.</body>태그 바로 앞에..!)

<!DOCTYPE html>
<html>
  <head>
    <title> 몽몽뭉뭉's Web page </title>
  </head>
  <body>
    <!-- 페이지 콘텐츠 -->
    <script type="text/javascript" src="example1.js"></script>
  </body>
</html>


###2.3 defer & async

defer: 스크립트의 실행을 문서 렌더링 이후로 미룰 수 있다.

async: 해당 스크립트가 해석될 때 까지 다른 스크립트나 문서 렌더링을 차단하지 않아도 된다고 명시.
비동기 스크립트는 마크업 순서대로 실행되지 않는다.(DOM 조작 스크립트는 async(비동기적)사용을 자제하자.)

###2.4 <noscript>
<noscript>요소는 브라우저가 스크립트를 지원하지 않거나 비활성화 되었을 때 사용된다.
스크립트 사용할 수 있으면 표시되지 않아욧!
