
Kullanıcıların form verilerini doğru ve eksiksiz girmesini sağlamak için hem HTML hem JavaScript ile form doğrulama yapılabilir.

---

## 1. HTML5 ile Basit Doğrulama

HTML form elementlerinde hazır bazı doğrulama özellikleri var:

|Özellik|Açıklama|
|---|---|
|`required`|Boş bırakılmasını engeller|
|`type="email"`|Email formatında olmalı|
|`minlength`|Minimum karakter sayısı|
|`maxlength`|Maksimum karakter sayısı|
|`pattern`|Regex (düzenli ifade) ile kontrol|
|`min`, `max`|Sayısal değer aralığı|

---

### Örnek:

```html
<form id="form1">   
	<input type="text" name="ad" placeholder="Adınız" required minlength="3" />   
	<input type="email" name="email" placeholder="Email" required />   
	<button type="submit">Gönder</button> 
</form>
```

---

## 2. Formun Doğrulama Durumunu Kontrol Etme

JavaScript ile formun geçerli olup olmadığını kontrol etmek için:

```js
const form = document.getElementById("form1");

form.addEventListener("submit", function(e) {
  if (!form.checkValidity()) {
    e.preventDefault(); // Gönderme işlemini durdurur
    alert("Lütfen formu doğru doldurun.");
  }
});
```

---
## 3. Özel Hata Mesajları Gösterme


```js
const ad = form.elements["ad"];  
ad.addEventListener("input", () => {   
	if (ad.validity.tooShort) 
	{     
		ad.setCustomValidity("Adınız en az 3 karakter olmalı.");   
	} 
	else 
	{     
	ad.setCustomValidity(""); // Hata mesajını temizle   
	} 
});
```

---

## 4. JavaScript ile Manuel Doğrulama

Formu tamamen JS ile doğrulamak istersen:

```js
form.addEventListener("submit", (e) => {
  e.preventDefault();
  const ad = form.elements["ad"].value.trim();
  const email = form.elements["email"].value.trim();

  if (ad.length < 3) {
    alert("Ad en az 3 karakter olmalı.");
    return;
  }

  const emailPattern = /^[^\s@]+@[^\s@]+\.[^\s@]+$/;
  if (!emailPattern.test(email)) {
    alert("Geçerli bir email girin.");
    return;
  }

  alert("Form başarıyla gönderildi!");
  form.reset();
});
```

---

## 5. Stil ile Hata Vurgulama

```css
input:invalid {
  border: 2px solid red;
}

input:valid {
  border: 2px solid green;
}

```

---

## Özet

- HTML5 ile kolayca doğrulama yapabilirsin (`required`, `pattern`, `type` vs.)
- `checkValidity()` formun doğruluğunu kontrol eder
- `setCustomValidity()` ile özel hata mesajı verilir
- JS ile formu manuel doğrulayıp kullanıcıya geri bildirim verebilirsin

---

