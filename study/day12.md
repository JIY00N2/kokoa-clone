## day12

### 2023.04.7 day12 review

my answer
style.css

```css
@import url("https://fonts.googleapis.com/css2?family=Nanum+Gothic&display=swap");
@import "variable.css";

* {
  box-sizing: border-box;
}
body {
  background-color: #f6f6f6;
  display: flex;
  justify-content: space-around;
  flex-wrap: wrap;
  font-family: "Nanum Gothic", sans-serif;
  padding: 30px;
  color: var(--black);
}
.screen {
  width: 40vh;
  height: 80vh;
  background-color: white;
  padding: 30px 20px;
  border-radius: 20px;
  position: relative;
}
.screen-header {
  display: flex;
  justify-content: space-between;
}
.main-song__info {
  display: flex;
  justify-content: space-between;
  align-items: center;
  flex-direction: column;
}
.main-song__info img {
  width: 70px;
  height: 70px;
  border-radius: 50%;
  box-shadow: var(--black-shadow);
}
h2 {
  font-size: 20px;
  font-weight: 600;
  margin-top: 20px;
  margin-bottom: 15px;
}
h5 {
  font-size: 12px;
  font-weight: 600;
  color: var(--gray);
}
.main-song__action {
  display: flex;
  justify-content: center;
}
.action-button {
  padding: 10px 20px;
  border-radius: 20px;
  display: flex;
  justify-content: center;
  align-items: center;
  margin: 20px 0px;
  box-shadow: var(--shadow);
  font-size: 12px;
}
.action-button:first-child {
  background-color: var(--black);
  color: white;
  margin-right: 5px;
}
.action-button:last-child {
  background-color: white;
}
.action-button:last-child > i {
  margin-right: 5px;
  color: #ff6347;
}

.songs-song,
.songs-song__info {
  display: flex;
  justify-content: space-between;
  align-items: center;
}

.songs-song {
  padding: 5px;
  margin-bottom: 20px;
  border-radius: 10px;
  box-shadow: var(--shadow);
}

.songs-song__info img {
  width: 50px;
  height: 50px;
  border-radius: 5px;
  margin-right: 10px;
}

h3 {
  margin-top: 8px;
  font-size: 14px;
  font-weight: 600;
}

li i {
  color: var(--icon-gray);
  margin-right: 5px;
}
.playing-song {
  left: 0px;
  right: 0px;
  width: 90%;
  margin-left: auto;
  margin-right: auto;
  padding: 10px 20px;
  border-radius: 25px;
  background-color: var(--black);
  color: white;
  box-shadow: var(--black-shadow);
  display: flex;
  justify-content: space-between;
  align-items: center;
  position: absolute;
}
.playing-song__info {
  display: flex;
  flex-direction: column;
}
.playing-song__singer {
  font-size: 10px;
  margin-bottom: 5px;
}
.playing-song__title {
  font-size: 12px;
  font-weight: 600;
}
.playing-song__btns {
  display: flex;
  align-items: center;
  justify-content: space-between;
}
.playing-song__btns i {
  font-size: 12px;
}
.playing-song__btns i:nth-child(2) {
  margin: 0px 20px;
}
.main-image,
.main-info {
  display: flex;
  justify-content: center;
  align-items: center;
}
.main-image > img {
  width: 180px;
  height: 180px;
  margin-top: 50px;
  margin-bottom: 40px;
  border-radius: 20px;
  box-shadow: 8px 9px 18px -6px #b39677;
}
.main-info {
  flex-direction: column;
}
.main-title {
  color: black;
  font-size: 18px;
  font-weight: 900;
  margin-bottom: 15px;
}
.main-singer {
  font-size: 12px;
  font-weight: 600;
  color: var(--gray);
  margin-bottom: 35px;
}
.playing-time {
  display: flex;
  justify-content: space-between;
  align-items: center;
}
.playing-time span {
  font-size: 10px;
  color: var(--gray);
}
.playing-bar {
  display: flex;
  align-items: center;
  margin-top: 20px;
  position: relative;
}
.playing-bar__past,
.playing-bar__rest {
  width: 35%;
  height: 4px;
  border-radius: 2px;
  background-color: var(--black);
  position: absolute;
}
.playing-bar__now {
  width: 8px;
  height: 8px;
  border-radius: 4px;
  background-color: var(--black);
  left: 33%;
  position: absolute;
}
.playing-bar__rest {
  width: 65%;
  background-color: var(--icon-gray);
  left: 35%;
}
.playing-controller {
  display: flex;
  justify-content: space-between;
  align-items: center;
  margin-top: 70px;
}
.playing-controller i:nth-child(1),
.playing-controller i:nth-child(5) {
  font-size: 15px;
  color: var(--icon-gray);
}
.playing-controller i:nth-child(2),
.playing-controller i:nth-child(4) {
  font-size: 20px;
  color: var(--black);
}
.playing-controller__circle {
  width: 50px;
  height: 50px;
  border-radius: 50%;
  background-color: var(--black);
  box-shadow: var(--black-shadow);
  display: flex;
  justify-content: center;
  align-items: center;
  position: relative;
}
.playing-controller__circle > i {
  color: white !important;
  font-size: 20px;
  position: absolute;
}
```

variable.css

```css
:root {
  --gray: rgba(0, 0, 0, 0.5);
  --icon-gray: rgba(0, 0, 0, 0.2);
  --shadow: 3px 2px 11px -1px rgba(225, 225, 225, 0.83);
  --black-shadow: 8px 9px 9px -9px #4a4a4a;
  --black: #3f3e3d;
}
```

```html
<!DOCTYPE html>
<html>
  <head>
    <meta charset="utf-8">
    <meta name="viewport" content="width=device-width">
    <title>You Are Awesome!</title>
    <link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/reset-css@5.0.1/reset.min.css">
    <link rel="stylesheet" href="https://cdn.jsdelivr.net/gh/FortAwesome/Font-Awesome@5.14.0/css/all.min.css">
    <link rel="stylesheet" href="style.css">
  </head>
  <body>
    <section class="screen">
      <header class="screen-header">
        <i class="fas fa-arrow-left"></i>
        <i class="fas fa-search"></i>
      </header>
      <div class="main-song__info">
        <img src="iu.PNG">
        <h2>아이유(IU)</h2>
        <h5>팝, 댄스, 어쿠스틱</h5>
      </div>
      <div class="main-song__action">
        <span class="action-button">Shuffle</span>
        <span class="action-button"><i class="fas fa-heart"></i>8,380,000</span>
      </div>
      <ul class="songs-list">
        <li class="songs-song">
          <div class="songs-song__info">
            <img src="https://i.namu.wiki/i/8p7Jv0SF79drleBQPJuvHLZJSyYtETLKLoAlhs08O37oS34fvKlgYduS0WqItkvT-UE4rcQw0bzlvaYvZgbn1Ht6EmIvh3-iVsjBBe9dk7HBjTFmbz2_8bMDXb0SAYWFzkAcfGBYPz_PWHIjJgGuIA.webp">
            <div class="songs-song__text">
              <h5>아이유(IU)</h5>
              <h3>에필로그(Epilogue)</h3></h3>
            </div>
          </div>
          <i class="fas fa-ellipsis-v"></i>
        </li>
        <li class="songs-song">
          <div class="songs-song__info">
            <img src="https://i.namu.wiki/i/2TZWdUelg6jnGYMLISTdNFFKdSKJDUqA63Uf_gi4N21dR3aO2iy01n1Dkg651v6crHoZtBySAFpiQae4VULevCFTDeF9O40BKM9Azw4JSTFyX3pqITCIvui4tz_y4nmLNXJCe03pxoQCbIAcW_z4kw.webp">
            <div class="songs-song__text">
              <h5>아이유(IU)</h5>
              <h3>팔레트(Palette)</h3>
            </div>
          </div>
          <i class="fas fa-ellipsis-v"></i>
        </li>
        <li class="songs-song">
          <div class="songs-song__info">
            <img src="https://i.namu.wiki/i/IBfnF9n1Ovk7QR9U0as8ASirP2Yxf2eUJMIYDmdSHZyU6gC86_JgcrUPYbo346vhtiKHthdy77oEJhvwZ_3trkOWEKtseSjX7YDEv2VTs3OJ5fTAepP2eCNuPnb1SyqkdDaZG6lm4AmLhko1um33Rg.jpg">
            <div class="songs-song__text">
              <h5>아이유(IU)</h5>
              <h3>strawberry moon</h3>
            </div>
          </div>
          <i class="fas fa-ellipsis-v"></i>
        </li>
        <li class="songs-song">
          <div class="songs-song__info">
            <img src="https://i.namu.wiki/i/8p7Jv0SF79drleBQPJuvHLZJSyYtETLKLoAlhs08O37oS34fvKlgYduS0WqItkvT-UE4rcQw0bzlvaYvZgbn1Ht6EmIvh3-iVsjBBe9dk7HBjTFmbz2_8bMDXb0SAYWFzkAcfGBYPz_PWHIjJgGuIA.webp">
            <div class="songs-song__text">
              <h5>아이유(IU)</h5>
              <h3>빈 컵(Empty Cup))</h3>
            </div>
          </div>
          <i class="fas fa-ellipsis-v"></i>
        </li>
      </ul>
      <div class="playing-song">
        <div class="playing-song__info">
          <span class="playing-song__singer">아이유(IU)</span>
          <span class="playing-song__title">금요일에 만나요(Friday)</span>
        </div>
        <div class="playing-song__btns">
          <i class="fas fa-step-backward"></i>
          <i class="fas fa-pause"></i>
          <i class="fas fa-step-forward"></i>
        </div>
      </div>
    </section>
    <section class="screen">
      <header class="screen-header">
        <i class="fas fa-arrow-left"></i>
        <i class="fas fa-ellipsis-v"></i>
      </header>
      <div class="main-image">
        <img src="https://i.namu.wiki/i/dFnONRP5muYCziucE9_oyArBCRqU4AW2NUUs0JsR0h2O29U_v8KiXqJ6lmSRACVIcPvDa3IMCZ4NwSYmkRR7GfPQxr6j5WrQd9NAzxr9LyholZMl2mGqYHicZO9W5WFvTCzx8zHg3ex-30_49lqCCA.webp">
      </div>
      <div class="main-info">
        <span class="main-title">금요일에 만나요(Friday)</span>
        <span class="main-singer">아이유(IU)</span>
      </div>
      <div class="playing-time">
        <span class="playing-time__now">1:20</span>
        <span class="playing-time__fin">3:38</span>
      </div>
      <div class="playing-bar">
        <div class="playing-bar__past"></div>
        <div class="playing-bar__now"></div>
        <div class="playing-bar__rest"></div>
      </div>
      <div class="playing-controller">
        <i class="fas fa-retweet"></i>
        <i class="fas fa-step-backward"></i>
        <div class="playing-controller__circle">
          <i class="fas fa-play"></i>
        </div>
        <i class="fas fa-step-forward"></i>
        <i class="fas fa-random"></i>
      </div>
    </section>
  </body>
</html>
```
