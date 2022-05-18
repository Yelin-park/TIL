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

