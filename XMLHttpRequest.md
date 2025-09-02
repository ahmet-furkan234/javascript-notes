
## ✅ Nedir?

`XMLHttpRequest`, JavaScript'te tarayıcı ile sunucu arasında **arka planda veri alışverişi yapmamızı** sağlayan eski bir API’dir.

> Sayfayı yenilemeden veri almanı sağlar ama kullanımı `fetch`'e göre daha karışıktır.

---

## 📦 Temel Kullanımı

```js
const xhr = new XMLHttpRequest(); // 1. Nesne oluşturulur

xhr.open("GET", "https://jsonplaceholder.typicode.com/users"); // 2. Bağlantı ayarlanır

xhr.onload = function () { // 3. Cevap geldiğinde çalışır
  if (xhr.status === 200) {
    const veri = JSON.parse(xhr.responseText); // JSON string → JS nesnesi
    console.log(veri);
  } else {
    console.log("İstek başarısız:", xhr.status);
  }
};

xhr.onerror = function () {
  console.log("Bağlantı hatası!");
};

xhr.send(); // 4. İstek gönderilir
```

---
## ⚙️ Açıklama Adım Adım

|Adım|Açıklama|
|---|---|
|1. `new XMLHttpRequest()`|Yeni XHR nesnesi oluşturur|
|2. `open(method, url)`|HTTP metodu ve adresi tanımlar (GET, POST vs.)|
|3. `onload`|Sunucudan cevap alındığında çalışır|
|4. `send()`|İsteği gönderir|

---
## 🧪 POST İsteği Örneği


```js
const xhr = new XMLHttpRequest();
xhr.open("POST", "https://jsonplaceholder.typicode.com/posts");

xhr.setRequestHeader("Content-type", "application/json");

xhr.onload = function () {
  if (xhr.status === 201) {
    console.log("Başarıyla gönderildi:", JSON.parse(xhr.responseText));
  }
};

const veri = JSON.stringify({ title: "Merhaba", body: "Deneme", userId: 1 });
xhr.send(veri);
```

---

## 🧠 Avantajları ve Dezavantajları

|Avantaj|Dezavantaj|
|---|---|
|Eski tarayıcı desteği vardır|Kullanımı karmaşıktır|
|Düşük seviye kontrol sağlar|Çok fazla kod yazmak gerekir|
|Hatalar ve durumlar zor yönetilir|`Promise` desteklemez|

---

## 📌 Ne Zaman Kullanılır?

- Çok eski sistemlerle uyumluluk gerekiyorsa
- Düşük seviyeli gelişmiş kontrol gerekiyorsa

Ama **günümüzde modern projelerde kullanılmaz**. Artık yerine `fetch()` veya `axios` gibi kütüphaneler tercih edilir.
