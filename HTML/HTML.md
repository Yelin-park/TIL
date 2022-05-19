# HTML

## 1. html 코딩 규칙(가이드)
<ol>
  <li> 문서 유형을 선언할 때는 대문자 사용 권장 (ex. !DOCTYPE html )</li>
  <li> 모든 요소(태그)는 소문자 사용 권장 </li>
  <li> 모든 요소가 종료태그가 필요한 것은 아니다. 
    <ul><li>br, hr, meta, img 닫기 태그 필요 X</li></ul>
  </li>
  <li>img src="" alt=""   =(등호) 주위에 공백 사용 X</li>
  <li>p태그의 닫기 태그 꼭 코딩 하자</li>
  <li>경로에 폴더명, 파일명은 *** 대소문자 구분을 한다. ***
      <ul><li>요청URL -> 웹서버(톰캣) : 톰캣에서 대소문자 구분을 해서 자원을 찾음</li></ul>
  </li>
  <li>파일 확장자
  <ul><li>.html    .htm</li></ul>
  <ul><li>외부 css 파일 : .css</li></ul>
  <ul><li> 외부 javascript 파일 : .js</li></ul>
  
  </li>
</ol>

- - -
#### [참조] 이모티콘 문자를 찍을 때는 가끔 &; 사용한다.
&#128516; = &#128516 &#128525; = &#128525 &#128151; = &#128151<br>
A - &#65; = &#65<br>
<br>
- - -
## 2. html Form(양식)
<h3> - 사용자 입력 처리를 하기 위해 사용하는 태그들..(사용자 입력 처리 -> 서버 전송 처리)</h3>
자바서버페이지 서버 처리 -> 응답<br>
&nbsp;&nbsp;&nbsp; > java server page == jsp<br>
<br>

<b> html - form태그 사용 코드 </b><br>
~~~ html
<form action="ex12_ok.jsp" method="get"> <!-- method 기본값은 get(방법 2가지있음) -->
	First Name : <br>
	<!-- id 속성 값이 아니라 name 속성값을 주어야 뒤에 내가 입력한 값이 나타난다.
		http://localhost/webPro/html/days05/ex12_ok.jsp?  (id 속성)
		http://localhost/webPro/html/days05/ex12_ok.jsp?fname=aa&lname=bb (name 속성)
	-->
	<input type="text" name="fname" autofocus="autofocus"><br> <!-- autofocus="autofocus" 속성 때문에 자동으로 깜빡깜빡 거림.. -->
	Last Name : <br>
	<input type="text" name="lname"><br>
	<br>
	<!-- submit == 전송하다 -->
	<input type="submit">
</form>
~~~
<br>

<b>&lt;결과&gt;</b><br>

![alt](https://github.com/Yelin-park/TIL/blob/main/HTML/img/ex12.JPG)

<br>

<b>jsp 코드</b>
~~~ jsp
<%@ page language="java" contentType="text/html; charset=UTF-8"
    pageEncoding="UTF-8"%>
<!DOCTYPE html>
<html>
<head>
<meta charset="UTF-8">
<title>Insert title here</title>
</head>
<body>
<h3>ex12_ok.jsp 파일</h3>
<!-- ex12.html에서 입력한 fname과 lname을 전송받았다.
fname/lname jsp 파일로 전송 -> DB 처리 또는 응답 -->
<%
	// ?fname=aa&lname=bb
	// java 코딩
  // request 요청하다, getParameter 파라미터를 가져오겠다, name이 fname에 해당하는 input 태그의 값을
	String fname = request.getParameter("fname"); 
	String lname = request.getParameter("lname");
%>

ex12.html 입력한 first name = <%= fname %><br>
ex12.html 입력한 last name = <%= lname %><br>
</body>
</html>
~~~

<br>

<b>&lt;결과&gt;<br></b>
![alt](https://github.com/Yelin-park/TIL/blob/main/HTML/img/jsp_test.JPG)
- - -
## 3. input 태그

### 1. 입력용 태그

### 2. value 속성이 있다.

### 3. type 속성<br>

<ul>
    <b><li>submit</li></b>
      - 서버에 제출하는 기능
    <b><li>text</li></b>
      - 문자를 입력받는 기능
    <b><li>button</li></b>
      - 버튼 기능(사용자 반응 처리 필요 - js)
    <b><li>reset</li></b>
      - 초기화를 하는 버튼(사용자 반응 처리 필요 - js)
    <b><li>radio</li></b>
      - 항목 중에 1개만 선택할 수 있는 기능<br>
      - label 태그가 항상 같이 사용되어짐<br>
      - 하나의 그룹으로 묶어주어야 하는데 이 기능을 하는 것은 name 속성이다.
    <b><li>checkbox</li></b>
      - 여러 개의 항목을 선택할 수 있는 기능<br>
      - 하나의 그룹을 묶이 위해서 똑같은 name 속성 값을 주어야 함<br>
    <b><li>file</li></b>
      - 첨부할 파일을 선택할 수 있는 기능<br>
      - 파일 선택할 뿐 서버에 파일이 업로드 되지는 않음. 파일을 업로드 할 수 있는 라이브러리를 설치해서 구현을 해야함
    <b><li>password</li></b>
      - 비밀번호를 입력받을 때 사용<br>
      - 입력시 **** 처럼 암호화되어져서 보여짐
    <b><li>color</li></b>
      - 색상을 선택할 수 있는 기능<br>
      - 브라우저 지원에 따라 색상 선택에 차이가 있다.(색상 선택 모양 등..)
    <b><li>date</li></b>
      - 날짜 선택 기능<br>
      - min, max 속성으로 기간을 제한할 수 있음(ex. 설문조사)
    <b><li>datetime-local</li></b>
      - 날짜 + 시간을 선택할 수 있는 기능
    <b><li>datetime</li></b>
      - 날짜 + 시간을 입력할 수 있는 기능
    <b><li>email</li></b>
      - 이메일을 입력할 수 있는 기능<br>
      - 이메일 형식에 맞게 자동으로 유효성 검사를 한다.
    <b><li>month</li></b>
      - 년도와 월만 선택할 수 있음
    <b><li>tel</li></b>
      - 연락처를 입력받는 기능<br>
      - pattern 속성으로 패턴을 지정하여 유효성 검사를 할 수 있음
    <b><li>number</li></b>
      - 숫자만 입력 가능한 기능<br>
      - min, max, step 속성으로 최소, 최대, 증가 값을 설정 가능
    <b><li>range</li></b>
      - 입력 범위를 지정할 수 있는 기능<br>
      - ex) 볼륨 설정시 사용
    <b><li>search</li></b>
      - 검색 필드
    <b><li>url</li></b>
      - url을 입력받는 기능<br>
      - url인지 유효성 검사를 함
    <b><li>week</li></b>
      - 년도와 주를 선택하는 기능
    <b><li>time</li></b>
      - 시간을 선택하는 기능
</ul>


