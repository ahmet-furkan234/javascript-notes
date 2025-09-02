
---
## 1. Event Bubbling (Olay Kabarcıklanması)

### Nedir?

- DOM’da bir elementte tetiklenen olay (event), önce o elementte işlenir,
- Sonra olay **bubbling** olarak adlandırılan mekanizma ile sırayla üst elementlere (parent) doğru yayılır.
- Bu sayede, parent elementler de çocuklarında gerçekleşen olayları dinleyebilir.

### Neden?

- DOM yapısı hiyerarşiktir ve olayların tek tek her element için dinlenmesi verimsiz olur.
- Bubbling olayı sayesinde olaylar yukarı doğru taşınabilir, böylece ortak bir üst elemana olay dinleyici koyulabilir.

---

### Örnek:


```html
<div id="container" style="padding:20px; background:#eee;">   
	<button id="btn">Tıkla</button> 
</div>
```


```js
document.getElementById("btn").addEventListener("click", () => {
  console.log("Button'a tıklandı");
});

document.getElementById("container").addEventListener("click", () => {
  console.log("Container'a tıklandı");
});
```

**Ne olur?**  
`btn` tıklanınca önce “Button'a tıklandı”, sonra “Container'a tıklandı” yazısı konsola gelir. Çünkü olay `btn` elementinde başlar, sonra üst container'a yayılır.

---

### Bubbling Süreci

1. Event `btn` elementinde başlar.
2. Event, üst container’a doğru yayılır (bubbling).
3. Container’daki event listener da tetiklenir.

---

## 2. Event Delegation (Olay Delege Etme)

### Nedir?

- Çok sayıda alt element için tek tek event listener eklemek yerine,
- Ortak bir üst elemente tek bir event listener ekleyerek,
- Event bubbling sayesinde hangi alt elemente tıklandığını kontrol edip işlemi yapmak.

### Avantajları

- Performans artar (çok sayıda dinleyici olmaz)
- Dinamik olarak eklenen elemanlar için ekstra işlem gerekmez
- Kod daha temiz ve yönetilebilir olur

---
### Örnek:


```html
<ul id="list">
  <li>Elma</li>
  <li>Armut</li>
  <li>Muz</li>
</ul>
```


```js
const list = document.getElementById("list");

list.addEventListener("click", (event) => {
  if (event.target.tagName === "LI") {
    alert(event.target.textContent + " tıklandı");
  }
});
```

**Ne olur?**  
Her bir `<li>` öğesine tıklanınca, ayrı ayrı dinleyici yok ama üst `ul`’de tek listener var.  
`click` olayını yakalar ve hangi `li`’nin tıklandığını `event.target` ile bulur.

---

## 3. Event Bubbling ve Delegation Birlikte Nasıl Çalışır?

- Event bubbling olmadan delegation mümkün değildir.
- Çünkü event bubbling olayın hedef elementten üst parentlara ulaşmasını sağlar.
- Delegation, bubbling’den yararlanarak olayları tek noktada yönetir.

---

## 4. Bubbling’ın İptali

Bazen bubbling’i durdurmak gerekebilir:

```js
btn.addEventListener("click", (e) => {   
	e.stopPropagation();  // Olayın üst elementlere yayılmasını engeller 
});
```

Bu durumda, üst `container` dinleyicisi tetiklenmez.

---

## 5. Daha Gelişmiş Örnek — Dinamik Elemanlar

```html
<ul id="list">
  <li>Elma</li>
  <li>Armut</li>
</ul>
<button id="add">Listeye Ekle</button>
```

```js
const list = document.getElementById("list");
const addBtn = document.getElementById("add");

list.addEventListener("click", (e) => {
  if (e.target.tagName === "LI") {
    alert(e.target.textContent + " tıklandı");
  }
});

addBtn.addEventListener("click", () => {
  const li = document.createElement("li");
  li.textContent = "Yeni Meyve";
  list.appendChild(li);
});
```

Dinamik olarak yeni `<li>` eklendiğinde ekstra event listener eklemeye gerek yok, delegation sayesinde tıklamaları yakalar.

---

## 6. Özet Tablosu

|Konu|Açıklama|
|---|---|
|Event Bubbling|Olay hedef elementten başlayıp yukarı parent’a yayılır|
|Event Delegation|Üst elementte tek listener ile alt elementlerin eventlerini yönetmek|
|Birlikte Kullanım|Delegation, bubbling sayesinde çalışır ve performans sağlar|
|stopPropagation()|Bubbling’i durdurur, delegation’ın işlevini keser|
