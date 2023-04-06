## day11 #6.12~6.17

### 2023.04.06 day11 Preview

### 1. border-box - padding을 주고 싶은데 box사이즈를 그대로 유지하기

```css
box-sizing: border-box;
```

### 2. 아이콘 위에 그림 그리기

```html
<a class="nav__link" href="#">
  <span class="nav__notification">1</span>
  <i class="far fa-comment fa-2x"></i>
</a>
```

```css
.nav__list {
  display: flex;
  justify-contnet: space-between;
}

.nav__link {
  position: relative;
}
.nav__notification {
  background-color: tomato;
  /* span이기 때문에 display:block을 해야하지만 display:flex때문에 지우자*/
  /* display: block; */
  width: 20px;
  height: 20px;
  border-radius: 50%;
  /* 숫자 1을 가운데 오게 하기 */
  display: flex;
  justify-content: center;
  align-items: center;
  color: white;
  font-weight: 600;
  /* 메세지 위에 숫자 1이 오게하기 */
  /* 가장 가까운 부모에게 position:relative; */
  position: absolute;
  left: 15px;
  bottom: 15px;
}
```

### 3. screen header

```html
<header class="screen-header">
  <h1 class="screen-header__title">Friends</h1>
  <div class="screen-header__icons">
    <span><i class="fas fa-search fa-lg"></i></span>
    <span><i class="fas fa-music fa-lg"></i></span>
    <span><i class="fas fa-cog fa-lg"></i></span>
  </div>
</header>
```

```css
.screen-header {
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 25px;
}

.screen-header__title {
  font-size: 22px;
  font-weight: 600;
}

.screen-header__icons span {
  margin-left: 25px;
}
```

### 4. 텍스트 가운데 정렬

```css
text-align: center;
display: block;
```

### 5. user component

```html
<div class="user-component">
  <div class="user-component__column">
    <img src="#" class="user-component__avatar" />
    <div class="user-component__text">
      <h4 class="user-component__title">yoon</h4>
      <h6 class="user-component__subtitle">texttext</h6>
    </div>
  </div>
  <div class="user-component__column"></div>
</div>
```

```css
.user-component,
.user-component__column:first-child {
  display: flex;
  /* 중앙 정렬 */
  align-items: center;
}
.user-component__avatar {
  width: 70px;
  height: 70px;
  border-radius: 30px;

  margin-right: 20px;
}

.user-component__title {
  font-weight: 600;
  font-size: 22px;
}

.user-component__subtitle {
  margin-top: 8px;
  font-size: 17px;
  color: rgba(0, 0, 0, 0.5);
}
```

### 6. 다른건 동일하게 하고 싶은데 특정한 것만 바꿀때 class modify 하자

```html
<img src="#" class="user-component__avatar user-component__avatar--xl" />
```

```css
.user-component__avatar--xl {
  width: 80px;
  height: 80px;
}
```

### 2023.04.06 day11 Review

my answer

```css
/* variable.css */
:root {
  --opacity: 0.4;
  --yellow: #fecd32;
}
```

```css
/* style.css */
@import url("https://fonts.googleapis.com/css2?family=Open+Sans&display=swap");
@import "variable.css";
* {
  box-sizing: border-box;
}

body {
  font-family: "Open Sans", sans-serif;
}

.library-header {
  background-color: var(--yellow);
  height: 120px;
  position: relative;
}

.library-header__column {
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 40px 20px 20px 20px;
}

i {
  font-size: 25px;
}
.library-header__column span:nth-child(2) {
  font-size: 30px;
  font-weight: bold;
}

.search-books {
  display: flex;
  justify-content: center;
  align-items: center;
}

input {
  width: 90%;
  border-radius: 25px;
  padding: 15px 35px;
  font-size: 15px;
  position: absolute;
  top: 100px;
  border: none;
  box-shadow: 5px 5px 5px rgba(0, 0, 0, 0.3);
}
.search-books i {
  position: absolute;
  top: 112px;
  right: 50px;
  opacity: var(--opacity);
}

input::placeholder {
  opacity: var(--opacity);
}
.wrapper {
  margin: 60px 30px;
}
.book-info {
  display: flex;
}
h2 {
  font-size: 25px;
  font-weight: 600;
  margin: 25px 0px;
}
.book-image {
  width: 150px;
  height: 210px;
}
.book-data {
  display: flex;
  flex-direction: column;
  margin-left: 30px;
}
.book-data__title {
  font-size: 25px;
  font-weight: 600;
}
.book-data__name {
  font-size: 18px;
  opacity: var(--opacity);
  margin: 15px 0px;
}
.book-data__rating > i {
  font-size: 15px;
  color: var(--yellow);
}
.book-data__tags {
  margin: 20px 0px;
  display: flex;
  justify-content: space-between;
}

.book-data__tag {
  display: block;
  padding: 10px 20px;
  background-color: #f7f7f7;
  text-align: center;
  border-radius: 5px;
  font-weight: 600;
}
.book-data__shops {
  display: flex;
  justify-content: space-between;
  align-items: center;
}
.book-data__bookmark {
  width: 40px;
  height: 40px;
  border-radius: 50%;
  background-color: var(--yellow);
  display: flex;
  justify-content: center;
  align-items: center;
}
.book-data__bookmark > i {
  font-size: 20px;
}
.book-data__buy {
  padding: 10px 30px;
  background-color: black;
  text-align: center;
  color: white;
  border-radius: 5px;
  margin-left: 50px;
}
.top-books__list {
  display: flex;
  overflow-x: scroll;
  padding-bottom: 15px;
}

.top-book {
  margin-right: 20px;
}
.top-book img {
  width: 100px;
  height: 150px;
  border-radius: 3px;
  border: 1px solid black;
}
.top-books__rating i {
  color: var(--yellow);
  font-size: 3px;
  margin-top: 10px;
  text-align: center;
}
.author {
  display: flex;
}
.author img {
  width: 180px;
  height: 150px;
  border-radius: 3px;
  margin-right: 30px;
}

.author-name {
  font-size: 20px;
  font-weight: 900;
  display: block;
  margin: 20px 0px;
}
.author-data {
  font-size: 18px;
  opacity: var(--opacity);
}
```

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
      href="https://cdn.jsdelivr.net/gh/FortAwesome/Font-Awesome@5.14.0/css/all.min.css"
    />
    <link rel="stylesheet" href="style.css" />
  </head>

  <body>
    <header class="library-header">
      <div class="library-header__column">
        <span><i class="fas fa-bars"></i></span>
        <span>library</span>
        <span><i class="fas fa-shopping-basket"></i></span>
      </div>
    </header>
    <div class="search-books">
      <input type="text" placeholder="Search books..." />
      <i class="fas fa-search"></i>
    </div>
    <main class="wrapper">
      <h2>Book of the day</h2>
      <div class="book-info">
        <img
          class="book-image"
          src="https://i.namu.wiki/i/Md1GNbJasfBfeG6Vy-Ye7nvS2pI5NXnJdVzuOpWHoAyT6wi75stz2CGiPlYdgP1DUEWozx5Hb_AYr_kSd3XC7QlttbnwyDcR6pyIZEie_ztAck2nOSSrY4rivfwMhDw5853DbgAGB2N362OZG7XwnA.webp"
        />
        <div class="book-data">
          <h3 class="book-data__title">Blindness</h3>
          <h5 class="book-data__name">José Saramago</h5>
          <div class="book-data__rating">
            <i class="fas fa-star"></i>
            <i class="fas fa-star"></i>
            <i class="fas fa-star"></i>
            <i class="fas fa-star"></i>
            <i class="fas fa-star-half-alt"></i>
          </div>
          <div class="book-data__tags">
            <span class="book-data__tag">Mystery</span>
            <span class="book-data__tag">SF</span>
          </div>
          <div class="book-data__shops">
            <span class="book-data__bookmark"
              ><i class="fas fa-bookmark"></i
            ></span>
            <span class="book-data__buy">Book Now</span>
          </div>
        </div>
      </div>
      <h2>Top Adventures</h2>
      <div class="top-books__list">
        <div class="top-book">
          <img src="https://image.yes24.com/goods/1387488/XL" />
          <div class="top-books__rating">
            <i class="fas fa-star"></i>
            <i class="fas fa-star"></i>
            <i class="fas fa-star"></i>
            <i class="fas fa-star"></i>
            <i class="fas fa-star-half-alt"></i>
          </div>
        </div>
        <div class="top-book">
          <img src="https://image.yes24.com/Goods/8157957/XL" />
          <div class="top-books__rating">
            <i class="fas fa-star"></i>
            <i class="fas fa-star"></i>
            <i class="fas fa-star"></i>
            <i class="fas fa-star"></i>
            <i class="fas fa-star"></i>
          </div>
        </div>
        <div class="top-book">
          <img
            src="https://image.aladin.co.kr/product/7/27/cover500/8970123695_3.jpg"
          />
          <div class="top-books__rating">
            <i class="fas fa-star"></i>
            <i class="fas fa-star"></i>
            <i class="fas fa-star"></i>
            <i class="fas fa-star"></i>
            <i class="fas fa-star-half-alt"></i>
          </div>
        </div>
        <div class="top-book">
          <img
            src="https://image.aladin.co.kr/product/4/6/letslook/A93746005X_f.jpg"
          />
          <div class="top-books__rating">
            <i class="fas fa-star"></i>
            <i class="fas fa-star"></i>
            <i class="fas fa-star"></i>
            <i class="fas fa-star"></i>
            <i class="fas fa-star-half-alt"></i>
          </div>
        </div>
        <div class="top-book">
          <img
            src="https://contents.kyobobook.co.kr/sih/fit-in/458x0/pdt/9788996991342.jpg"
          />
          <div class="top-books__rating">
            <i class="fas fa-star"></i>
            <i class="fas fa-star"></i>
            <i class="fas fa-star"></i>
            <i class="fas fa-star"></i>
            <i class="fas fa-star"></i>
          </div>
        </div>
      </div>
      <h2>Popular authors</h2>
      <div class="author">
        <img
          src="https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcQ2CDsjhPO2nGLWvtS9gwHB5PXSTZmomp4ZbUD4Wc20P4wXJgyM0KxexDCCbEkt5Jw6aGw&usqp=CAU"
        />
        <div class="author-info">
          <h5 class="author-name">Keigo Higashino</h5>
          <p class="author-data">
            He is a popular writer who is very famous in Korea as well as in
            Japan, and is famous for writing bestsellers such as The Miracle of
            the Namiya General Store and The Devotion of Suspect X.
          </p>
        </div>
      </div>
    </main>
  </body>
</html>
```
