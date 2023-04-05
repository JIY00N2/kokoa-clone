## day10 #6.6~6.11

### 2023.04.05 day10 Preview

### 1. reset css

https://meyerweb.com/eric/tools/css/reset/

### 2. h1과 p 같은 text태그 가운데 정렬

```css
text-align: center;
```

### 3. text의 가로 크기 제한

```css
/* 두줄로 가운데 정렬 하려면 display:flex
flex-direction:column
align-items:center*/
width: 50%;
```

### 4. 테두리 없애기

```css
border: none;
```

### 5. input 테두리 없애기

```css
input:focus {
  outline: none;
}
```

### 6. variable

```css
:root {
  --yellow: #ffe311;
}
```

### 7. transition 좀 더 부드럽게 바뀌게 하기

```css
transition: border-color 0.3s ease-in-out;
```

### 8. not

```css
/* input type이 submit가 아닐때 밑에 적용*/
#login-form input:not([type="submit"]) {
  border-bottom: 1px solid rgba(0, 0, 0, 0.2);
  transition: border-color 0.3s ease-in-out;
}
```

### 9. cursor

```css
cursor: pointer;
```

### 10. inherit

```css
#login-form a {
  /*a가 색상을 아버지로부터 상속 받아 옴 
  default 색은 블랙임 */
  text-align: center;
  text-decoration: none;
  color: inherit;
}
```

### 11. form의 두가지 속성

1. action - 어떤 페이지로 data를 보낼건지 지정할 수 있음

2. method
   > 1. POST - 백엔드 서버에 정보를 전송하는 방식
   >    2.GET - 보안에 취약, URL에 포함되어도 상관없는 정보들을 GET으로 전송

```html
<!--login누르면 friends.html로 이동  -->
<form action="friends.html" method="GET">
    <input name="username" type="text"></input>
    <input name="password" type="text"></input>
    <input type="submit" value="log in"></input>
</form>
```

### 12. nav

```css
.nav {
  /* 밑에 화면 고정 */
  position: fixed;
  bottom: 0;
  width: 100%;
  box-sizing: border-box;
  /* 색깔 밑 패딩 */
  background-color: gray;
  padding: 20px 40px;
  border-top: 1px solid rgba(0, 0, 0, 0.3);
}

.nav__ul {
  display: flex;
  justify-content: space-between;
}

.nav__a {
  /* 검정색 */
  color: inherit;
}
```

```html
<!-- nav>ul>li*4>a -->
<nav class="nav">
  <ul class="nav__ul">
    <li class="nav__li">
      <a class="nav__a" href="friends.html">아이콘 들어가기</a>
    </li>
    <li class="nav__li">
      <a class="nav__a" href="#">아이콘 들어가기</a>
    </li>
    <li class="nav__li">
      <a class="nav__a" href="#">아이콘 들어가기</a>
    </li>
    <li class="nav__li">
      <a class="nav__a" href="#">아이콘 들어가기</a>
    </li>
  </ul>
</nav>
```

### 13. 화면 안에 다 나오게함

```css
box-sizing: border-box;
```

### 2023.04.05 day10 Review

my answer

```html
<!DOCTYPE html>
<html>
  <head>
    <meta charset="utf-8" />
    <meta name="viewport" content="width=device-width" />
    <title>You Are Awesome!</title>
    <link
      rel="stylesheet"
      href="https://cdn.jsdelivr.net/npm/reset-css@5.0.1/reset.min.css"
    />
    <link
      rel="stylesheet"
      href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css"
    />
    <link rel="stylesheet" href="style.css" />
  </head>

  <body>
    <header>
      <i class="fa-solid fa-xmark"></i>
      <h1>Playlist</h1>
    </header>
    <main>
      <section class="playlist-info">
        <div class="playlist-info__picture">
          <i class="far fa-image fa-3x"></i>
        </div>
        <div class="playlist-info__text">
          <h2>Refrain</h2>
          <h3>by Aimer</h3>
        </div>
      </section>
      <section class="playlist-btn">
        <div class="playlist-btn__square">
          <i class="fas fa-play fa-xs"></i>
          <span>Play</span>
        </div>
        <div class="playlist-btn__heart">
          <i class="fa-regular fa-heart"></i>
        </div>
        <div class="playlist-btn__plus">
          <i class="fa-solid fa-plus"></i>
        </div>
      </section>
      <ul class="playlist">
        <li class="playlist-song">
          <div class="playlist-song__picture"></div>
          <div class="playlist-song__text">
            <h4>OMG</h4>
            <h5>NewJeans</h5>
          </div>
        </li>
        <li class="playlist-song">
          <div class="playlist-song__picture"></div>
          <div class="playlist-song__text">
            <h4>Memories</h4>
            <h5>Conan Gray</h5>
          </div>
        </li>
        <li class="playlist-song">
          <div class="playlist-song__picture"></div>
          <div class="playlist-song__text">
            <h4>먹구름</h4>
            <h5>윤하</h5>
          </div>
        </li>
        <li class="playlist-song">
          <div class="playlist-song__picture"></div>
          <div class="playlist-song__text">
            <h4>2soon</h4>
            <h5>keshi</h5>
          </div>
        </li>
        <li class="playlist-song">
          <div class="playlist-song__picture"></div>
          <div class="playlist-song__text">
            <h4>Heartache</h4>
            <h5>One OK Rock</h5>
          </div>
        </li>
      </ul>
    </main>
  </body>
</html>
```

```css
@import url("https://fonts.googleapis.com/css2?family=Noto+Sans+KR:wght@100;500&display=swap");

* {
  box-sizing: border-box;
}

body {
  font-family: "Noto Sans KR", sans-serif;
  height: 100vh;
  border: 5px solid #00c6ad;
  padding: 50px 50px 50px 40px;
}

header {
  display: flex;
  justify-content: center;
  text-align: center;
  position: relative;
}
header i {
  position: absolute;
  left: 0;
  font-size: 30px;
}

h1 {
  font-size: 30px;
  font-weight: 700;
}

.playlist-info,
.playlist-song {
  width: auto;
  height: 110px;
  margin-top: 30px;
  display: flex;
  justify-content: flex-start;
}

.playlist-info__picture,
.playlist-song__picture {
  width: 100px;
  height: 100px;
  background-color: #ffbd11;
  border-radius: 10px;
  border: 2px solid black;
  display: flex;
  justify-content: center;
  align-items: center;
}
.playlist-info__picture > i {
  font-size: 35px;
  color: white;
}
.playlist-info__text,
.playlist-song__text {
  margin-left: 30px;
  width: auto;
  height: 100px;
  display: flex;
  justify-content: space-around;
  flex-direction: column;
}
h2 {
  font-size: 40px;
  font-weight: 900;
}
h3 {
  fonst-size: 30px;
  font-weight: 600;
}

.playlist-btn {
  margin: 30px 0px;
  display: flex;
  justify-content: space-between;
  align-items: center;
}

.playlist-btn__square,
.playlist-btn__heart,
.playlist-btn__plus {
  width: 180px;
  height: 50px;
  border: 2px solid black;
  border-bottom-width: 5px;
  border-radius: 10px;
  display: flex;
  justify-content: center;
  align-items: center;
}
.playlist-btn i {
  font-size: 20px;
}
.playlist-btn__square > i {
  margin-right: 15px;
}
.playlist-btn__square > span {
  font-size: 18px;
  font-weight: 600;
}
.playlist-btn__heart,
.playlist-btn__plus {
  width: 50px;
  border-radius: 50%;
}

.playlist-song {
  height: 60px;
}
.playlist-song__picture {
  width: 60px;
  height: 60px;
}

.playlist-song__text {
  height: 60px;
}
h4 {
  font-size: 20px;
  font-weight: 900;
}
h5 {
  font-size: 15px;
  font-weight: 400;
  opacity: 0.8;
}
li:first-child > .playlist-song__picture {
  background-color: #54c0f7;
}
li:nth-child(2) > .playlist-song__picture {
  background-color: #ff9ef2;
}
li:nth-child(3) > .playlist-song__picture {
  background-color: #6afce6;
}
li:nth-child(4) > .playlist-song__picture {
  background-color: #eef78f;
}
li:nth-child(5) > .playlist-song__picture {
  background-color: #b68bef;
}
```
