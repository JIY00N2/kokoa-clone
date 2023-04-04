## day9 #6.0~6.5

### 2023.04.04 day9 Preview

### 1. BEM(Block Element Modifier)

참고 사이트: https://nykim.work/15

### 2. font awesome

```html
// body 태그 닫기전 바로 위에 작성
<script
  src="https://kit.fontawesome.com/6478f529f2.js"
  crossorigin="anonymous"
></script>
```

### 3. css 단축키 => link:css 엔터

### 4. font 사이트

https://fonts.google.com/

### 5.css hack(justify-content대신사용가능)

- 레시피 같이 어디든 쓸 수 있다. 이상하지만 작동한다.<br>

1. 상위 박스 : justify-content: center; -중앙으로 몰림<br>
2. 내부 박스 범위 : width: 33%; -왼쪽으로 몰려서 범위 벌어짐, 왼쪽 위치할 박스는 왼쪽에 붙어서 정렬됨<br>
3. 중앙에 위치할 박스 : display: flex; justify-content: center; -중앙에 위치할 박스만 중앙에 위치함<br>
4. 오른쪽에 정렬할 박스 : _display_: flex; _justify-content_: flex-end; _align-items_: center; -오른쪽에 붙어서 정렬됨<br>

```html
<div class="status-bar">
  <div class="status-bar__column">
    <span>No service</span>
    <i class="fas fa-wifi"></i>
  </div>
  <div class="status-bar__column">
    <span>18:43</span>
  </div>
  <div class="status-bar__column">
    <span>100%</span>
    <i class="fas fa-battery-full"></i>
    <i class="fas fa-bolt"></i>
  </div>
</div>

<header class="welcome-header">
  <h1 class="welcome-header__title">Welcome to Kokoa Clone</h1>
  <p class="welcome-header__text">
    If you have a kokoa Account, log in with your emial or phone number
  </p>
</header>

<form id="login-form">
  <input type="text" placeholder="Email or phone number" />
  <input type="password" placeholder="Password" />
  <input type="submit" value="Log in" />
  <a href="#">Find kokoa account or password</a>
</form>
```

```css
body {
  font-family: -apple-system;
}
.status-bar {
  /*세개 div 가로로 오게하기 */
  display: flex;
  /*5-1*/
  justify-content: center;
}
/* 5-2 */
.status-bar__column {
  width: 33%;
}
/* 5-3 */
.status-bar__column:nth-child(2) {
  display: flex;
  justify-content: center;
}
/* 5-4 */
.status-bar__column:last-child {
  display: flex;
  justify-content: flex-end;
  align-items: center; /* 중앙에 오게 하기 */
}
/*No service와 아이콘 사이에 간격 주기 */
.status-bar__column:first-child span {
  margin-right: 5px;
}

/*밧데리 아이콘들 사이의 간격 주기 */
.status-bar__column .fa-battery-full {
  margin: 0px 3px;
}
```

### 2023.04.04 day9 Review

my answer

```css
body {
  height: 100vh;
  background-color: black;
  display: flex;
  justify-content: center;
  align-items: center;
}

.blue-box {
  width: 470px;
  height: 410px;
  background-color: #6bbcbe;
  display: flex;
  justify-content: center;
  align-items: center;
  flex-direction: column;
}

.box {
  display: flex;
  justify-content: center;
  align-items: center;
  margin: 30px 0px;
}

@keyframes rotate {
  0% {
    transform: translateX(0%) translateY(0%);
  }
  50% {
    transform: translateX(180%) translateY(-180%);
  }
  100% {
    transform: translateX(360%) translateY(0%);
  }
}

.white-dot {
  width: 10px;
  height: 10px;
  background-color: white;
  border-radius: 50%;
  margin: 0px 5px;
}

.white-dot:nth-child(1) {
  animation: rotate 1s ease-in-out infinite;
}

@keyframes scaleUp {
  0% {
    transform: scaleY(1);
  }
  50% {
    transform: scaleY(2);
  }
  100% {
    transform: scaleY(1);
  }
}

.white-box {
  width: 10px;
  height: 30px;
  background-color: white;
  margin: 0px 5px;
  animation: scaleUp 1s ease-in-out infinite;
}

.white-box:nth-child(1) {
  animation-delay: 0.1s;
}
.white-box:nth-child(2) {
  animation-delay: 0.2s;
}
.white-box:nth-child(3) {
  animation-delay: 0.3s;
}
.white-box:nth-child(4) {
  animation-delay: 0.4s;
}
.white-box:nth-child(5) {
  animation-delay: 0.5s;
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
    <div class="blue-box">
      <div class="box">
        <div class="white-dot"></div>
        <div class="white-dot"></div>
        <div class="white-dot"></div>
      </div>
      <div class="box">
        <div class="white-box"></div>
        <div class="white-box"></div>
        <div class="white-box"></div>
        <div class="white-box"></div>
        <div class="white-box"></div>
      </div>
    </div>
  </body>
</html>
```
