
**Asenkron**, JavaScript’te işlemlerin sıralı (bloklayıcı) şekilde değil, **zamanla bağımsız ve paralel gibi** çalışmasını sağlayan programlama modelidir.

---

### 🔁 Senkron (Bloklayıcı)

İşlemler sırayla çalışır. Bir işlem bitmeden diğeri başlamaz.

```js
console.log("1");
console.log("2");
console.log("3");
// Çıktı: 1, 2, 3
```

## ⚡ Asenkron (Bloklamaz)

Bazı işlemler beklerken diğerleri çalışmaya devam eder.

```js
console.log("1");

setTimeout(() => {
  console.log("2"); // 1 saniye sonra
}, 1000);

console.log("3");

// Çıktı: 1, 3, (1 saniye sonra) 2
```

---

## ⚙️ Asenkronluğu Sağlayan Yapılar

| Yapı                         | Açıklama                                           | Örnek                            |
| ---------------------------- | -------------------------------------------------- | -------------------------------- |
| **setTimeout / setInterval** | Zamanlayıcı fonksiyonlar                           | `setTimeout(() => {...}, 1000)`  |
| **HTTP İstekleri**           | Sunucu ile veri alışverişi (fetch, XMLHttpRequest) | `fetch("...").then()`            |
| **Olaylar (Events)**         | Kullanıcı etkileşimi, sistem olayları              | `addEventListener("click", ...)` |
| **Promise / Async-Await**    | Modern asenkron yapılar                            | `async function() { await ... }` |

---

## 🧠 JavaScript Nasıl Asenkron Çalışır?

JavaScript, **tek iş parçacıklı (single-threaded)** bir dildir. Ancak **Event Loop (Olay Döngüsü)** ve **Callback Queue** sayesinde:

- Zamanlayıcılar (setTimeout vs.)
- Ağ istekleri (fetch vs.)
- Kullanıcı olayları

gibi işlemler ayrı olarak bekletilir ve **ana iş kuyruğuna** sonradan eklenir.

---

## 🔄 Küçük Örnek


```js
console.log("Başladı");

setTimeout(() => {
  console.log("Asenkron işlem bitti");
}, 2000);

console.log("Bitti");
// Çıktı: Başladı → Bitti → (2 saniye sonra) Asenkron işlem bitti`
```