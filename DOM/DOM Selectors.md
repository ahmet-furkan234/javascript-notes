
DOM seçicileri sayesinde HTML sayfasındaki öğelere JavaScript ile ulaşabilir ve onlar üzerinde işlem yapabilirsin.

---

## ✳️ 1. `getElementById()`

**ID değeriyle tek bir öğe seçer.**

```html
<p id="mesaj">Merhaba</p>
```

```js
const p = document.getElementById("mesaj");
console.log(p.textContent); // Merhaba
```

---

## ✳️ 2. `getElementsByClassName()`

**Class adıyla birden fazla öğeyi seçer. HTMLCollection döner.**

```html
<div class="kutu">1</div>
<div class="kutu">2</div>
```

```js
const kutular = document.getElementsByClassName("kutu");
console.log(kutular.length); // 2
```

---

## ✳️ 3. `getElementsByTagName()`

**Etiket adıyla (div, p, h1, vs.) öğeleri seçer. HTMLCollection döner.**

```html
<p>Bir</p>
<p>İki</p>
```

```js
const paragraflar = document.getElementsByTagName("p");
console.log(paragraflar[1].textContent); // İki
```

---

## ✳️ 4. `querySelector()`

**CSS seçici ile ilk eşleşen öğeyi döner.**

```html
<p class="metin">Merhaba</p>
```

```js
const p = document.querySelector(".metin");
```

- ID seçmek: `#id`
- Class: `.class`
- Etiket: `div`, `p`, `h1`
- İç içe: `div .btn`, `ul li:first-child` vs.

---

## ✳️ 5. `querySelectorAll()`

**CSS seçiciyle eşleşen tüm öğeleri NodeList olarak döner.**

```html
<ul>
  <li>Elma</li>
  <li>Armut</li>
</ul>
```

```js
const liste = document.querySelectorAll("li");

liste.forEach(item => console.log(item.textContent));
```

---

## 🧠 Notlar

|Seçici|Dönüş Türü|Çoklu Seçim?|
|---|---|---|
|`getElementById`|Tek element (null da olabilir)|❌|
|`getElementsByClassName`|HTMLCollection|✅|
|`getElementsByTagName`|HTMLCollection|✅|
|`querySelector`|Tek element (ilk eşleşen)|❌|
|`querySelectorAll`|NodeList|✅|
