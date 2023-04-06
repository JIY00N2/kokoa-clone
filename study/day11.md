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
