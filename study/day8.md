## day8 #4.0~4.6

### 2023.04.03 day8 Preview

### 1. transition 속성은 state가 없는 요소에 붙임

```css
a {
  color: wheat;
  background-color: tomato;
  transition: background-color 10s ease-in-out, color 5s ease-in-out;
  /* hover에 있는 background-color를 10초동안 부드럽게 바꾸고 color를 5초동안 부드럽게 바꿈 == transition: all 5s ease-in-out*/
}
a:hover {
  color: tomato;
  background-color: wheat;
}
```

### 2. transition 변화를 쉽게 알아보는 사이트

https://matthewlein.com/tools/ceaser

### 2-1 animation 사이트

https://animista.net/

### 3. transition 종류: linear, ease-in, ease-in-out, ease-out, ease..

### 4. transformation과 transition을 합치면 애니메이션을 만들 수 있다.

```css
img {
  transition: transform 5s ease-in-out;
}
img:hover {
  transform: rotateX(360deg);
}
```

### 5. Animations

```css
/* first option */
@keyframes coinFlip {
  from {
    transform: rotateX(0);
  }
  to {
    transform: rotateX(360deg);
  }
}

/* second option 원하는 step만큼 사용*/
@keyframes coinFlip {
  0% {
    transform: rotateX(0);
  }
  50% {
    transform: rotateX(360deg) translateX(-100px);
  }
  100% {
    transform: rotateX(0);
  }
}

img {
  animation: coinFlip 5s ease-in-out infinite;
}
```

### 6. media query - 오직 css만을 이용해서 스크린의 사이즈를 알 수 있는 방법, 알고 싶은 조건 작성, and로 연결, element 요소 안에 작성

```css
/* 이 스크린이 600px 보다 크고 750px보다 작을 때 {} 실행 */
@media screen and (min-width: 600px) and (max-width: 750px) {
  div {
    background-color: tomato;
  }
}
```

### 7. orientation - 세로모드인지 가로모드인지 구별

1. orientation: landscape - 가로
2. orientation: portrait - 세로

```css
@media screen and (orientation: landscape) {
}
```

### 8. media type

1. @media screen{} - 화면에 보여지는 옵션
2. @media print{} - 프린트 할때 옵션 설정 가능

### 2023.04.03 day8 Review

```css
body {
  background-color: #f5f5f5;
  height: 100vh;
  font-weight: bold;
  font-family: Georgia, serif;
}

.header {
  text-align: center;
  font-size: 35px;
  margin: 40px 0px;
}

.divide-two {
  display: flex;
  justify-content: center;
  text-align: center;
}

.tomato-box,
.teal-box,
.burlywood-box,
.thistle-box {
  background-color: tomato;
  width: 200px;
  height: 320px;
  border: 5px solid white;
  margin: 10px;
}

.teal-box {
  background-color: #008080;
}
.burlywood-box {
  background-color: #deb887;
}
.thistle-box {
  background-color: #d7bfd7;
}

.white-box {
  margin-top: 15px;
  width: auto;
  height: 110px;
  background-color: white;
  display: flex;
  text-align: left;
  justify-content: center;
  flex-direction: column;
}

.color-name,
.color-code {
  font-size: 23px;
  padding-left: 10px;
  margin: 15px 0px;
}

.color-code {
  font-size: 18px;
}
```

```html
<!DOCTYPE html>
<html>
  <head>
    <meta charset="utf-8" />
    <meta name="viewport" content="width=device-width" />
    <link rel="stylesheet" href="style.css" />
    <title>repl.it</title>
  </head>

  <body>
    <header class="header">The Best Colors</header>
    <div class="divide-two">
      <div class="tomato-box">
        <div class="white-box">
          <div class="color-name">Tomato</div>
          <div class="color-code">#FF6347</div>
        </div>
      </div>
      <div class="teal-box">
        <div class="white-box">
          <div class="color-name">Teal</div>
          <div class="color-code">#008080</div>
        </div>
      </div>
    </div>
    <div class="divide-two">
      <div class="burlywood-box">
        <div class="white-box">
          <div class="color-name">Burlywood</div>
          <div class="color-code">#DEB887</div>
        </div>
      </div>
      <div class="thistle-box">
        <div class="white-box">
          <div class="color-name">Thistle</div>
          <div class="color-code">#D7BFD7</div>
        </div>
      </div>
    </div>
  </body>
</html>
```
