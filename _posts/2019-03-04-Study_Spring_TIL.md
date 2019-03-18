# 190304 TIL

## Spring Project Basic
- AOP: Around Advice가 주로 사용됨
- pom.xml: 프로젝트 설정파일이 담김

## Maven 의존 설정
- 의존 설정과 플러그인 설정
```XML
    <dependency>
        <groupId>org.springframework</groupId>
        <artifactId>spring-context</artifactId>
        <version>4.1.0.RELEASE</version>
    </dependency>
```
- 메이븐: 모듈을 **아티팩트** 단위로 관리
- 위는 4.1.0 버전의 아티팩트에 대한 dependency를 추가한 것
- dependency를 추가한다 == 클래스패스에 spring-context 아티팩트를 추가한다는 것


## 기본 폴더 구조 
1. src\main\java: java 소스 코드
2. src\main\resource: 클래스패스에 위치할 자원 파일
