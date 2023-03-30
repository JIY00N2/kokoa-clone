## day5,6,8,9 #3.0~3.5 / 3.6~3.11 / 3.12~3.16 / 3.17

### 2023.03.30 Preview

### 1. css를 HTML에 추가하는 방법

```html
<link href="폴더이름.css" rel="stylesheet" />
```

### 2. css - 위에서 아래로 적용

```css
selector(html 태그) {
  attribute(속성)
}

#id {
}

.class {
}

*{
  // 모든 요소 지칭
}
```

### 3. block(div, header, main, section, footer, article...) 세로로 배치됨, 옆에 아무것도 못 옴

### 3-1 div

```html
// 세로로 이어서 두개의 박스
<div></div>
<div></div>
```

### 3-2 block의 특징

> 1.  margin - box의 경계의 바깥 공간
> 2.  padding - box의 경계로 부터 안쪽 공간
> 3.  border - box의 경계

### 4. inline(span, a, img) - 가로로 배치됨, 옆에 올 수 있음, 이것을 제외하고 모두 block

```html
// 가로로 이어서 3개
<span>hello</span>
<span>hello</span>
<span>hello</span>
```

### 4-1 inline은 width(너비), hegith(높이)가 없다

### 4-2 inline-block을 통해 4-1 해결 가능하지만 사용하지 말자 -> flex 사용

### 5. css를 통해 block과 inline을 지정 할 수 있음

```css
display: block;
display: inline;
```

### 6. margin, padding 적용 방식 동일

```css
margin: 20px 10px; // 상하 , 좌우
margin: 20px 10px 25px 5px; // 상 우 하 좌(시계방향)
margin: 10px; // 상하좌우
```

### 6-1 collapsing margins(상하에서만 발생) -body안에 div의 위 아래 마진이 body의 마진과 만나면 둘 중 큰 값의 마진으로 body에 적용된다, body와 div의 margin은 하나로 취급됨

### 7. border

```css
border: 2px solid black; // 주로 이 형식 많이 사용
```

### 8. class 여러개 지정하기

```html
<span class="btn tomato teal">hello</span> // btn, tomato, teal class 적용
```

### 9. flexbox

1. 자식 element에는 어떤것도 적지 않는다. 부모 element에만 명시
   <br>-> div(자식)에 flex를 적용하고 싶다 -> body(부모)에 명시
2. default 값: 주축(main axis) - 수평
3. default 값: 교차축(cross axis) - 수직

```css
body {
  display: flex;
  hegiht: 100vh; // 화면 높이의 100%
  justify-content: center; // 주축(수평), div가 모두 가운데로 이동
  align-items: center; // 교차축(수직) -> body의 height과 관련
}
```

```html
<body>
  <div></div>
  <div></div>
  <div></div>
</body>
```

### 10. flex-direction

1. default 값: row
2. flex-direction: column; <br>
   \-> 주축: 수직, 교차축: 수평으로 변경
3. flex-direction: column-reverse;<br>
   \-> 밑에서 위로
4. flex-direction: row-reverse;<br>
   \-> 오른쪽에서 왼쪽으로

### 11. position(absolute와 relative 짝꿍)

```css
position: fixed; // 박스 고정, top, bottom, left, right를 사용하면 이전 박스와 영향 받지 않음
position: static; // 박스를 처음 위치하는 곳
position: relative; // element가 처음 위치한 곳을 기준으로 조금씩 수정 top, bottom, left, right
position: aboslute; // top, bottom, left, right를 쓰고 싶을 때 사용, 가장 가까운 relatvie 부모를 기준으로 이동시킴
```

### 12. Pseudo Selectors

```css
div:last-child {
  // 마지막 div
}
div:first-child {
  // 첫 번째 div
}
span:nth-child(2) {
  // 두번쨰 span
}
span:nth-child(even) {
  // 짝수번쨰 span
}
span:nth-child(5n + 1) {
  // 5번쨰마다
}
```

### 13. Combinators

```html
<div>
  <span>hello</span>
  <p>blablabalbalablabalbalbalabal<span>hi</span></p>
  <span>bye</span>
</div>

<div>
  <input type="text" placeholder="username" />
  <input type="password" required placeholder="password" />
</div>
```

```css
p span {
  // 부모 자식
  // p안의 span 선택하기
}

div > span {
  // hello span에 밑줄 주기
  // 바로 밑 자식
  text-deocration: underline;
}

p + span {
  // bye span에 밑줄 주기
  // p 바로 다음에 오는 span 찾기
  text-deocration: underline;
}

p ~ span {
  // p다음에 오긴 하는데 중간에 뭔가 있을때
}

input:required {
  // input중에 required 써있는것만 적용
}
input[placeholder~="name"] {
  // input중에 placeholder에 name이 있을때
}
input[placeholder*="name"] {
  // input중에 placeholder에 name이 포함되어 있을때
}
```

### 14. State

1. active: 해당 요소를 마우스로 클릭했을 때 효과 적용
2. hover: 마우스가 해당 요소 위를 지나갈 때 효과 적용
3. focus: 키보드로 선택되었을 때 효과 적용
4. focus-within: 부모 요소에게 적용, 자신의 자식 요소중 하나가 focused 되었을 때 효과를 적용
5. visited: 방문한 사이트일 경우에 효과를 적용
6. 여러 조건들 나열

```css
hgih-tag: hover low-tag: focus {
}
```

### 2023.03.30 day4 Review

```html
<body>
  <h1>Create An Account</h1>
  <form>
    <div class="first-name">
      <label for="first-name__input">First name</label>
      <input
        id="first-name__input"
        type="text"
        required
        placeholder="First-name"
      />
    </div>
    <div class="last-name">
      <label for="last-name__input">Last name</label>
      <input
        id="last-name__input"
        type="text"
        required
        placeholder="Last name"
      />
    </div>
    <div class="email">
      <label for="email__input">Email</label>
      <input id="email__input" type="email" required placeholder="Email" />
    </div>
    <div class="user-name">
      <label for="user-name__input">Username</label>
      <input
        id="user-namel__input"
        type="text"
        required
        placeholder="Username"
      />
    </div>
    <div class="password">
      <label for="password__input">Password</label>
      <input
        id="password__input"
        type="password"
        required
        placeholder="Password"
        minlength="10"
      />
    </div>
    <div class="birth-date">
      <label for="birth-date__input">Birth date</label>
      <input id="birth-date__input" type="date" required />
    </div>
    <div class="condition">
      <label for="conditione__input">How happy are you?</label>
      <input id="condition__input" type="range" required list="markers" />
      <datalist id="markers">
        <option value="0"></option>
        <option value="10"></option>
        <option value="20"></option>
        <option value="30"></option>
        <option value="40"></option>
        <option value="50"></option>
        <option value="60"></option>
        <option value="70"></option>
        <option value="80"></option>
        <option value="90"></option>
        <option value="100"></option>
      </datalist>
    </div>
    <div class="favorite-color">
      <label for="color__input">What is your fav.color?</label>
      <input id="color__input" type="color" required />
    </div>
    <div class="submit">
      <input id="submit__input" type="submit" value="Create Account" />
    </div>
  </form>
</body>
```
