# CSS
> Do it ! HTML+CSS+자바스크립트 웹 표준의 정석 - 고경희
## 1. CSS 스타일과 스타일 시트
### 1-1. 스타일 형식
```html
ex)
선택자 { 속성: 속성값;          //   p { text-align: center;
         속성: 속성값; }        //        color : blue; }
```
<hr>

### 1-2. 스타일 시트
* 스타일 규칙을 한눈에 확인하고 수정하기 쉽도록 묶어 놓은 것.
* 스타일 시트
  * 브라우저 기본스타일
  * 사용자 스타일
   * 인라인 스타일
   * 내부 스타일 시트
   * 외부 스타일 시트
<hr>

* 브라우저 기본 스타일 : 웹 문서에서 CSS를 사용하지 않더라도 브라우저 기본 스타일을 사용함.
* 인라인 스타일 : 스타일을 적용할 대상에 직접 표시하는 방법.
```html
ex) <p style = "color:blue;"> </p>
```
* 내부 스타일 시트 : 웹 문서안에 사용할 스타일을 같은 문서안에 정리 한 것.
```html
ex) <head> 태그안에 <style> </style> 태그에 작성함.
```
* 외부 스타일 시트 : 웹 문서안에 사용할 스타일을 별도의 .css파일로 저장하고 가져와서 사용함.
```html
ex) <link rel="stylesheet" href = "파일경로">
```
### 1-3. 기본 선택자
* 전체 선택자 : 웹 브라우저의 기본 스타일을 초기화할 때 자주 사용.
```html
ex) * {속성: 값;}        // <style> * {margin:0; padding:0;} </style>
```
* 타입 선택자 : 특정 태그를 사용한 모든 요소에 스타일을 적용.
```html
ex) 태그명 {속성: 값;}     // <style> p { font-style: italic; }  </style>
```
* 클래스 선택자 : 클래스를 적용한 부분만 스타일을 적용.
```html
ex) 정의: .클래스명 { 속성: 값;}           // <style> .accent { padding: 5px; }  </style>
    사용: <선택자 class = " 클래스명 ">    // <h1 class = "accent"> 제목 </h1>
```
* id 선택자 : 특정 부분에 스타일을 적용하지만 문서에서 한 번만 적용할 수 있음.
```html
ex) 정의: #id명 { 속성: 값;}           // <style> #container { padding: 5px; }  </style>
    사용: <선택자 id = " id명 ">       // <div id = "container" > 내용 </div>
```
* 그룹 선택자 : 여러 선택자에서 같은 스타일 규칙을 사용할 경우 , 로 구분해 한번만 정의.
```html
ex) <style> h1, p { text-aling: center }; </style>
```
<hr>

### 1-4. 캐스케이딩 스타일 시트 (CSS)
* CSS에서 C는 Cascading의 줄임말이며, 스타일 시트에서 우선순위가 위에서 아래로 적용 된다는 의미.
* 스타일끼리 충돌하지 않도록 막아주는 개념이며 2가지 방법이 있다.
  * 스타일 우선순위
    * 사용자 스타일 -> 제작자 스타일 -> 브라우저 기본 스타일
    * 우선순위가 같을경우
      * !important -> 인라인 스타일 -> id스타일 -> 클래스스타일 -> 타입스타일
  * 스타일 상속
    * 태그의 자식요소에 별도로 스타일을 지정하지 않으면, 부모 요소의 스타일이 상속됨.
<hr>

## 2. 텍스트를 표현하는 스타일
### 2-1. 글꼴 관련 스타일
* font-family 속성 : 글꼴을 지정함.
```html
ex) body { font-family: "맑은 고딕", 돋움, 굴림 } 
```
* font-size 속성 : 글자 크기를 지정함.
```html
ex) body { font-size: 15px;}     // px, em, rem 단위를 사용함. 
```
* font-style 속성 : 이탤릭체로 글자를 표시함.
```html
ex) body { font-style: normal | italic | oblique } 
```
* font-weight 속성 : 글자 굵기를 지정함.
```html
ex) body { font-weight: 숫자값 | normal | bold | bolder | lighter } 
```
### 2-2 웹 폰트
* 사용자 시스템에 없는 글꼴을 사용할 수 있다.
```html
ex) 
@font-face {
  font-family: '글꼴파일'
  src: url('파일경로')
}
```
<hr>

### 2-3 텍스트 관련 스타일
* color 속성 : 글자색을 지정
* text-align : 텍스트 정렬
* text-decoration : 줄을 표시하거나 없애줌
* line-height : 줄 간격을 조절, 세로정렬할 때 유용함.
* text-shadow : 텍스트에 그림자 효과를 넣음. 
* text-transform : 텍스트의 대소문자 변환.
* letter-spacing : 글자 간격을 조절
* word-spacing : 글자 간격을 조절
<hr>

### 2-4 목록 관련 스타일
* list-style-type : 불릿 모양과 번호 스타일을 지정
* list-style-image : 원하는 이미지를 사용.
* list-style-position : 리스트를 들여쓴다.
* list-style : 목록 속성을 한꺼번에 표시. 
  * 위에 3가지를 한번에 표시할 수 있다.
```html
ex)
ol{
  list-style: none; lower-alpha; inside;
}
```
<hr>

### 2-5 표 관련 스타일
* caption-side : 표 제목의 위치를 정해줌. (top,bottom)
* border : 표에 테두리를 그려줌.
* border-spacing : 셀과 셀사이의 여백
* border-collapse : 표와 셀 테두리를 합쳐줌.

## 3. 레이아웃을 구성하는 CSS 박스 모델
### 3-1 블록 레벨 요소, 인라인 레벨 요소
* 블록 레벨 요소 : 태그를 사용해 요소를 삽입했을 때 혼자 한 줄을 차지하는 것.
  * ex) `<h1>`, `<div>`, `<p>`
* 인라인 레벨 요소 : 태그를 사용했을 때 한 줄을 차지하지 않는 것.
  * ex) `<span>`, `<img>`, `<strong>`
<hr>

### 3-2 박스 모델의 기본 구성
* 블록 레벨 요소는 모두 박스 모델 요소이다.
* 박스 모델 : 콘텐츠, border, padding, margin 등으로 구성 됨.
<hr>

### 3-3 콘텐츠 영역의 크기 지정하기
* width 속성 : 너비를 지정
* height 속성 : 높이를 지정
<hr>

### 3-4 박스 모델의 크기를 계산하기
* box-sizing 속성
```html
ex) 
.box1 { box-sizing: boder-box; }      // 테두리까지 포함해 너빗값을 지정.
.box2 { box-sizing: content-box; }    // 콘텐츠 영역만 너빗값을 지정.
```
<hr>

### 3-5 박스 모델의 그림자 효과주기
* box-shadow 속성
```html
ex) .box1 { box-shadow: <수평거리>, <수직거리>, <흐림정도>, <번짐정도>, <색상>; }
```
<hr>

### 3-6 테두리 스타일 지정하기
* border-style 속성: 테두리 스타일을 지정 (solid, dotted, dashed)
* border-width 속성: 테두리 두께
* border-color 속성: 테두리 색상
* border : 테두리 스타일들을 묶어서 한번에 표기할 수 있음. 
```html
#box1 { border: 3px; solid; blue; }
```
* border-radius 속성: 테두리를 둥글게 만듬.
<hr>

### 3-7 여백 조절하기
* margin 속성: 요소 주변의 여백을 의미하며, 요소와 요소 사이의 간격을 조절 할 수 있다.
  * margin 속성과 auto값을 이용해 웹 문서를 가운데 정렬할 수 있다.
  ```html
  #container{
    width: 600px;            // 너비값을 반드시 지정해야함.
    margin: 20px auto;       // 위아래 마진은 20, 좌우 마진은 자동.
  }
  .....
  <div id = "container">
    <h1> 제목 </h1>
  </div>
  ....
  ```
* padding 속성: 콘텐츠 영역과 테두리 사이의 여백을 의미. 
<hr>

### 3-8 레이아웃 배치 방법
* display 속성 : 배치 방법을 결정함
  * 블록레벨 요소와 인라인레벨 요소를 바꿔 사용할 수 있다.
  * 메뉴항목을 가로로 배치할 때 많이 사용.
  * 이미지를 표 형태로 배치할 수 있음.
  * display : block             // 인라인 레벨 요소를 블록 레벨 요소로
  * display : inline            // 블록 레벨 요소를 인라인 레벨 요소로
  * display : inline-block      // 인라인,블록라인 속성 모두 가지며 마진과 패딩 지정가능.
  * display : none    
* flaot 속성 : 왼쪽이나 오른쪽으로 배치.
  * 웹 요소를 문서 위에 떠 있게 만듬.
  * 플로팅이란 요소를 왼쪽, 오른쪽에 떠 있게 만드는 레이아웃 기법.
  * `<p>` 태그는 블록레벨 요소라 이미지와 나란히 한줄에 배치 할 수 없음.
  * float 속성을 이용하면 이미지를 표시하고 그 주변에 텍스트를 둘러싸도록 할 수 있음.
  * float : left | right | none(기본값)
* clear 속성 : float 속성을 해제함.
  * float 속성을 이용하면 그 다음에 넣는 요소도 float 속성을 가지게 됨.
  * 더이상 float 속성을 사용하지 않으려면 clear 속성을 사용해야 함.
  * clear : left | right | both 
<hr>

### 3-9 웹 요소의 위치 지정하기
* 웹 요소의 위치 지정하는 속성
  * left, right, top, bottom 속성
* position 속성의 속성 값
  * static, relative, absolute, fixed
  * position : absolute 값을 사용하려면 부모요소에 relative 값을 지정해야 함.
<hr>

## 4. 이미지와 그라데이션 효과로 배경 꾸미기
### 4-1. 배경색과 배경 범위 지정 
