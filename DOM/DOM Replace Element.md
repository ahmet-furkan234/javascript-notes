
Bu işlemle sayfadaki bir elementi **başka bir elementle değiştirebilirsin.**

---

## ✅ Yöntem: `parent.replaceChild(newElement, oldElement)`

Bir ebeveynin içindeki eski öğeyi, yeni öğe ile değiştirir.

---

## 📌 Örnek:



```html
<div id="kapsayici">   
	<p id="eski">Bu eski paragraf</p> 
</div>
```



```js
const eskiP = document.getElementById("eski"); 
const kapsayici = document.getElementById("kapsayici");  

// Yeni paragraf oluştur 
const yeniP = document.createElement("p"); 
yeniP.textContent = "Bu yeni paragraf.";  
// Eskiyi yeniyle değiştir 

kapsayici.replaceChild(yeniP, eskiP);
```

> 🔄 `replaceChild(yeni, eski)` → Unutma: sıralama bu şekilde!

---

## 🧠 Notlar:

- `replaceChild()` sadece **ebeveyn (parent)** üzerinden çalışır.
- Sadece **tek bir elementi** değiştirir.
- Eski eleman DOM'dan kaldırılır, yerine yeni gelen DOM'a eklenmiş olur.

---

## 🧪 Alternatif (Modern Yöntem): `element.outerHTML`

Eğer çok küçük bir değişim yapmak istiyorsan:

```js
document.getElementById("eski").outerHTML = "<p>Yeni içerik</p>";
```

>⚠️ Bu yöntem yeni elementi **string olarak** ekler, yeni element DOM içinde yeni sayılır ama olay dinleyicileri kaybolabilir.

---

## 📦 Mini Örnek: Butona Tıklayınca Element Değişsin

```html
<div id="kutu">Eski içerik</div>
<button id="degistirBtn">Değiştir</button>
```

```js
document.getElementById("degistirBtn").addEventListener("click", function () {
  const eskiDiv = document.getElementById("kutu");
  const yeniDiv = document.createElement("div");
  yeniDiv.textContent = "Yeni içerik";
  eskiDiv.parentElement.replaceChild(yeniDiv, eskiDiv);
});
```

