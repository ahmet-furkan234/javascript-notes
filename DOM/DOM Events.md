
Kullanıcılarla etkileşimi sağlamak için olayları kullanırız: tıklama, yazı yazma, form gönderme, fare hareketi vb.

---

## 🎯 Temel Kavram

> JavaScript, HTML elementlerine kullanıcı etkileşimi olduğunda tepki verebilir.

---

## ✅ Olayları Ekleme Yöntemleri

### 1. **HTML içinden (tavsiye edilmez)**


```html
<button onclick="alert('Tıklandı!')">Tıkla</button>
```

### 2. **Elemente doğrudan `onclick` atamak (az tercih edilir)**


```js
const btn = document.querySelector("button"); 
btn.onclick = function () {   
	alert("Tıklandı!"); 
};
```

### 3. ✅ **`addEventListener` ile olay eklemek (En doğru yol)**


```js
const btn = document.querySelector("button");  
btn.addEventListener("click", function () {   
	alert("Tıklandı!"); 
});
```

---

## 📌 Sık Kullanılan DOM Olayları

|Olay Adı|Açıklama|
|---|---|
|`click`|Tıklama|
|`dblclick`|Çift tıklama|
|`mouseover`|Üzerine gelme|
|`mouseout`|Üzerinden çıkma|
|`keydown`|Klavyeye tuş basma|
|`keyup`|Tuşu bırakma|
|`input`|Form alanında yazı değişimi|
|`change`|Seçim/değer değişimi (select, checkbox, vs.)|
|`submit`|Form gönderimi|-

---

## 🧪 Örnek: Fareyle üzerine gelince yazı değiştir


```html
<p id="metin">Üzerine gel</p>
```



```js
const p = document.getElementById("metin");  
p.addEventListener("mouseover", function () {  
	p.textContent = "Merhaba 👋"; 
});

p.addEventListener("mouseout", function () {
	p.textContent = "Üzerine gel"; 
});
```

## 🧪 Örnek: Klavyede yazı yazıldıkça göster


```html
<input type="text" id="ad" placeholder="Adınızı yazın"> 
<p id="goster"></p>
```


```js
const input = document.getElementById("ad"); 
const goster = document.getElementById("goster");  
input.addEventListener("input", function () {
	goster.textContent = "Girdiğiniz: " + input.value; 
});
```

---

## 💡 Ekstra Bilgi: `event` objesi

```js
btn.addEventListener("click", function (e) {
  console.log("Tıklama oldu:", e);
});
```

>`e.target` → Olayın gerçekleştiği elementi verir.  
>`e.preventDefault()` → Varsayılan davranışı engeller (form gönderme gibi).


---

## 🚦 Örnek: Form gönderimini engelle

```html
<form id="form">
  <input type="text" required>
  <button>Gönder</button>
</form>
```

```js
document.getElementById("form").addEventListener("submit", function (e) {
  e.preventDefault();
  alert("Form gönderimi engellendi!");
});
```

---




