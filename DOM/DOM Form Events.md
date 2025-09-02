
Formlarla çalışırken kullanabileceğimiz olaylar sayesinde kullanıcı girişlerini kontrol edebilir, doğrulama yapabilir ve veri göndermeyi yönetebiliriz.

---

## ✅ Sık Kullanılan Form Olayları

| Olay     | Ne Zaman Tetiklenir?                                 |
| -------- | ---------------------------------------------------- |
| `submit` | Form gönderilmek istendiğinde                        |
| `input`  | Girdi alanında her karakter değiştiğinde             |
| `change` | Değişiklik tamamlandıktan sonra (ve odaktan çıkınca) |
| `focus`  | Input/textarea odaklandığında                        |
| `blur`   | Input/textarea odaktan çıktığında                    |
| `reset`  | Form sıfırlandığında (`form.reset()`)                |

---

## 📌 Örnek 1: `submit` olayı


```html
<form id="kayitFormu">
  <input type="text" name="ad" placeholder="Adınız" required />
  <button type="submit">Gönder</button>
</form>
```

```js
const form = document.getElementById("kayitFormu");

form.addEventListener("submit", function (e) {
  e.preventDefault(); // Sayfa yenilenmesini engeller
  const formData = new FormData(form);
  console.log("Form gönderiliyor:", formData.get("ad"));
});
```


---

## 📌 Örnek 2: `input` ve `change` farkı

```html
<input type="text" id="email" placeholder="Email girin" />
```

```js
const email = document.getElementById("email");

email.addEventListener("input", () => {
  console.log("Anlık yazım:", email.value);
});

email.addEventListener("change", () => {
  console.log("Yazma tamamlandı, odaktan çıkıldı:", email.value);
});
```

---

## 📌 Örnek 3: `focus` ve `blur` olayları

```js
email.addEventListener("focus", () => {
  console.log("Email alanına odaklanıldı");
});

email.addEventListener("blur", () => {
  console.log("Email alanından çıkıldı");
});
```

---


## 📌 Örnek 4: `reset` olayı

```html
<form id="form2">
  <input type="text" name="ad">
  <button type="reset">Sıfırla</button>
</form>
```


```js
document.getElementById("form2").addEventListener("reset", () => {
  console.log("Form sıfırlandı");
});
```

---

## 📌 Ekstra: Form verisini almak

```js
const formData = new FormData(form);
for (const [key, value] of formData.entries()) {
  console.log(`${key}: ${value}`);
}
```

---

## 🧠 Hatırlatma

- `submit` olayı sadece `<form>` elementinde çalışır.
- `input`, `change`, `focus`, `blur` olayları tüm form elemanlarında çalışır.
- `required`, `minlength`, `pattern` gibi HTML validasyonları, form gönderilmeden önce kontrol edilir.