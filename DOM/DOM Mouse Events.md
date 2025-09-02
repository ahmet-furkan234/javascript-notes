
Fareyle yapılan işlemleri JavaScript ile algılayıp tepki verebiliriz.

---

## ✅ En Sık Kullanılan Fare Olayları

|Olay|Açıklama|
|---|---|
|`click`|Tek tıklama|
|`dblclick`|Çift tıklama|
|`mousedown`|Mouse tuşuna basıldığı an|
|`mouseup`|Mouse tuşu bırakıldığında|
|`mouseenter`|Elementin üzerine girildiğinde (tek seferlik)|
|`mouseleave`|Elementten çıkıldığında|
|`mouseover`|Elementin üzerine girildiğinde (alt elementlerde de tetiklenir)|
|`mouseout`|Elementten çıkıldığında|
|`mousemove`|Fare hareket ettikçe|
|`contextmenu`|Sağ tıklama|

---

## 📌 Örnek 1: `click`, `dblclick`, `contextmenu`


```html
<button id="btn">Tıkla</button>
```



```js
const btn = document.getElementById("btn");  
btn.addEventListener("click", () => {
	console.log("Tek tıklama"); 
});  
	
btn.addEventListener("dblclick", () => {   
	console.log("Çift tıklama"); 
});  

btn.addEventListener("contextmenu", (e) => {   
	e.preventDefault();   
	console.log("Sağ tıklama engellendi"); 
});
```

---

## 📌 Örnek 2: `mouseenter` vs `mouseover`

```html
<div id="kutu" style="width: 200px; height: 200px; background: lightblue;">
  <p>Üzerine gel</p>
</div>
```

```js
const kutu = document.getElementById("kutu");

kutu.addEventListener("mouseenter", () => {
  console.log("mouseenter: Sadece kutuya ilk girişte çalışır");
});

kutu.addEventListener("mouseover", () => {
  console.log("mouseover: Alt elementlere her girişte de çalışır");
});
```


---

## 📌 Örnek 3: `mousemove` ile imleç takibi

```html
<div id="takip" style="width:300px;height:150px;border:1px solid black;"></div>
<p id="koordinat"></p>
```

```js
const takip = document.getElementById("takip");
const koordinat = document.getElementById("koordinat");

takip.addEventListener("mousemove", function (e) {
  koordinat.textContent = `X: ${e.offsetX}, Y: ${e.offsetY}`;
});
```

---

---

## 🎯 `MouseEvent` Özellikleri

|Özellik|Açıklama|
|---|---|
|`e.clientX`|Sayfa içindeki X konumu|
|`e.clientY`|Sayfa içindeki Y konumu|
|`e.offsetX`|Hedef element içindeki X konumu|
|`e.offsetY`|Hedef element içindeki Y konumu|
|`e.button`|Hangi mouse tuşu (0: sol, 1: orta, 2: sağ)|

---

## 🔐 Mini Örnek: Sağ tıklamayı engelle



```js
document.addEventListener("contextmenu", function (e) {   
	e.preventDefault();   
	alert("Sağ tıklama devre dışı!"); 
});
```

---

