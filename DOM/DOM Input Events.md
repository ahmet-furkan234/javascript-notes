
Bu olaylar, kullanıcı form alanlarıyla (input, textarea, select vs.) etkileşime geçtiğinde tetiklenir.

---

## ✅ Sık Kullanılan Input/Form Olayları

|Olay Adı|Açıklama|
|---|---|
|`input`|Kullanıcı yazı alanında her karakter değiştirdiğinde tetiklenir|
|`change`|Değer değiştirildikten sonra ve odaktan çıkınca çalışır|
|`focus`|Form alanı odaklandığında|
|`blur`|Form alanı odak dışına çıktığında|
|`submit`|Form gönderilmeye çalışıldığında|

---

## 📌 `input` vs `change`

### `input`: Her tuşta tetiklenir

### `change`: Odak değiştirildiğinde tetiklenir


```html
<input type="text" id="ad" placeholder="Adınızı girin">
```


```js
const ad = document.getElementById("ad");  
ad.addEventListener("input", () => {   
	console.log("Her yazışta tetiklenir:", ad.value);
});  

ad.addEventListener("change", () => {   
	console.log("Odaktan çıkınca tetiklenir:", ad.value); 
});
```

---
## 📌 `focus` ve `blur` olayları


```js
ad.addEventListener("focus", () => {   
	console.log("Odaklandı"); 
});  

ad.addEventListener("blur", () => {   
	console.log("Odaktan çıktı"); 
});
```

---

## 📌 `submit` Olayı (Form gönderimini kontrol etme)


```html
<form id="form">   
	<input type="text" placeholder="Adınızı girin" required>   
	<button type="submit">Gönder</button> 
</form>
```


```js
const form = document.getElementById("form"); 
form.addEventListener("submit", function (e) {   
	e.preventDefault(); // Sayfanın yenilenmesini engeller   
	console.log("Form gönderildi!"); 
	});
```

---

## 🧪 Örnek: Canlı yazılan değeri göster


```html
<input type="text" id="mesaj" placeholder="Bir şeyler yaz..."> 
<p id="gosterge"></p>
```


```js
const mesaj = document.getElementById("mesaj"); 
const gosterge = document.getElementById("gosterge");  
mesaj.addEventListener("input", () => {   
	gosterge.textContent = "Yazdığınız: " + mesaj.value; 
});
```

---

## 🧠 Ek Bilgi

- `textarea` için de tüm bu olaylar geçerlidir.
- `select` (açılır menü) için genellikle `change` kullanılır.
