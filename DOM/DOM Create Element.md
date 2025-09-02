
Bu sayede JavaScript ile dinamik olarak HTML elemanları oluşturabilir ve sayfaya ekleyebilirsin.

---

# 🧱 DOM – Yeni Eleman Oluşturma

## 📌 Adımlar:

1. `document.createElement()` ile yeni eleman oluştur.
2. Özelliklerini ayarla (metin, class, id, stil vs).
3. Sayfaya ekle (`appendChild`, `append`, `prepend`, vs).

---

## ✅ Örnek 1: Basit `p` etiketi oluşturma

```JS
// 1. Elemanı oluştur
const paragraf = document.createElement("p");

// 2. İçeriğini ayarla
paragraf.textContent = "Bu paragraf JavaScript ile oluşturuldu.";

// 3. Sayfaya ekle (örneğin body içine)
document.body.appendChild(paragraf);
```

---

## ✅ Örnek 2: Listeye yeni `li` ekleme

```HTML
<ul id="meyveler">
  <li>Elma</li>
</ul>
```

```js
const ul = document.getElementById("meyveler");

const yeniLi = document.createElement("li");
yeniLi.textContent = "Armut";

ul.appendChild(yeniLi); // <li>Armut</li> eklenir
```

---

## 📌 Diğer Özellikler Nasıl Eklenir?

```js
const btn = document.createElement("button");

btn.textContent = "Tıkla";
btn.id = "buton1";
btn.className = "btn btn-primary";
btn.style.backgroundColor = "blue";

// Olay ekleme
btn.addEventListener("click", function () {
  alert("Butona tıkladın!");
});

document.body.appendChild(btn);
```

---

## 📌 Diğer Ekleme Yöntemleri

| Yöntem           | Açıklama                                       |
| ---------------- | ---------------------------------------------- |
| `appendChild()`  | Sonuna ekler. Sadece 1 eleman alır.            |
| `append()`       | Sonuna ekler. Metin veya çoklu eleman da alır. |
| `prepend()`      | Başına ekler.                                  |
| `insertBefore()` | Belirli bir yerin önüne ekler.                 |

---
## 🧠 Not:

- `createElement` sadece elementi oluşturur, sayfaya **eklemez**.
- Elementi DOM'a eklemeden önce tüm ayarlarını yapabilirsin.
- Tek seferde iç içe elementler oluşturmak istiyorsan `innerHTML` kullanılabilir ama bu daha az güvenlidir.
