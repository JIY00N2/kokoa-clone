### 2023.04.01 day6 Review

```css
body {
  height: 100vh;
  background-color: #ff6347;
  display: flex;
  justify-content: center;
  align-items: center;
}

.beige-box {
  background-color: #f5deb3;
  border: 2px solid black;
  width: 250px;
  height: 250px;
}

.turquoise-parent {
  height: 100%;
  display: flex;
  justify-content: space-between;
  align-items: center;
  flex-direction: column;
}

.turquoise-box {
  background-color: #008080;
}

.turquoise-box:first-child {
  margin-top: 20px;
  border: 3px solid white;
  width: 55px;
  height: 55px;
}
.turquoise-box:last-child {
  margin-bottom: 20px;
  border: 3px solid white;
  width: 55px;
  height: 55px;
}
.turquoise-box:nth-child(2) {
  border: 3px dashed white;
  width: 210px;
  height: 55px;
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
    <div class="beige-box">
      <div class="turquoise-parent">
        <div class="turquoise-box"></div>
        <div class="turquoise-box"></div>
        <div class="turquoise-box"></div>
      </div>
    </div>
  </body>
</html>
```
