# css

## 1. CSS

ㄱ. Cascading Style Sheets 약어<br>
ㄴ. html 요소가 표시되는 방법을 설명<br>
ㄷ. html 문서의 스타일 지정하는데 사용<br>
ㄹ. 많은 작업(유지, 보수, 지정) 절약<br>
ㅁ. 여러 웹 페이지의 스타일을 일괄적으로 관리할 수 있다(장점)<br>
ㅂ. 외부 스타일 시트(.css) 사용 가능<br>
ㅅ. 다양한 장치(기기) 및 화면 크기에 대한 출력의 디자인, 레이아웃 및 변경 스타일 정의 처리<br>
ㅇ. html 요소가 화면, 종이 또는 기타 미디어에 표시되는 방식 지정<br>
<br>

## 2. CSS 구문(형식)

스타일 적용할 대상 세미콜론(;)<br>
selector { 속성:속성값; 속성:속성값; 속성:속성값;...}<br>
&nbsp; &nbsp; &nbsp; ㄴ 선택자<br>
<br>

## 3. CSS 적용하는 방법<br>

<b>ㄱ. 내부(internal) CSS 적용 방법 - 해당 문서(웹페이지)만 스타일 적용 - head 태그 안에 style 태그</b><br>

```html
<head>
  <style>
    selector {
      속성: 속성값;
      ...;
    }
  </style>
</head>
```

<br>

<b>ㄴ. 인라인(inline) CSS 적용 방법 - 해당 요소에만 스타일 적용</b><br>
&nbsp; &nbsp; &nbsp; &nbsp; 시작 태그 안에 style 속성으로 스타일 적용<br>

```html
<p style="스타일적용"></p>
<p style="border: 1px solid gray;"></p>
```

<br>

<b>ㄷ. 외부(External) CSS 적용 방법 - 여러 문서(웹페이지)에 스타일 적용</b><br>
&nbsp; &nbsp; &nbsp; &nbsp; 외부 스타일 적용할 파일 => style.css<br>
<br>
&nbsp; &nbsp; 외부 css 파일 모양)

```css
@charset "UTF-8";

body {
  background-color: lightblue;
}
```

<br>
&nbsp; &nbsp; 선언 형식)

```html
<link rel="stylesheet" href="css파일명.css" />
```

<br>

## 4. CSS 선택자(selector)

1. 태그명
2. #아이디명
3. .클래스명
4. 그룹화 => 태그명, .아이디명..<br>
   &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; :

## 5. css 적용 우선순위(정리중..)

- 맨 위에 있는 css 먼저 적용한 후 마지막에 설정한 값으로 적용이 되어진다.
- internal CSS 적용 방법보다 inline CSS 적용 방법이 우선순위가 높다.
- 태그명.클래스명 > 클래스명 > 태그명
- 태그명#아이디명 > #아이디명 > 태그명
