# Javascript
> Do it ! HTML+CSS+자바스크립트 웹 표준의 정석 - 고경희
## 1. 자바스크립트 
### 1-1. 자바스크립트 작성하기.
* `<script>` 태그안에 작성.
```html
<body>
  <h1 id="heading"> </h1>
  <p> </p>
  <script>
    var heading = document.querySelector('#heading');
    heading.onclick = function() {
      heading.style.color = "red";
    }
  </script>
</body>
```
* 외부 스크립트 파일로 연결하기.
```html
<body>
  <h1 id="heading"> </h1>
  <p> </p>
  <script src= "js/change-clor.js"> </script>       // 외부 스크립트 파일 연결
</body>
```
<hr>

### 1-2. 기본 입출력 방법.
* 간단한 입출력
  * `alert(메시지)` : 알림 창 만들기.
  * `confirm(메시지)` : 확인 창 만들기.
  * `prompt(메시지, 지정할 기본값)` : 입력받기.
    * ex) ` var name = prompt("이름을 입력하세요."); `
  * `document.write(메시지 | 변수)` : 출력하기.
  * `console.log(메시지 | 변수)` : 콘솔창에 출력하기.
    * ex) ` console.log(name); `
  * `parseInt(값)` : 입력받은 값을 정수로 변환 ( 실수,문자열이든 )
   * ex) `var num = parseInt ( prompt ("입장객은 몇 명인가요?") );`
<hr>

## 2. 자바스크립트 기본 문법
### 2-1. 변수 선언하기
* `var 변수명;`
* `var birthyear = 1994;`
### 2-2. 자료형
```html
* 기본 유형
  * 숫자형 : var birthYear = 2000; 
  * 문자형 : var birthYear = "2000";       // " , ' 로 묶음.
  * 논리형 : var isEmpty = true;           // true, false 2가지 값.
* 복합 유형
  * 배열 : var seasons = ['봄', '여름', '가을', '겨울'];       // 하나의 변수에 여러 개 값 저장.
  * 객체 : var date = new Date();          // 함수와 속성을 함께 포함.    
* 특수 유형
  * undefined : 변수를 선언한 상태에서 값이 할당되지 않은 상태.
  * null : 변수에 할당된 값이 유효하지 않다는 의미.    
```
### 2-3. 연산자
* 비교 연산자
  * == : 피연산자가 서로 같으면 true
  * === : 피연산자도 같고 자료형도 같으면 true
  * != : 피연산자가 서로 같지 않으면 true
  * !== 피연산자가 서로 같지 않거나 자료형이 같지않으면 true
* 문자열의 비교
  * 맨 앞의 문자부터 하나씩 아스키 값을 비교해서 결정함.
<hr>

### 2-4. 조건문
* if문, if~else문
```html
if(조건){
  조건 결과 값이 true일 때 실행할 명령
}
```
```html
if(조건){
  조건 결과 값이 ture일 때 실행할 명령
}
else{
  조건 결과 값이 false일 때 실행할 명령
}
```
* 조건 연산자
  * `(조건) ? (true일 때) : (false일 때)`
```html
ex)
(number % 3 === 0) ? alert("3의 배수") : alert("3의 배수가 아님.");
```
* switch문
```html
switch(조건)
{
  case 값1: 명령1
    break;
  case 값2: 명령2
    break;
  case 값3: 명령3
    break;
}
```
  * switch문의 조건은 case 문의 값과 일치해야 명령을 실행함.
<hr>

### 2-5. 반복문
* for문
```html
for(초기값; 조건; 증가식){
  
}
```
* while문, do~while문
  * while문은 조건이 true인 동안 명령을 반복
  * do~while문은 일단 무조건 한번 명령을 실행한뒤 조건을 체크.
```html
while(조건){
    
}
do{
  
}while(조건)
```
* break문, continue문
  * break문을 실행할 경우 해당 반복문, 조건문을 빠져 나옴.
  * continue문을 실행할 경우 해당 문을 한차례 건너뛰게 함.
<hr>

## 3. 함수와 이벤트.
### 3-1. 함수.
* 함수 선언
  * function 함수명() { ... }
  * ex) ` function addNumber(){ var num1 = 1; } `
* 함수 호출
  * 함수명() 또는 함수명(변수)
  * ex) ` addNumber(); `
* 함수 선언과 실행 순서
  * 자바스크립트 소스를 해석할 때 함수 선언을 가장 먼저 함. 
  * 함수 호출을 먼저하고 뒤에 선언을 해도 문제가 없음.

<hr>

### 3-2. var과 호이스팅
* var 변수의 특징
  * 스코프: 변수를 선언하고 사용할 때 변수가 적용되는 범위
  * 지역변수(로컬변수) : 함수 안에서만 사용할 수 있는 변수.
    * 함수 안에서 var 예약어를 이용해 변수를 선언.
  * 전역변수(글로벌변수) : 스크립트 소스 전체에서 사용할 수 있는 변수.
    * 함수 밖에서 선언해야함.
    * 함수 안에서는 var 예약어를 사용하지 않아야함.
  * var 변수는 재선언과 재할당을 할 수 있음.
* 호이스팅
  * 상황에 따라 변수의 선언과 할당을 분리해서 선언 부분을 스코프의 가장 위쪽으로 끌어올리는 것.
```html
ex)
<script>
  var x = 10;

  function displayNumber() {
    console.log(" x = " + x);
    console.log(" y = " + y);        // y가 아직 정의되지 않았는데 y를 사용.
    var y = 20;
  }
  displayNumber();
  x = 50;                // x 변수 재할당
  var x = 100;           // x 변수 재선언
</script>

결과 값: x = 10
         y = undefined
   해석: 변수 호이스팅으로 스코프 최상단에서 var y; 라는 변수선언을 진행.
         선언만하고 할당은 하지 않았으므로 undefined 라는 결과 값 출력.
```
<hr>

### 3-3. let, const
* var 예약어를 사용하면 재선언, 재할당등 실수가 많이 일어나 오류가 자주 발생함.
* ES6 이후 부터는 let,const를 사용하는 것을 권장.
* var, let, const
  * 스코프의 범위 
    * var : 함수 영역의 스코프.
    * let, const : 블록( {}로 묶은부분 ) 영역의 스코프.
  * 전역 변수를 선언하고 싶다면 let 예약어를 쓰지 않고 변수 이름과 값만 할당하면 됨.
* let 
  * 재할당은 가능하지만 재선언은 불가.
  * 호이스팅이 없음.
* const
  * 재할당, 재선언 불가.
* 자바스크립트 변수 가이드.
  * 전역 변수는 최소한으로 사용. 오류 발생 확률이 높아짐.
  * var 변수는 함수의 시작 부분에서 선언. 호이스팅 때문에 오류 발생 확률 높아짐.
  * for문에서 카운터 변수로 var 예약어를 사용하지 않음.
  * ES6를 사용한다면 var보다 let을 사용.
<hr>

### 3-4. 재사용 가능한 함수 만들기.
* 매개변수, 인수, return
  * 매개변수: 함수를 선언할 때 외부에서 값을 받아 줄 변수.
  * 인수: 함수를 호출할 때 값 부분.
  * return: 함수의 반환 값.
* 매개변수 기본값 지정하기.
```html
ex)
function multiple(a, b = 5){            // 매개변수 b의 변수값을 넘겨받지 못했을때 기본값을 지정.
  return a*b;
}
```
<hr>

### 3-5. 함수 표현식.
* 익명함수 : 함수 이름을 지정하지 않고 사용.
  * ` function(a,b) { ... } `     
  * 익명함수는 함수 자체가 식이므로 변수에 할당해서 사용.
  * 다른 함수의 매개변수로 사용할 수도 있음.
```html
ex)
var sum = function(a,b){               // 익명함수를 선언하고 sum에 할당.
  return a+b;
}
documnet.write( sum(10,20) );          // 익명함수 실행.
```


* 즉시 실행 함수 : 함수를 호출하지 않고 바로 실행.
  * ` ( function() { ... }() ); `
  * ` ( function(매개변수) { ... }(인수) ); `
```html
ex)
( function(a,b){
    sum = a + b;
}(10, 20) );
document.write(sum);
```


* 화살표 함수 
  * 익명 함수에서만 사용할 수 있음.
  * 변수에 할당해서 사용.
  * (매개변수) => { 함수 내용}
```html
ex)
const hi = () => { return "hello" };                // 매개변수가 없음.  
let num = user => { documnet.write(user); }         // 매개변수가 1개일 때.
let sum = (a,b) => a+b;                             // 매개변수가 2개 이상일 때.
```
<hr>

### 3-6. 이벤트, 이벤트처리기
 > 이벤트: 사용자가 행하는 어떤 동작. 클릭이나 선택 등등. <br>    
 > 이벤트처리기: 이벤트가 발생했을 때 실행하는 함수.
* 마우스 이벤트

| 종류 | 설명 | 
|---|:---:|
| click | 사용자가 HTML 요소를 클릭할 때 이벤트 발생. |
| dbclick | 사용자가 HTML 요소를 더블클릭할 때 이벤트 발생. |
| mousedown | 사용자가 요소 위에서 마우스 버튼을 눌렀을 때 이벤트 발생. |
| mousemove | 사용자가 요소 위에서 마우스 포인터를 움직일 때 이벤트 발생. |
| mouseover | 마우스 포인터가 요소위로 옮겨질 때 이벤트 발생. |
| mouseout | 마우스 포인터가 요소를 벗어날 때 이벤트 발생. |
| mouseup | 사용자가 요소 위에 놓인 마우스 버튼에서 손을 뗄 때 이벤트 발생. |

* 키보드 이벤트

| 종류 | 설명 | 
|---|:---:|
| keydown | 사용자가 키를 누르는 동안 이벤트 발생 |
| keypress | 사용자가 키를 눌렀을 때 이벤트 발생 |
| keyup | 사용자가 키에서 손을 뗄 때 이벤트 발생 |

* 폼 이벤트

| 종류 | 설명 | 
|---|:---:|
| blur | 폼 요소에 포커스를 잃었을 때 이벤트 발생. |
| change | 목록이나 체크 상태 등이 변경되면 이벤트 발생. `<input>, <select>, <textarea>`태그에서 사용. |
| focus | 폼 요소에 포커스가 놓였을 때 이벤트 발생. ` <lable>, <select>, <textarea>, <button>` 태그에서 사용. |
| reset | 폼이 리셋되었을 때 이벤트 발생. |
| submit | submit 버튼을 클릭했을 때 이벤트 발생. |

* 문서로딩 이벤트

| 종류 | 설명 | 
|---|:---:|
| abort | 문서가 완전히 로딩되기 전에 불러오기를 멈췄을 때 이벤트 발생. |
| error | 문서가 정확히 로딩되지 않았을 때 이벤트 발생. |
| load | 문서 로딩이 끝나면 이벤트 발생. |
| resize | 문서 화면 크기가 바뀌었을 때 이벤트 발생. |
| scroll | 문서 화면이 스크롤되었을 때 이벤트 발생. |
| unload | 문서에서 벗어날 때 이벤트 발생. |
<hr>

### 3-7. 이벤트처리기 - HTML태그
* 이벤트 처리기(이벤트 핸들러)
  * `<태그 on이벤트명 = "함수명"> `
  * `<a onclick = "alert('클릭')"> `
```html
ex)
<body>
  <a href = "#" onclick = "changeColor('green')"> green </a>
  <a href = "#" onclick = "changeColor('red')"> red </a>
  
  <div id="result"> </div>

  <script>
    function changeColor(color){
      var result = document.querySelector('#result');
      result.style.backgroundColor = color;             
    }
  </script>
</body>
```
<hr>

### 3-7. 이벤트 처리기 - DOM
* HTML 태그에서 onclick 같은 이벤트를 넣지않고 자바스크립트에서 이벤트를 넣음.
* DOM을 사용하면 자바스크립트가 HTML의 요소를 가져와서 이벤트 처리기를 연결.
* 태그와 자바스크립트 소스를 분리해서 보기 좋게 사용할 수 있음.
* ` 웹요소.onclick = 함수; `
* `querySelecot()` : 웹 요소를 가져옴. 괄호안에는 클래스, id, 선택자를 넣을 수 있음. 
```html
ex)
<div id = "item">
  <button id = "open"> 상세 설명 보기 </button>
  <div id = "desc">
    <h1> 내용 </h1>
    <p> 내용 </p>
    <button id = "close"> 살세 설명 닫기 </button>
  </div>
</div>

<script>
  document.querySelector('#open').onclick = function ()            //querySelecot를 통해 id=open을 찾고, onclick시 즉시 실행 함수
  {
    document.querySelector('#desc').style.display = "block";       // id=desc의 display를 블록레벨로 만듬.
    document.querySelector('#open').style.display = "none";        // id=open의 display를 none으로 만듬. 
  }
  document.querySelector('#close').onclick = function ()
  {
    document.querySelector('#desc').style.display = "none";
    document.querySelector('#open').style.display = "block";
  }
</script>
```
<hr>

## 4. 객체 (Object)
### 4-1. 객체 알아보기
* 자바스크립트에서 객체란?
  * 프로그램에서 인식할 수 있는 모든 대상을 가리킴.
  * 데이터를 저장하고 처리하는 기본 단위.
* 자바스크립트에서 사용하는 객체
  * 문서 객체 모델(DOM)
  * 브라우저 관련 객체
  * 내장 객체
* 객체 - 인스턴스 만들기
  * 객체를 사용하려면 참조 형태로 사용 해야함.
  * 즉, 객체 자체가 아니라 인스턴스 형태로 만들어서 사용.
  * 객체가 틀이라면 그 틀을 기반으로 만들어 낸 것이 인스턴스.
  * 방법: ` new 객체명 `
  * 예시: ` let now = new Date()           // Date객체의 인스턴스를 만들고 변수에 저장 `
* 객체 - 프로퍼티, 메서드
  * 객체에는 프로퍼티와 메서드가 있다.
  * 프로퍼티 : 객체의 특징, 속성을 가르킴
  * 메서드 : 객체의 동작을 표현함.
  * 프로퍼티와 메서드 표시: 인스턴스 명 뒤에 마침표(.) 를 붙이고 프로퍼티나 메서드 이름을 작성.
<hr>

### 4-2. 내장 객체
* Array 객체 (배열)
  * Array 객체로 배열 만드는 방법.
```html
ex)
let numbers = new Array();                             // 초기값이 없고 배열의 크기를 지정하지 않음.
let numbers = new Array(4);                            // 초기값이 없고 배열의 크기를 지정함.
let numbers = ["one", "two", "three", "four"];         // 초기값이 있고 배열 선언.
let numbers = Array("one", "two", "three", "four");    // 초기값이 있고 배열 선언.
```
  * Array 객체의 length 프로퍼티.
    * 배열의 크기가 저장되어 있음.
  * Array 객체의 메서드

| 종류 | 설명 | 
|---|:---:|
| concat() | 서로 다른 배열 2개를 합쳐 새로운 배열을 만듬. |
| join() | 배열 요소를 하나의 문자열로 만듬.  |
| push() | 배열의 맨 끝에 새로운 요소를 추가. |
| unshift() | 배열의 시작 부분에 새로운 요소를 추가. |
| pop() | 배열의 마지막 요소를 꺼내 그 값을 결과로 반환. |
| shift() | 배열의 첫번째 요소를 꺼내 그 값을 결과로 반환. |
| splice() | 배열의 요소를 추가하거나 삭제함. |
| slice() | 배열에서 특정한 부분만 잘라냄. |
<hr>

* Math 객체 (수학)
  * Math 객체는 new로 인스턴스를 만들지 않고 바로 사용함.
  * ` Math.프로퍼티명, Math.메서드명 `
  * Math 객체의 메서드

| 종류 | 설명 | 
|---|:---:|
| abs() | 절대값을 반환. |
| floor() | 매개변수의 소수점 이하 부분을 버림. |
| max() | 매개변수의 최댓값을 반환. |
| min() | 매개변수의 최솟값을 반환. |
| random() | 0과 1사이의 무작위 수를 반환. |
| round() | 매개변수의 소수점 이하 부분을 반올림. |
| sqrt() | 매개변수에 대한 제곱근을 반환. |
 <hr>

 ### 4-3 브라우저 관련 객체
 * window 객체
  * window 객체의 프로퍼티

| 종류 | 설명 | 
|---|:---:|
| document | 브라우저 창에 표시된 웹 문서에 접근 할 수 있음. |
| innerHeight | 내용 영역의 높이를 나타냄. |
| innerWidth | 내용 영역의 너비를 나타냄. |
| location | window 객체의 위치 또는 현재 URL을 나타냄. |
| name | 브라우저 창의 이름을 가져오거나 수정. |

  * window 객체의 메서드

| 종류 | 설명 | 
|---|:---:|
| alert() | 알림 창을 표시. |
| close() | 현재 창을 닫음. |
| open() | 새 창을 열음. |
| confirm() | 확인,취소 버튼이 있는 확인 창을 띄움. |
| moveBy() | 현재 창을 지정한 크기만큼 이동. |
| moveTo() | 현재 창을 지정한 좌표로 이동. |
| prompt() | 프롬프트 창에 입력한 텍스트를 반환. |
| scroll() | 지정한 위치까지 스크롤. |
| stop() | 로딩을 중지. |
<hr>

* screen 객체
  * screen 객체의 프로퍼티

| 종류 | 설명 | 
|---|:---:|
| availHeight | UI 영역을 제외한 영역의 높이를 나타냄. |
| availWidth | UI 영역을 제외한 영역의 너비를 나타냄. |
| height | UI 영역을 포함한 영역의 높이를 나타냄.
| width | UI 영역을 포함한 영역의 너비를 나타냄. |
| orientation | 화면의 현재 방향을 나타냄. |

  * screen 객체의 메서드

| 종류 | 설명 | 
|---|:---:|
| lockOrientation() | 화면 방향을 잠금. |
| unlockOrientation() | 화면 방향 잠금을 해제. |

<hr>

## 5. 문서 객체 모델 (DOM)
### 5-1 문서 객체 모델이란
* 자바스크립트로 웹 문서에 접근, 제어할 수 있도록 객체를 사용해서 체계적으로 정리하는 방법.
* DOM은 텍스트, 이미지, 표 등 모든 요소를 각각 개체로 정의함.
* DOM 트리
  * 문서 객체 모델의 구조를 나타냄.
  * 요소노드(부모) : 모든 HTML 태그
    * 텍스트 노드(자식) : HTML 태그에서 사용하는 텍스트 내용
    * 속성 노드(자식) : HTML 태그에 있는 속성
<hr>

### 5-2 DOM 요소에 접근하고 속성 가져오기.
* DOM '요소'노드에 접근하기.
  * ` document.getElementByid("id명") ` : id 선택자로 접근.
  * ` document.getElementByClassName("class명") ` : class 선택자로 접근.
  * ` document.getElementByTagName("tag명") ` : tag로 접근.
* DOM '요소,자식,텍스트' 노드에 접근하기.
  * ` document.Selector("선택자") ` : 요소, 속성, 텍스트에 접근. 반환값 하나.
  * ` document.SelectorAll("선택자") ` : 요소, 속성, 텍스트에 접근. 반환값 여러 개.
* `getElementBy~, Selector~` 의 차이점.
  * `getElementBy~`
    * ( ) 값을 넣을때 "클래스이름", "id값" 을 넣는다.
    * 반환 값이 요소만 저장 된다.
  * `querySelector~`
    * ( ) 값을 넣을때 " .클래스이름", "#id값", 요소, 속성을 넣는다. 
    * 반환 값은 노드, 노드리스트가 저장 된다.
* 웹 요소의 내용을 추가, 수정하는 프로퍼티.
  * ` innerText `
  * ` document.getElenebtByClassName("text").innerText = "수정하기"; `   // text라는 클래스를 가진 요소의 내용을 추가, 수정.
* 속성 가져오기, 수정하기
  * ` getAttribute("속성값") `: 요소의 속성에 접근.
  * ` setAttribute("속성", "값") `: 원하는 속성값으로 변경.
<hr>

### 5-3 DOM 이벤트 처리하기.
* DOM 요소에 함수를 직접 연결하기.
```html
<img src = "#" id = "cup">

<script>
  let cup = documnet.querySelector("#cup");       // id=cup 요소를 변수 cup에 저장.
  cup.onclick = function(){                       // 변수 cup에 함수를 직접 연결.
    ...
  }
</script>
```

* 함수 이름을 사용해 연결하기.
```html
<img src = "#" id = "cup">

<script>
  let cup = document.querySelector("cup");
  cup.onclick = changePic;

  funtion changePic(){
    ...
  }
</script>
```

* addEventListener() 메서드 사용하기.
  * ` 요소.addEventListener("이벤트종류", 함수, 캡처여부); `
```html
<img src = "#" id = "cup">

<script>
  let cup = document.querySelector("#cup");         // id가 cup인 요소를 변수 cup에 저장.
  cup.addEventListener("click", changePic);        // cup 클릭시 changePic 함수 실행.

  function changPic(){
    ...
  } 
  
  혹은
  
  cup.addEventListener("click", function(){        // 따로 함수를 구현하지않고 메서드 안에서 함수를 구현.
    ...
  });

</script>
```

* CSS 속성 접근하기.
  * ` document.요소.style.속성명 `
  * ` document.getElementById("desk").style.color = "blue"; `
<hr>

### 5-4 DOM에서 노드 추가, 삭제하기.
* 새로운 노드를 만들거나 추가하려면 노드리스트를 이용해야 함.
* 요소노드와 속성노드, 텍스트노드를 만들경우 부모 자식간 연결을 해줘야 함.
* 노드를 삭제하려면 부모노드에서 자식노드를 삭제해야함.

* 요소 노드 만들기.
  * ` createElement() ` 
  * ` var newP = document.createElement( "p" );     // 새로운 <p> 요소를 만듬. `
    
* 텍스트 노드 만들기.
  * ` createTextNode() `
  * ` var newText = document.createTextNode( "텍스트" ); `
    
* 속성 노드 만들기.
  * `createAttribute() `
  * value 로 값 지정.
  * ` var newSrc = documnet.createAttribute( "속성명" );       // 새로운 src 속성 `
  * ` newSrc.value = "images/dom.jpg";                         // src 속성 값 부여 `

* 요소 노드, 자식 노드 연결하기.
  * ` appendChild() `
  * 부모노드.appendChild(자식노드)
  * ` newP.appendChild(newText); `

* 요소 노드, 속성 노드 연결하기.
  * ` setAttributeNode() `
  * 요소노드.setAttribute(속성노드)
  * ` var newImg = document.createElement("img");           // img 요소 생성 `
  * ` newImg = setAttribute(newSrc);                        // img 요소에 newSrc 속성 연결. `

* 노드 삭제하기.
  * 노드를 삭제하려면 부모노드로 먼저 접근해야한다.
  * 노드.parentNode : 노드의 부모노드를 반환.
  * 부모노드.removeChild(자식노드)
  * ` li.parentNode.removeChild(li)             // li.parentNode는  li의 부모노드를 의미. `

  <hr>
