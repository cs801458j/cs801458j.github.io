# JavaScript

- 본 내용은 프론트엔드 개발자를 위한 자바스크립트 프로그래밍에 기반합니다. 

## 3.4 js Data Type
- ECMAScript 기본 데이터 타입에 어떤 것이 있을까?  
- ECMAScript에는 **원시 데이터 타입** 5가지가 있다..!
    - Undefined
    - Null
    - Boolean
    - 숫자
    - 문자열 
    - Object(얘는 별개..! 이름-값 쌍으로 구성된 순서 없는 목록) 
    
### 3.4.1 typeof & undefined

#### typeof 
- typeof: data type을 나타냄
- typeof null: 의외로 **object** 타입을 반환합니다. 빈 객체를 참조하는 특별한 값이기 때문!
#### undefined
- undefined: var를 사용하여 변수를 정의했지만, 초기화 되지 않았을 때 undefined가 할당됨
#### null
- 빈 객체를 가리키는 포인터 
- 변수가 정의할 때 해당 변수가 객체를 가리키게 할 생각이라면 해당 변수에는 다른 값을 쓰지 말고 null로 초기화 하길 권장함. 
#### boolean 
- true, false 라는 두가지 리터럴 값만 갖는다. 
#### 부동소수점 숫자 
- 부동소수점 숫자를 저장할 때 정수를 저장할 때에 비해 메모리를 두 배로 소모함. 
#### NaN
- 숫자를 반환할 것으로 의도한 조작이 실패했을 때 의도한 조작이 실패했을 때 반환하는 값


### 3.4.2 객체 타입
- ECMAScript에서 객체는 데이터와 기능의 집합!
```
    var o = new Object(); // 괄호를 쓰는 것을 권장 합니다!
```
- Object: 모든 객체의 원형. Object 타입의 프로퍼티와 메소드를 전부 상속함. 
- 객체 안에 속성값으로 객체가 들어갈 수 있음.
```js
    var person = {
      body: {
        height: 173,
        weight: 66
      }
    };
    person.body.height; // 173
```
- {} 를 이용하여 만든 객체를 **literal**이라고 부름.

### 3.4.3 반복문 
#### for - in 반복문 
- for-in 문은 객체의 프로퍼티를 나용하는데 사용
- 비열거형 속성을 가진 객체는 반복하지 않음 (ex. Array, Object.prototype, String.prototype)
```js
    for (variable in object) statement
    
    // 실제 사용 예시 
    for (var propName in window) {
        document.write(propName);
    }    
```

```js
    var o = {a:1, b:2, c:3};
    
    function show_props(obj, objName) {
      var result = "";
        
      for (var prop in obj) {
        result += objName + "." + prop + " = " + obj[prop] + "\n";
      }
        
      return result;
    }
    
    alert(show_props(o, "o")); /* alerts: o.a = 1 o.b = 2 o.c = 3 */
```

## 4 변수의 스코프와 메모리

### 4.1 원시값과 참조값

- 원시값: 단순한 데이터. 변수에 저장된 실제 값을 조작!
- 참조값: 여러 값으로 구성되는 객체. 해당 객체에 해당하는 참조를 조작! (js 는 메모리에 직접 접근하는 것을 허용하지 않음)

#### 자동적인 Global 변수 
```js
    myFunction();
    
    // code here can use carName as a global variable
    document.getElementById("demo").innerHTML = "I can display " + carName;
    
    function myFunction() {
        carName = "Volvo";
    }
```
- HTML에서 전역 범위는 윈도우 객체. 모든 전역 변수는 윈도우 객체에 속함.
#### 변수의 생명주기 
- 자바스크립트의 변수의 생명주기는 변수가 선언되는 때 시작된다. 
- 지역변수는 함수가 끝나면 소멸된다. 
- web browser에서 wjsdurqustnsms 윈도우 브라우저를 끄면 삭제되지만, 같은 창에 로드된 새 페이지에서 계속 사용할 수 있다. 



## 5 함수 
### 함수 표현식 
```js
    addOne(1);

    function addOne(x) {
      var y = x + 1;
      return y;
    }   //  result >> 2
    
    var addOne = function(x) {
      var y = x + 1;
      return y;
    };  //  result >> syntax error!
```
- hoisting: 끌어올리기  
- 함수는 자신이 위치한 코드에 상관 없이 함수 선언문 형태로 정의한 함수의 유효 범위는 전체 코드의 맨 처음부터 시작!
- 함수선언이 함수 실행부분보다 뒤에 있더라도 JS 엔진이 함수 선언을 끌어올린다..!
- 함수의 hoisting은 함수를 끌어올리지만, 변수의 값은 끌어올리지 않는다.
### this 키워드 
- 함수의 정의에서 this는 **owner**를 참조한다. 
```js
    // Create an object:
    var person = {
        firstName: "John",
        lastName : "Doe",
        id       : 5566,
        fullName : function() {
           return this.firstName + " " + this.lastName;
        }
    };
```


## 6 Event
- 이벤트?? 이벤트 아주 중요함!
- HTML 이벤트는 HTML 요소에 발생하는 "것"
- JavaScript가 HTML 페이지에서 사용될 때 JavaScript는 이러한 이벤트에 "반응"할 수 있음!
### HTML Event
- HTML 이벤트는 브라우저가 수행하는 작업이거나 사용자가 수행하는 작업
    - HTML 웹 페이지로드가 완료
    - HTML 입력 필드가 변경
    - HTML 버튼을 클릭
    





## 설명 해야할 리스트 
- Prototype
- 비동기 
-