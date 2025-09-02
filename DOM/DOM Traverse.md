
Bu konu sayesinde bir öğenin **ebeveynine, çocuğuna veya kardeşine** JavaScript ile kolayca ulaşabilirsin.

---

# 🔍 DOM Traverse (Gezinme)

## 📌 1. `parentNode` / `parentElement`

Bir öğenin **ebeveyn (üst)** elemanını döner.

```html
<div id="kapsayici">
  <p id="metin">Merhaba</p>
</div>
```

```js
const p = document.getElementById("metin");

console.log(p.parentNode);    // <div id="kapsayici">
console.log(p.parentElement); // Aynı sonucu verir
```

---

## 📌 2. `childNodes` vs `children`

Bir öğenin **alt (çocuk) elemanlarını** verir.

```html
<ul id="liste">
  <li>Elma</li>
  <li>Armut</li>
</ul>
```

```js
const ul = document.getElementById("liste");

console.log(ul.childNodes); // Tüm düğümler: li + boşluk + satır sonu (NodeList)
console.log(ul.children);   // Sadece HTML elemanları: <li>, <li> (HTMLCollection)
```

> ✅ Genellikle `children` kullanılır, çünkü `childNodes` metin boşluklarını da alır.

---


## 📌 3. `firstChild` vs `firstElementChild`

İlk çocuğa erişmek için:

```js
ul.firstChild          // Boşluk olabilir ❌
ul.firstElementChild   // <li> ✅
```

Benzeri şekilde:

- `lastChild`
- `lastElementChild`

---

## 📌 4. `nextSibling` / `nextElementSibling`

Bir öğenin **bir sonraki kardeşi**:

```html
<div>
  <p id="bir">Bir</p>
  <p>İki</p>
</div>
```

```js
const p1 = document.getElementById("bir");

console.log(p1.nextSibling);        // Boşluk veya satır ❌
console.log(p1.nextElementSibling); // <p>İki</p> ✅
```

Aynı şekilde:

- `previousSibling`
- `previousElementSibling`

---
## 🧠 Özet Tablo

| Özellik                  | Açıklama                   |
| ------------------------ | -------------------------- |
| `parentNode`             | Üst düğüm                  |
| `childNodes`             | Tüm çocuklar (metin dahil) |
| `children`               | Yalnızca öğe çocukları     |
| `firstChild`             | İlk çocuk (her türden)     |
| `firstElementChild`      | İlk öğe çocuğu             |
| `lastChild`              | Son çocuk                  |
| `lastElementChild`       | Son öğe çocuğu             |
| `nextSibling`            | Sonraki kardeş düğüm       |
| `nextElementSibling`     | Sonraki öğe kardeş         |
| `previousSibling`        | Önceki kardeş düğüm        |
| `previousElementSibling` | Önceki öğe kardeş          |
