
Bu, standart HTML5 doğrulama yetmezse kendi doğrulama kurallarımızı yazmamızı sağlar.

---

## 1. Neden Custom Validation?

- HTML5 `pattern` veya `type` ile karşılanmayan özel kurallar için
- Örneğin: Şifre karmaşıklığı, kullanıcı adı benzersizliği, özel formatlar vb.
- Hata mesajını kendimiz kontrol etmek istediğimizde

---

## 2. `setCustomValidity()` ile özel hata mesajı


```html
<form id="form2">   
	<input type="text" id="username" placeholder="Kullanıcı adı" required />   
	<button type="submit">Gönder</button> 
</form>`
```


```js
const username = document.getElementById("username");
const form2 = document.getElementById("form2");

username.addEventListener("input", () => {
  if (username.value.length < 5) {
    username.setCustomValidity("Kullanıcı adı en az 5 karakter olmalı.");
  } else {
    username.setCustomValidity(""); // Hata yoksa mesajı temizle
  }
});

form2.addEventListener("submit", (e) => {
  if (!form2.checkValidity()) {
    e.preventDefault();
    alert("Formda hata var, düzeltin.");
  } else {
    alert("Form başarıyla gönderildi!");
  }
});
```

---

## 3. Örnek: Şifre doğrulaması

```html
<form id="form3">
  <input type="password" id="password" placeholder="Şifre" required />
  <input type="password" id="confirmPassword" placeholder="Şifre tekrar" required />
  <button type="submit">Gönder</button>
</form>
```

```js
const password = document.getElementById("password");
const confirmPassword = document.getElementById("confirmPassword");
const form3 = document.getElementById("form3");

confirmPassword.addEventListener("input", () => {
  if (confirmPassword.value !== password.value) {
    confirmPassword.setCustomValidity("Şifreler uyuşmuyor.");
  } else {
    confirmPassword.setCustomValidity("");
  }
});

form3.addEventListener("submit", (e) => {
  if (!form3.checkValidity()) {
    e.preventDefault();
    alert("Formda hata var!");
  } else {
    alert("Form gönderildi!");
  }
});
```

---

## 4. `reportValidity()` ile hata göstermek

```js
form3.addEventListener("submit", (e) => {
  if (!form3.checkValidity()) {
    e.preventDefault();
    form3.reportValidity(); // Formdaki hataları otomatik gösterir
  }
});
```

---
## 5. Özet

- `setCustomValidity()` ile özel hata mesajı tanımlanır
- Mesaj boşsa (`""`) form alanı geçerli sayılır
- `checkValidity()` ile form doğruluğu kontrol edilir
- `reportValidity()` ile otomatik hata mesajları gösterilebilir

---

