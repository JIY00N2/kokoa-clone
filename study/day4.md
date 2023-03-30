### 2023.03.30 Review

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
