
## ✅ Nedir?

`fetch()` tarayıcıda yerleşik gelen, sunucudan veri almak veya sunucuya veri göndermek için kullanılan **Promise tabanlı** modern bir API’dir.

> ✅ Daha okunabilir  
> ✅ Promise desteği sayesinde `then/catch` veya `async/await` ile kullanılabilir  
> ✅ JSON ile mükemmel uyumludur

---

## 📦 Temel Kullanımı (GET)


```js
fetch("https://jsonplaceholder.typicode.com/users")
  .then(response => {
    if (!response.ok) throw new Error("Bir hata oluştu!");
    return response.json(); // JSON'u JavaScript nesnesine çevir
  })
  .then(data => {
    console.log(data); // Veriyi kullan
  })
  .catch(error => {
    console.error("Hata:", error.message);
  });

```

---

## ✅`async/await` ile Kullanımı (Tavsiye Edilen)


```js
async function veriAl() {
  try {
    const response = await fetch("https://jsonplaceholder.typicode.com/posts");
    if (!response.ok) throw new Error("İstek başarısız");
    
    const data = await response.json();
    console.log(data);
  } catch (error) {
    console.error("Hata:", error.message);
  }
}

veriAl();
```

---

```js
fetch("https://jsonplaceholder.typicode.com/posts", {
  method: "POST",
  headers: {
    "Content-Type": "application/json"
  },
  body: JSON.stringify({
    title: "Yeni Başlık",
    body: "Açıklama",
    userId: 1
  })
})
  .then(res => res.json())
  .then(data => console.log(data))
  .catch(err => console.error("Hata:", err));
```

---

## 🔧 Diğer HTTP Metotları

- `GET` – veri alma
- `POST` – veri gönderme
- `PUT` – tüm veriyi güncelleme
- `PATCH` – kısmi güncelleme
- `DELETE` – silme

```js
fetch("api/url", {
  method: "DELETE"
});
```

---

## 📌 Özet

|Özellik|`XMLHttpRequest`|`fetch()`|
|---|---|---|
|Yapı|Callback tabanlı|Promise tabanlı|
|Yazım|Uzun, karmaşık|Kısa, okunabilir|
|Modernlik|Eski|Yeni (ES6+)|
|Hata yönetimi|Zor|Kolay (catch / try-catch)|

---

