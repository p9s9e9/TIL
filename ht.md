# Do it ! HTML+CSS+자바스크립트 웹 표준의 정석 - 고경희
## 1. HTML 태그
* `<header>` : 주로 사이트의 맨 위쪽을 담당.
* `<main>` : 사이트의 핵심 콘텐츠를 담당.
* `<footer>` : 웹 문서 맨아래 쪽을 담당. ex) 저작권정보, 제작정보, 연락처 
* `<aside>` : 본문 내용 외에 사이드 바를 만들 때 사용.
* `<article>` : 내용이 각기 독립적이고 홀로 설 수 있는 내용을 담을 때 사용. ex) 뉴스 기사, 블로그 글
* `<section>` : 내용이 서로 관계 있는 문서를 분리할 때 사용. ex) 문서의 각기 다른 주제들
* `<div>` : 내용이 관계가 없을 때 사용. 오직 묶는 역할을 함.
* `<nav>` : 현재 또는 다른 페이지로 이동하는 링크를 하나로 묶을 때 사용. ex) 메뉴, 목차
* `<a>` : 다른 페이지로 연결할 때 사용하는 태그.

## 2. 텍스트 관련 태그
* `<h1>` : 제목을 나타내는 태그. h1~h6 까지 사용
* `<p>` : 텍스트 단락을 만들 때 사용.
* `<br>` : 줄바꿈을 할 때 사용.
* `<blockquote>` : 책의 내용이나 말을 인용할 때 사용
* `<strong>` : 중요한 내용의 텍스트를 굵게할 때 사용.
* `<b>` : 단순히 글자를 굵게 표시할 때 사용.
* `<em>` : 특별히 강조하고 싶은 내용의 텍스트를 기울일 때 사용.
* `<i>` : 단순히 텍스트를 기울일 때 사용.
* `<sub>` : 아래 첨자를 표시할 때 사용.
* `<sup>` : 위 첨자를 표시할 때 사용.
* `<s>` : 취소선을 표시할때 사용.
* `<u>` : 밑줄을 그을때 사용.

## 3. 목록 관련 태그
* `<ol>` : 순서 있는 목록을 만들 때 사용. 
  * 속성 : type = ( "1" | "a" | "A" ) , start = ( "시작숫자" | "시작문자" )
* `<ul>` : 순서 없는 목록을 만들 때 사용.
* `<li>` : 목록의 리스트를 만들 때 사용.
* `<dl>` : 이름과 설명 형태로 된 목록을 만들 때 사용.
* `<dt>` : 이름 부분을 지정할 때 사용.
* `<dd>` : 설명 부분을 지정할 때 사용.

## 4. 표 관련 태그
### 4-1 표, 행 ,셀 생성
* `<tabel>` : 표를 만들 때 사용.
* `<caption>` : 표의 제목을 만들 때 사용.
* `<tr>` : 행을 만들 때 사용.
* `<td>` : 행 안에 있는 셀을 만들 때 사용.
* `<th>` : 행의 제목 셀을 만들 때 사용.
#### 4-1-1 속성
* rowspan : 행을 합칠 때 사용.
* colspan : 열을 합칠 때 사용.
```html
ex)   `<td rowspan ="합칠 셀의 개수"> 셀의 내용 </td>`
      `<td colspan ="합칠 셀의 개수"> 셀의 내용 </td>`
```

### 4-2 표의 구조 지정
* `<thead>` : 표의 구조를 지정할 때 헤더 부분들을 묶을 때 사용.
* `<tbody>` : 표의 구조를 지정할 때 본문 부분들을 묶을 때 사용.
* `<tfoot>` : 표의 구조를 지정할 때 푸터 컨텐츠들을 묶을 때 사용.

### 4-3 열을 묶을 때
* `<col>` : 열을 1개만 지정할때 사용.
          <colgroup>안에 열의 개수만큼 <col> 태그를 넣어야함.
* `<colgroup>` : `<col>` 태그를 2개 이상 묶을 때 사용, `<caption>` 태그 다음에 사용해야 함.
```html               
ex)  
<colgroup>
  <col>             // 표의 1열
  <col>            //  표의 2열
</colgroup>
```

## 5. 이미지 관련 태그
### 5-1. 이미지 삽입
* `<img>` : 이미지를 삽입할 때 사용.
     `ex) <img src="파일경로" alt = "대체용 텍스트" width = "너비" height = "높이">`
<br>
## 6. 오디오, 비디오 태그
### 6-1. 다양한 멀티미디어 파일 삽입
* ` <object>` : 오디오, 비디오, 이미지, pdf 등 다양한 멀티미디어 파일을 삽입할 때 사용.
    `ex) <object width="너비" height="높이" data="파일경로"></object>`
* `<embed>` : 다양한 멀티미디어 파일을 삽입할 수 있고 대부분의 브라우저에서 사용 가능.
    `ex) <embed src="파일경로" width="너비" height="높이">`

### 6-2. 오디오, 비디오 파일 삽입
* `<autio>`, `<video>` : 오디오와 비디오 파일을 삽입할 때 사용.
```html    
ex) 
<audio src="파일경로"></audio>
<video src="파일경로"></audio>
```

## 7. 폼 관련 태그
### 7-1. 폼 생성 태그
`<form> 여러 폼 요소 </form>`

#### 7-1-1. 속성
* name : JS로 폼을 제어할 때 사용할 폼의 이름을 지정.
* action: 폼의 내용을 처리해줄 서버 프로그램을 지정.
* target : action 속성에서 지정한 파일을 다른 창에서 열도록 함.
* method: 사용자가 입력한 내용을 서버 쪽 프로그램으로 어떻게 넘길지 지정함.
* autocomplete : 폼의 자동 완성 기능

### 7-2. 폼 요소를 그룹으로 묶을 때
* `<fieldset>` : 하나의 폼안에 여러 구역을 나누어 표시할 때 사용.
* `<legend>` : `<fieldset>` 태그의 제목을 붙일 때 사용.
```html
ex)
<fieldset>
<legend> 그룹 이름 </legend>
</fieldset>
```

### 7-3. 폼 요소의 레이블을 붙일 때
<label>  - 폼 요소에 레이블(이름)을 붙이고 2가지 방법으로 활용가능.
   1. <input> - 입력받을 폼을 형성하고 속성으로 타입을 지정할 수 있다.
	ex)<label> 아이디 <input type="text"> </label>

   2. label 태그의 for 속성  - 폼 요소의 id 속성값을 label 태그의 for 속성에게 알려줌.
	ex)<label for="id명"> 아이디 <input id="id명"> </label>
	ex)<label for="user-id"> 아이디 </label>
	   <input type="text" id="user-id">
      -  1번째 방법은 레이블 다음 바로 폼을 형성해 입력을 받아야하지만
         2번째 방법은 아이디 값을 지정해 서로 연결해주므로
         폼이 페이지의 어느 곳에 있더라도 값이 지정된다.

## 8. input 태그의 type 속성
### 8-1. 속성
* type = "text" | "password" | "url" | "email" | "tel" |
         "checkbox" | "radio" | "submit" | "reset" | "button" 등등
  `ex) <input type="radio" value="넘겨줄 값" name="이름">`

* 라디오 버튼에서 하나의 버튼만 선택하게 하려면 모든 라디오 버튼의 name 값을 같게 해야함. 

## 9. input 태그의 주요 속성
  - autofocus required : 자동으로 입력 커서를 갖다 놓는다.
  - placeholder : 힌트를 표시  
  - readonly : 읽기 전용으로 만듬
  - required : 필수 입력으로 지정한다.
  - checked : 체크박스, 라디오 버튼에서 기본으로 선택해 놓고 싶은 항목을 지정.

## 10. 폼에서 사용하는 여러가지 태그

- <textarea> : 여러 줄을 입력하는 텍스트영역을 만듬.
- <select>, <option> : 드롭다운 목록을 만들어 준다.
     - slecet 의 속성 size : 화면에 표시할 드롭다운 항목의 개수 지정.
     - option 의 속성 seleceted : 기본적으로 선택해서 보여줄 항목을 지정.
                                value : 서버로 넘겨줄 값을 지정.
     ex) <label for="prod1"> 상품선택</label>
          <select id="prod1">
               <option value="gfit_3"> 선물 3kg </option>
               <option value="gift_5"> 선물 5kg </option>
          </select>

- <datalist>, <option> : 데이터 목록을 만들어 준다.

- <button> : input 태그의 필드와 다른 폼을 전송하거나 리셋하는 버튼을 삽입.
     ex) <button type="sumbit || reset || button"> 내용 </button>
     submit : 폼을 서버로 전송 (input type="submit" 과 같은 기능)
       reset : 폼에 입력한내용 초기화 (input type="reset" 과 같은 기능)
       button : 버튼 형태만 만들 뿐 자체 기능은 추가해야함 (input type="button")
