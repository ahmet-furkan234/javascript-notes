
Kullanıcının klavye ile yaptığı işlemleri algılayabilir ve tepki verebiliriz.

---

## ✅ Temel Olaylar

| Olay Adı   | Ne Zaman Çalışır?                                                  |
| ---------- | ------------------------------------------------------------------ |
| `keydown`  | Klavye tuşuna basıldığı anda (basılı tutulduğunda sürekli çalışır) |
| `keyup`    | Klavye tuşu bırakıldığında                                         |
| `keypress` | ![[Pasted image 20250625104852.png]]                               |
> ✅ Modern uygulamalarda `keydown` ve `keyup` kullanılır.


---

## 📌 Örnek 1: Tuşa basma ve bırakma

```html
<input type="text" id="giris" placeholder="Bir şeyler yaz...">
```


```js
const giris = document.getElementById("giris");

giris.addEventListener("keydown", function () {
  console.log("Bir tuşa basıldı.");
});

giris.addEventListener("keyup", function () {
  console.log("Tuş bırakıldı.");
});
```

---

## 📌 Örnek 2: Basılan tuşu öğrenmek

```js
giris.addEventListener("keydown", function (e) {
  console.log("Basılan tuş:", e.key);
  console.log("Kod:", e.code);
});
```

|Özellik|Açıklama|
|---|---|
|`e.key`|Kullanıcının bastığı karakter (`a`, `Enter`, `Shift`, `1` vs.)|
|`e.code`|Klavyedeki fiziksel tuşun adı (`KeyA`, `Digit1`, `ArrowDown` vs.)|

---

## 📌 Örnek 3: Enter tuşuyla formu kontrol etme

```html
<input type="text" id="isim" placeholder="Adınızı yazın">
```

```js
document.getElementById("isim").addEventListener("keydown", function (e) {
  if (e.key === "Enter") {
    alert("Enter tuşuna bastınız!");
  }
});
```

---

## 📌 Örnek 4: Ok tuşları ile hareket ettirme



```html
<div id="kutu" style="width:50px;height:50px;background:red;position:relative;"></div>
```


```js
const kutu = document.getElementById("kutu"); 
let x = 0;  document.addEventListener("keydown", function (e) {   
	if (e.key === "ArrowRight") 
	{     
		x += 10;     
		kutu.style.left = x + "px";   
	} 
});
```

---

## 🧠 İpucu: Tuşları büyük/küçük harf duyarlı yakalamak için `e.key.toLowerCase()`

---

```js
document.addEventListener("keydown", function (e) {
  if (e.ctrlKey && e.key === "s") {
    e.preventDefault();
    alert("Ctrl + S engellendi.");
  }
});
```

---

## ✔️ Özet

- `keydown`: Tuşa basıldığı anda çalışır.
- `keyup`: Tuş bırakıldığında çalışır.
- `e.key`: Basılan tuşun değerini verir.
- `e.code`: Fiziksel tuşun adını verir.

---

