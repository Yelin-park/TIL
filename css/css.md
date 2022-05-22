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

<br>

## 5. CSS 적용 우선순위(정리중..)

- 맨 위에 있는 css 먼저 적용한 후 마지막에 설정한 값으로 적용이 되어진다.
- internal CSS 적용 방법보다 inline CSS 적용 방법이 우선순위가 높다.
- 태그명.클래스명 > 클래스명 > 태그명
- 태그명#아이디명 > #아이디명 > 태그명

<br>

## 6. CSS 색상 지정

1. 표준색상명(140개)으로 나타냄
2. RGB(0~255, 0~255, 0~255) - red/green/blue 색의 3원소 값을 주어서 나타냄
3. #16진수값 - HEX == 16진수
4. RGBA(alpha 투명도 0.0~1.0)
5. HSL - hue(색조) / saturation(채도) / lightness(밝기, 명도)
   <ul>
   <li>색조 : 0~360 / 채도 : 0~100% / 밝기 : 0(검정)~100%(흰색)</li>
   <li> 0(빨강) / 120(녹색) / 240(파랑)</li>
   </ul>
6. HSLA(alpha 투명도 0.0~1.0)

<br>

<b>[코드 예시]</b>

```html
<style>
  p {
    /* 1. 표준 색상명(140개) */
    background-color: tomato;

    /* 2. RGB(0~255, 0~255, 0~255) */
    /* color: white; */
    /* color : rbb(255, 255, 255) */
    color: rgb(255, 255, 255);

    /* 3. #16진수값 */
    /* color: #ffffff; */
    color: #fff;

    /* 4. RGBA */
    color: rgb(255, 255, 255, 0.5);

    /* 5. HSL - hue(색조) / saturation(채도) / lightness(밝기, 명도) */
    background-color: hsl(0, 100%, 50%);
  }
</style>
```

```html
<body>
  /* inline css 적용 방식 */
  <p style="background-color: hsla(9, 100%, 64%, 0.5)">
    Lorem ipsum dolor sit amet.
  </p>
</body>
```

<br>

## 7. CSS 배경과 배경색, 배경이미지

1. 배경 배경색 : background-color
2. 배경 이미지 : background-image
3. 배경 반복 : background-repeat
4. 배경 위치 : background-position
5. 배경 약식 속성 : background(color image repeat attachment position 순서대로..)

<b>[배경색 코드 예시]</b>

```html
<style>
  /* color를 주는 속성값과 거의 동일함 */

  h3 {
    background-color: yellow;
  }

  /* 블럭모드 = width 100% 다 잡힘 */
  div {
    border: 1px solid gray;
    width: 200px;
    padding: 10px;

    /* 투명도 0(투명) ~ 1(불투명) */
    background-color: rgba(0, 255, 0, 0.1);
  }

  div.first {
    /* opacity : 투명도만 주는 속성 / opacity 속성으로 투명도를 설정하면 자식(하위) 요소도 동일한 투명도를 상속(적용)한다 */
    opacity: 0.5;
  }
</style>

<body>
  <div class="bg_test">
    <div class="first">Lorem ipsum dolor.</div>
    <div class="second">Perspiciatis quas quidem!</div>
    <div class="third">Eius odit quod.</div>
    <!-- inline 방식이 더 우선이라 적용되어짐 -->
    <div style="background-color: rgba(0,255,0,0.3);">
      Inventore amet expedita!
    </div>
    <div>Neque quaerat illo.</div>
  </div>
</body>
```

<b>[적용 결과]</b>

![alt](https://github.com/Yelin-park/TIL/blob/main/css/img/7.JPG)

<br>

<b>[배경 이미지, 반복, 위치 코드 예시]</b>

```html
<style>
  body {
    /* background-color: orange; */
    /* 이미지는 전체 요소(body)를 덮도록 자동으로 가로/세로 반복하고 있다. */
    /* 배경색 : 주황 => 배경색은 적용되어져 있고, 그 위에 이미지를 덮고 있다. */
    /* (주의) 텍스트의 색상에 방해되지 않도록 배경 이미지를 사용한다. */
    background-image: url("https://item.kakaocdn.net/do/c620e34ce78db64b44ff1e422a35e2787154249a3890514a43687a85e6b6cc82");

    /* background-repeat : 배경 반복을 주는 속성 */ /* ex02의 3번 */
    /* background-repeat: repeat;*/ /* 안주면 기본값 */
    /* background-repeat: repeat-x; */ /* y축을 반복 */
    /* background-repeat: repeat-y; */ /* x축을 반복 */
    background-repeat: no-repeat; /* 반복 안하겠다. */

    /* 스크롤을 내리면 배경도 같이 올라가짐 */ /* ex02의 4번 */
    /* background-attachment: scroll; */ /* 기본값 */
    background-attachment: fixed; /* 스크롤 내려도 배경 고정됨 */

    /* 우측 상단에 위치하게 됨 */
    /* %와 px을 줘도 됨 */
    background-position: right top;
  }

  #top {
    /* css 테두리 약식 */
    /* border: 1px solid gray; */
    border-width: 1px;
    border-style: solid;
    border-color: gray;

    width: 25px;
    height: 25px;

    /* ***** 위치를 나타내는 속성 left, top, right, bottom **** */
    position: fixed; /* 고정 시킬거다 */
    right: 5px; /* 우측으로 5px 위치에 */
    bottom: 5px; /* 아래쪽 5px 위치에 */
  }

  #top:hover {
    background-color: black;
    color: yellow;
    font-weight: bold;
    cursor: pointer; /* 커서 모양을 손가락 모양으로.. */
  }
</style>

<body>
  <div id="top" onclick="top_click();">Top</div>
  <h3>css 배경 이미지</h3>
  Lorem ipsum dolor sit amet, consectetur adipisicing elit. Vitae aperiam
  ratione aspernatur iste maxime rerum illum sint optio labore iusto ut et.
  Ratione laboriosam enim eos nostrum minima rerum asperiores.
  <p>.</p>
  <p>.</p>
  <p>.</p>
  <p>.</p>
  <p>.</p>

  <script>
    function top_click() {
      // alert("이벤트 발생 확인");
      // 아래 2가지 코딩은 동일한 코딩(맨위로 올리겠다.)
      // 브라우저 마다 적용되는 방식이 달라서 중복 코딩을 한다.
      document.body.scrollTop = 0;
      document.documentElement.scrollTop = 0; // 크롬에서 적용되는 함수
    }
  </script>
</body>
```

<b>[적용 결과]</b>
![alt](https://github.com/Yelin-park/TIL/blob/main/css/img/days02_ex02_03_1.JPG)

<br>

## 8. CSS 테두리(border)

- 기본 선언 형식 : border: 1px solid gray;
- 테두리는 상하좌우 원하는 곳에만 테두리를 설정할 수 있다. top/right/bottom/left
- border-style은 필수이다. style을 지정하지 않으면 width, color 속성이 적용되지 않는다.
  <br>

<b>[테두리 코드 예시]</b>

```html
<p style="border-top: 1px solid;">위쪽 테두리</p>
<p style="border-right: 1px solid;">오른쪽 테두리</p>
<p style="border-bottom: 1px solid;">아래쪽 테두리</p>
<p style="border-left: 1px solid;">왼쪽 테두리</p>
<p style="border-style: solid; border-width: 15px;">실선 테두리</p>
<p style="border-style: dotted; border-width: thick;">점선 테두리</p>
<p style="border-style: dashed;">점선 테두리</p>
<p style="border-style: double;">이중 테두리</p>
<p style="border-style: groove;">3D 홈 테두리</p>
<p style="border-style: ridge;">3D 융기된 테두리</p>
<p style="border-style: inset;">3D 삽입 테두리</p>
<p style="border-style: outset;">3D 아웃셋 테두리</p>
<p style="border-style: hidden;">숨겨진 테두리</p>
<p style="border-style: none;">테두리 정의 X</p>
```

<b>[적용 결과]</b>

![alt](https://github.com/Yelin-park/TIL/blob/main/css/img/8.%ED%85%8C%EB%91%90%EB%A6%AC.JPG)

<br>

## 9. CSS margin(여백)

1. border의 외부 요소 주위의 공간(바깥 여백)
2. margin 속성을 사용해서 처리를 함
3. margin-top, margin-right, margin-bottom, margin-left
4. margin 속성 = auto 설정
<ul>
  <li> > 브라우저 여백 자동 처리</li>
	<li> ex) margin: 0 auto => 가운데 정렬</li>
</ul>

5. px, in, pt, cm 등등 + %, inherited 여백을 부모 상속
6. margin 속성은 음수허용 (ex. -100px;)

```
!주의! margin 축소
  1번째 div.bottom 여백 : 75px;
  2번째 div.top 여백 : 25px;

  1번째 div [여백 25px+75px 가 아니라 큰 px로 설정되어져서 75px이 되어짐] 2번째 div
```

![alt](https://github.com/Yelin-park/TIL/blob/main/css/img/days02_ex04.JPG)

<br>

<b>[margin test 코드 예시]</b>

```html
<style>
  /* border가 옆으로 바짝 붙게함 */
  /*
  body{
		margin: 0;
		padding: 0;
	}
	*/
  .margin_test {
    border: 1px solid black;

    /*
		margin-top: 25px;
		margin-right: 50px;
		margin-bottom: 75px;
		margin-left: 100px;
		*/

    /* 약식 : top right bottom left     시계방향*/
    /*margin: 25px 50px 75px 100px; */
    /* margin: 25px; */ /* 4개 모두 25px 주겠다.(동일한 설정) */

    /* margin: 25px 100px; */ /* 상하, 좌우 설정*/

    margin: 25px 50px 100px; /* top, 좌우, bottom 설정 */
  }
</style>

<body>
  <div class="margin_test">
    Lorem ipsum dolor sit amet, consectetur adipisicing elit. Harum quas
    doloremque cumque nisi voluptatum modi pariatur ab sapiente impedit ea iusto
    maxime adipisci deleniti soluta aliquam voluptatibus quisquam amet voluptas.
  </div>
  <div class="margin_test">
    Dolorem aperiam fugit maxime aliquid nesciunt iste distinctio est culpa
    vitae commodi consequuntur quam laudantium error sit sint earum dignissimos
    adipisci nam quae quos rerum! Deserunt soluta corporis facilis atque.
  </div>
  <div class="margin_test">
    Ipsum quos molestias pariatur mollitia quis explicabo similique repellendus
    ipsam a dignissimos id impedit debitis fugit ratione tenetur optio nisi
    soluta nostrum non incidunt quo fugiat natus deserunt placeat rem!
  </div>
</body>
```

<b>[적용 결과]</b>

![alt](https://github.com/Yelin-park/TIL/blob/main/css/img/9%EB%B2%88%20%EC%97%AC%EB%B0%B1.JPG)

## 10. inherit(상속) 이란?

- 말그대로 부모 태그의 설정 값을 상속 받겠다 라는 의미이다.

<br>

## 11. CSS padding(안쪽 여백) & width 속성

1. 기준은 border이며, border + [ 간격 = 패딩 ] + content => border와 content 사이의 간격을 padding(패딩)이라 한다.

2. 위의 안쪽 여백 : padding-top<br>
   오른쪽 안쪽 여백 : padding-right<br>
   아래쪽 안쪽 여백 : padding-bottom<br>
   왼쪽 안쪽 여백 : padding-left<br>
3. 단위 : px, %, pt, cm 등등 inherit 속성 사용 가능
4. padding은 음수 허용 X
5. padding 속성을 설정하면 width 속성에 영향을 준다. (width가 커진다.)
6. border 속성도 width 속성에 영향을 준다.
7. margin 속성도 width 속성에 영향을 준다.

<br>

<b>[padding 코드 예시]</b>

```html
<style>
  div {
    border: 1px solid red;
    background-color: gray;

    /* 아래 3가지 같은 코딩 */
    /* padding: 50px; */
    /* 		
		padding-top: 50px; 
		padding-right: 50px; 
		padding-bottom: 50px; 
		padding-left: 50px; */
    /* padding: 50px 50px 50px 50px;  */

    /* padding: 25px 50px 75px 100px; */ /* top, right, bottom, left 순서 */

    /* padding: 25px 50px; */ /* 상하, 좌우 설정 */

    padding: 25px 50px 100px; /* top, 좌우, bottom */
  }
</style>

<body>
  <div>
    Lorem ipsum dolor sit amet, consectetur adipisicing elit. Animi repellat
    autem dolore a consequuntur facilis repudiandae alias sunt quis ex. Iste
    possimus porro architecto quo tenetur ipsam facilis amet commodi?
  </div>
</body>
```

<b>[적용 결과]</b>

![alt](https://github.com/Yelin-park/TIL/blob/main/css/img/10%EB%B2%88%20%ED%8C%A8%EB%94%A9.JPG)

<br>

<b>[width, border, padding 영향 확인하는 코드 예시]</b>

```html
<style>
  .ex1,
  .ex2 {
    width: 300px;
  }

  div.ex1 {
    background-color: red;
  }

  div.ex2 {
    background-color: blue;
    color: white;
    padding: 10px; /* 모든 방향 패딩 10px 설정 */
    /* div.ex2의 width의 값은 300px + 10px(left) + 10px(right) = 총 320px */

    border: 5px solid green;
    /* div.ex2의 width의 값은 300px + 10px(left padding) + 10px(right padding) + 5px(left border) + 5px(right border) = 총 330px */
  }

  /* width 유지 + padding, border 유지 => content 너비 축소 */
  * {
    box-sizing: border-box;
  }
</style>

<body>
  <div class="ex1">div width 300px</div>
  <div class="ex2">div width 300px</div>
</body>
```

<b>[적용 결과]</b>
![alt](https://github.com/Yelin-park/TIL/blob/main/css/img/days02_ex05_02_1.JPG)

<br>

![alt](https://github.com/Yelin-park/TIL/blob/main/css/img/days02_ex05_02_2.JPG)

<br>

## 12. CSS의 너비(width)와 높이(height) 속성

1. width, height 속성
2. max-width 속성 : 어떤 요소의 최대 너비를 설정하는 속성
3. min-width 속성 : 어떤 요소의 최소 너비를 설정하는 속성
4. max, min이 들어간 속성은 크기를 줄이거나 늘려도 최대, 최소값을 설정해주기 때문에 스크롤바가 생기지 않음 BUT width로 설정시 스크롤바 생김
5. 속성값 : %(반응형 웹 작업할 때 사용하기..), px, cm 등등
   - inherit(부모의 너비, 높이 상속받겠다.)
   - 설정하지 않으면 기본값은 auto
   - %는 웹브라우저에 맞춰서 보여줌
   * height는 중요하지 않음

<br>

<b>[코드 예시]</b>

```html
<style>
  .wh_test {
    width: 50%;
    max-width: 500px; /* 최대 너비 설정, 웹브라우저를 최대로 키워도 500px은 넘기지 않음 */
    height: 200px;
    background-color: lightblue;
  }
</style>

<body>
  <div class="wh_test">너비 50%, 높이 200px 설정</div>
</body>
```

<b>[적용 결과]</b>

![alt](https://github.com/Yelin-park/TIL/blob/main/css/img/11%EB%B2%88.JPG)

<br>

<b>[코드 예시]</b>

```html
<style>
  .wh_test2 {
    background-color: lightblue;
    height: 100px;
    /* width: 500px; */ /* 고정 크기, 브라우저 크기를 500보다 작게 줄이면 스크롤바가 생김 */
    max-width: 500px; /* 최대값이 500이기 때문에 브라우저 크기에 맞춘다. */
    min-width: 400px; /* 최소 너비, 400까지는 최소로 유지하겠다. 웹브라우저의 크기가 줄어들던 늘어나던 */

    /* 		height 높이
		max-height 최대높이
		min-height 최소높이 */
  }
</style>

<body>
  <div class="wh_test2"></div>
</body>
```

<br>

## 13. CSS의 box model

1. 디자인, 배치(layout)
2. content<br>
   padding<br>
   border<br>
   margin<br>

```html
<style>
  pre {
    border: 15px solid green;
    padding: 50px;
    margin: 20px;
    width: 300px;
  }
</style>
```

3. pre 박스의 총 너비 = 300 + 15 + 15 + 50 + 50 + 20 + 20 = 470<br>
   총 높이 = (90) + 15 + 15 + 50 + 50 + 20 + 20 = 260<br>
   &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;ㄴ90은 설정한 값이 아니라 F12를 눌러서 확인한 값

<br>

## 14. CSS 운곽선(outline)

1. 윤곽선 - 어떤 요소의 테두리(border) 외부에 그려지는 선

<br>

<b>[코드 예시]</b>

```html
<style>
  .outline_test {
    border: 1px solid red;
    padding: 10px;
    margin: auto; /* 자동으로 잡겠다. auto가 기본 값 */

    outline: 1px solid blue;
    /* border + [ 간격 == outline-offset ]+ outline */
    outline-offset: 15px;
  }
</style>

<body>
  <div class="outline_test">
    Lorem ipsum dolor sit amet, consectetur adipisicing elit. Veritatis ad ex
    deleniti labore vero necessitatibus neque eveniet a nesciunt adipisci eum id
    quos magnam recusandae sit doloremque quidem aut perferendis!
  </div>
</body>
```

<b>[적용 결과]</b>

![alt](https://github.com/Yelin-park/TIL/blob/main/css/img/13%EB%B2%88.JPG)

<br><br>

## 15. CSS 텍스트(text) 관련 서식

1. 텍스트 색상 : color
2. 텍스트 정렬 : text-aling
3. 텍스트의 마지막 것만 우측 정렬 : text-aling-right
4. 텍스트 방향 변경 : direction
   - unicode-bidi : bidi-override 설정을 세트로 함께 쓰인다.
5. 텍스트에서 이미지의 수직 정렬 설정 : vertical-align
6. 텍스트 장식 : text-decoration
7. 텍스트 변환 : text-transform

<br>

<b>[코드 예시]</b>

```html
<style>
  .text_test_h3 {
    color: green;
    /* 2. 텍스트 정렬 : text-aling */
    /* text-align: center; */
    /* justify 사전적 의미 : 타당성(정당성)을 보여주다, 해명하다, [인쇄되는 텍스트의 행의 끝을 나란히 맞추다] */
    /* 단어 마다의 간격은 다를 수 있지만 맨 끝에 남는 공간이 다 맞춰짐 */
    text-align: justify;
  }

  p #p1 {
    color: blue;
    border: 1px solid gray;
    /* text-align: justify; */
    text-align-last: right; /* 텍스트의 마지막 것만 우측 정렬 */
  }

  .text_test_div {
    /* 3. 텍스트 방향 변경 : direction*/
    direction: rtl; /* right to left 오른쪽에서 왼쪽으로 */
    unicode-bidi: bidi-override; /* direction과 세트로 쓰임 */
  }
</style>
<style>
  /* align 수평 정렬 */
  /* 텍스트에서 이미지의 수직 정렬 설정 : vertical-align */
  img.a {
    vertical-align: baseline; /* 기본값 */
  }

  img.b {
    vertical-align: text-top;
  }

  img.c {
    vertical-align: text-bottom;
  }

  img.d {
    vertical-align: sub;
  }

  img.e {
    vertical-align: super;
  }
</style>

<body>
  <h3 class="text_test_h3">텍스트(text) 관련된 서식</h3>

  <div class="test_test_div">
    Lorem ipsum dolor sit amet, consectetur adipisicing elit.
  </div>

  <p id="p1">
    Lorem ipsum dolor sit amet, consectetur adipisicing elit. Cum odit
    accusantium quae reiciendis explicabo soluta voluptas non incidunt
    cupiditate fugiat eligendi tempore nihil iure eos maiores ipsum sint debitis
    libero?
  </p>

  <p>
    Lorem<img
      src="../images/sqpurple.gif"
      class="a"
      style="width:9px; height:9px;"
    />ipsum dolor sit amet.
  </p>
  <p>
    Quibusdam<img
      src="../images/sqpurple.gif"
      class="b"
      style="width:9px; height:9px;"
    />consequuntur dolore ipsa optio!
  </p>
  <p>
    Labore<img
      src="../images/sqpurple.gif"
      class="c"
      style="width:9px; height:9px;"
    />cum magnam quia alias.
  </p>
  <p>
    Tempore<img
      src="../images/sqpurple.gif"
      class="d"
      style="width:9px; height:9px;"
    />aperiam dicta deleniti obcaecati.
  </p>
  <p>
    Magni<img
      src="../images/sqpurple.gif"
      class="e"
      style="width:9px; height:9px;"
    />modi fugit et neque.
  </p>
</body>
```

<b>[적용 결과]</b>

![alt](https://github.com/Yelin-park/TIL/blob/main/css/img/days02_ex09.JPG)

<br>

## 15-2. CSS 텍스트 간의 간격 설정

1. text-indent 속성 : 첫 번째 라인(줄)에 들여쓰기
2. line-height 속성 : 라인과 라인 사이의 간격(0은 간격이 작아지고 값이 클 수록 간격이 넓어짐)

<b>[예시]</b>

```html
<p style="text-indent: 50px; line-height: 0.5;">
  Lorem ipsum dolor sit amet, consectetur adipisicing elit. Doloribus odit iure
  totam accusantium aliquid sunt exercitationem veritatis asperiores maiores
  tenetur necessitatibus placeat! Doloremque natus quisquam ut dolores quam
  deserunt esse!
</p>
<p style="text-indent: 50px; line-height: 3;">
  Lorem ipsum dolor sit amet, consectetur adipisicing elit. Doloribus odit iure
  totam accusantium aliquid sunt exercitationem veritatis asperiores maiores
  tenetur necessitatibus placeat! Doloremque natus quisquam ut dolores quam
  deserunt esse!
</p>
```

<b>[적용 결과]</b>

![alt](https://github.com/Yelin-park/TIL/blob/main/css/img/14-2%EB%B2%88.JPG)

<br>

3. letter-spacing 속성 : 텍스트에서 문자와 문자 사이의 간격(공백) 설정(음수값도 설정 가능-겹쳐보임)

<b>[예시]</b>

```html
<h3 style="letter-spacing: 5px;"텍스트간의 간격 설정</h3>
<h3>텍스트간의 간격 설정</h3>
<h3 style="letter-spacing: -3px;">텍스트간의 간격 설정</h3>
```

<b>[적용 결과]</b>

![alt](https://github.com/Yelin-park/TIL/blob/main/css/img/14-3%EB%B2%88.JPG)

<br>

4. word-spacing 속성 : 단어와 단어 사이의 간격(공백) 설정(음수값도 설정 가능-겹쳐보임)

<b>[예시]</b>

```html
<p style="word-spacing: 10px;">
  Lorem ipsum dolor sit amet, consectetur adipisicing elit. Ipsum veritatis?
</p>
<p>
  Lorem ipsum dolor sit amet, consectetur adipisicing elit. Ipsum veritatis?
</p>
<p style="word-spacing: -5px;">
  Lorem ipsum dolor sit amet, consectetur adipisicing elit. Ipsum veritatis?
</p>
```

<b>[적용 결과]</b>

![alt](https://github.com/Yelin-park/TIL/blob/main/css/img/14-4%EB%B2%88.JPG)

<br>

5. white-space(공백) 속성 : 텍스트 개행을 자동으로 하지 않도록 설정(비활성화)

<b>[예시]</b>

```html
<style>
  .ws_test {
    border: 1px solid gray;
    width: 500px;
    margin: 0 auto;

    /* p 태그의 width 속성 때문에 텍스트가 자동으로 개행이 된 것이다. */

    white-space: nowrap; /* 텍스트 개행을 자동으로 하지 말아라(비활성화) */
  }
</style>

<body>
  <p class="ws_test">
    Lorem ipsum dolor sit amet, consectetur adipisicing elit. Accusantium
    recusandae non ducimus alias minus voluptates in nihil nostrum minima qui
    vero harum delectus deleniti sequi sed laborum dolore placeat nulla.
  </p>
</body>
```

<b>[적용 결과]</b>

![alt](https://github.com/Yelin-park/TIL/blob/main/css/img/14-5%EB%B2%88.JPG)

<br>

6. word-break 속성 : 라인(줄) 끝에 도달할 때 단어가 끊어지는 방식을 지정(공백을 안만들게끔)
7. word-wrap 속성 : 긴 단어를 어쩔 수 없이 끊고 다음 줄로 줄바꿈을 하라는 설정

<b>[코드 예시]</b>

```html
<style>
  p .wbw_test {
    border: 1px solid gray;
    width: 200px;

    /* br 개행(줄바꿈) 비활성화 */
    /* white-space: nowrap; */

    /* 긴 단어를 어쩔수 없이~ 끊고 다음 줄로 줄바꿈을 하라는 설정 */
    word-wrap: break-word;

    /* 라인(줄) 끝에 도달할 때 단어가 끊어지는 방식을 지정(공백을 안만들게끔..) */
    word-break: break-all;
  }
</style>

<body>
  <p class="wbw_test">
    Lorem StartipsumdolorsitipwordwrapipsumdolowordwrapmdolorsitEnd amet,
    consectetur ametconsectetur
  </p>
</body>
```

<b>[적용 결과]</b>

![alt](https://github.com/Yelin-park/TIL/blob/main/css/img/14-6%EB%B2%88.JPG)

<br>

## 15-3. CSS 텍스트 그림자

1. text-shadow: offset-x offset-y blur-radius color | none | initial | inherit
2. offset-x : 그림자의 수평 거리를 정합니다. (필수)
3. offset-y : 그림자의 수직 거리를 정합니다. (필수)
4. blur-radius : 흐림 정도를 정합니다. (선택 : 값을 정하지 않으면 0)
5. color : 색을 정합니다. (선택 : 값을 정하지 않으면 브라우저 기본값)
6. none : 그림자 효과를 없앱니다.
7. initial : 기본값으로 설정합니다.
8. inherit : 부모 요소의 속성값을 상속받습니다.

<br>

<b>[코드 예시]</b>

```html
<style>
	h3 .txt_shadow1{
    /* 빨강색, 파랑색 그림자 2개 만들기 */ /* 그림자를 글자 아래에 만들었다. */
		text-shadow: 0 0 3px red, 0 0 5px blue;
	}

  h3 .txt_shadow2{
		/* 수평 수직 번짐 색깔 */
		text-shadow: 2px 2px 5px red;
		color: black;
	}

	h3 .txt_shadow3{
		color: white;
		text-shadow: 1px 1px 2px black, 0 0 25px blue, 0 0 5px darkblue;
	}

</style>
</head>
<body>
<h3 class="txt_shadow1">텍스트 색상, 정렬, 간격, [ 그림자 ]</h3>
<h3 class="txt_shadow2">텍스트 색상, 정렬, 간격, [ 그림자 ]</h3>
<h3 class="txt_shadow3">텍스트 색상, 정렬, 간격, [ 그림자 ]</h3>
</body>
```

<b>[적용 결과]</b>

![alt](https://github.com/Yelin-park/TIL/blob/main/css/img/ex09_04.JPG)

<br>

## 16. CSS 글꼴 설정

1. css 글꼴(font)은 웹 사이트에 적합한 글꼴을 선택하는 것이 중요하다.
2. 읽기 쉬운 글꼴, 색상, 크기 선택 중요하다.
3. 웹 안전 글꼴 : 모든 브라우저/장치에서 보편적으로 설치되어 있는 글꼴 사용하는 것이 안전하다.
4. 하나의 글꼴 명칭에 공백이 있으면 설정시 ""으로 묶어주기
5. 브라우저의 기본 텍스트 크기는 16px
6. 1em == 현재 브라우저의 글꼴 크기 == 16px
7. font-size는 명칭된 이름이나 단위를 사용할 수 있다. (단위 중 em은 브라우저 메뉴에서 텍스트 크기를 조정할 수 있도록 하기 위해서 개발자가 px 대신에 em 단위를 사용)
8. font 약식 설정 순서 : style, variant, weight, size, family 순서

<br>

<b>[코드예시]</b>

```html
<style>
  .font_test {
    /* 하나의 글꼴 명칭에 공백이 있으면 "" 묶어주기 */
    font-family: Arial, Verdana, "Times New Roman";
    /* font-size: xx-large; */ /* 명칭된 이름, 단위 사용 가능(ex. 15px) */
    font-size: 2.5em;
    /font-weight: bold; /* 글씨 굵게하는 정도 설정, 100~900 으로 넣어도 됨. 기본값은 400 */
    font-variant: small-caps; /* 작은 대문자 형태로 나타내겠다. */
    font-style: italic; /* 기울임꼴 텍스트 지정 */
  }
</style>

<body>
  <p class="font_test">Lorem ipsum dolor sit amet.</p>
</body>
```

<b>[적용 결과]</b>

![alt](https://github.com/Yelin-park/TIL/blob/main/css/img/15%EB%B2%88.JPG)

<br>

## 16-2. 구글(Google) 글꼴을 사용하는 방법

1. Google에서 100개 이상의 무료 글꼴 제공
2. link 태그로 설정하여 사용

<b>[코드 예시]</b>

```html
<!-- (주의) 여러 글꼴을 구글에 요청하면 웹 페이지 속도가 느려진다. -->
<!-- 구글에서 제공하는 링크로... -->
<!-- <link rel="stylesheet" href="https://fonts.googleapis.com/css?family=Sofia"> 
<link rel="stylesheet" href="https://fonts.googleapis.com/css?family=Audiowide"> -->
<link
  rel="stylesheet"
  href="https://fonts.googleapis.com/css?family=Sofia|Audiowide"
/>
<!-- | 연산자로 나열해서 사용 -->

<style>
  .ggp_test {
    font-family: "Audiowide", "Sofia", sans-serif;
  }

  .ggh_test {
    font-family: "Sofia", sans-serif;
  }
</style>

<body>
  <p class="ggp_test">
    Lorem ipsum dolor sit amet, consectetur adipisicing elit. Labore eos facere
    voluptates sunt deserunt suscipit itaque nemo magni harum animi debitis
    molestias culpa praesentium iure rerum hic repudiandae. Rem tempora.
  </p>

  <h3 class="ggh_test">010-9898-3423</h3>
</body>
```

<b>[적용 결과]</b>

![[alt](https://) 15-2번](https://github.com/Yelin-park/TIL/blob/main/css/img/15-2%EB%B2%88.JPG)

<br>

## 17. CSS에서 아이콘 사용하기

1. 아이콘 라이브러리 사용(가장 간단한 방법) - ex) fontawesome
2. 구글 아이콘 사용
3. 부트스트랩 아이콘 사용
4. 등등

위의 3가지 방법을 사용하기 위해서는 아래 각각의 script나 link 코드를 추가해야한다.
fontawesome은 회원가입 후 자신의 코드를 넣어야 한다.

```html
<!-- fontawesome -->
<script
  src="https://kit.fontawesome.com/자신의코드.js"
  crossorigin="anonymous"
></script>

<!-- google -->
<link
  rel="stylesheet"
  href="https://fonts.googleapis.com/icon?family=Material+Icons"
/>

<!-- 부트스트랩 -->
<link
  rel="stylesheet"
  href="https://maxcdn.bootstrapcdn.com/bootstrap/3.3.7/css/bootstrap.min.css"
/>
```

<b>[아이콘 사용 코드 예시]</b>

```html
<!-- fontawesome에서 제공하는 아이콘 사용 -->
<i class="fas fa-cloud"></i>
<i class="fas fa-heart" style="font-size: 36px; color: red;"></i>
<i class="fas fa-car"></i>
<i class="fas fa-file"></i>
<i class="fas fa-bars"></i>

<br />
<br />

<!-- google에서 제공하는 아이콘 사용 -->
<i class="material-icons">cloud</i>
<i class="material-icons">favorite</i>
<i class="material-icons">attachment</i>
<i class="material-icons">computer</i>
<i class="material-icons">traffic</i>

<br />
<br />

<!-- 부트스트랩을 사용한 아이콘 -->
<span class="glyphicon glyphicon-cloud"></span>
<span class="glyphicon glyphicon-remove"></span>
<span class="glyphicon glyphicon-user"></span>
<span class="glyphicon glyphicon-envelope"></span>
<span class="glyphicon glyphicon-thumbs-up"></span>
```

<b>[적용 결과]</b>

![alt](https://github.com/Yelin-park/TIL/blob/main/css/img/ex11.JPG)
