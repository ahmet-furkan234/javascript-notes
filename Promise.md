
**Promise**, gelecekte bir zamanda tamamlanacak (başarılı veya hatalı) bir işlemi temsil eder.

> 📌 Promise: “Bir söz veriyorum, işlem bitecek — ya başarıyla (`resolve`) ya da hatayla (`reject`).”

---

## 🔧 Promise’in Temel Yapısı

```js
const promise = new Promise((resolve, reject) => {
  // Asenkron işlem burada yapılır
  const basariliMi = true;

  if (basariliMi) {
    resolve("İşlem başarılı!");
  } else {
    reject("Bir hata oluştu.");
  }
});

promise
  .then(sonuc => console.log("✅", sonuc))
  .catch(hata => console.error("❌", hata));
```

---

## 🧠 Promise'in 3 Durumu Vardır:

| Durum                    | Açıklama                      |
| ------------------------ | ----------------------------- |
| **Pending**              | Beklemede, henüz tamamlanmadı |
| **Fulfilled (Resolved)** | Başarılı şekilde tamamlandı   |
| **Rejected**             | Hatalı şekilde tamamlandı     |

---
## 📌 Basit Örnek: Zamanlı İşlem


```js
const bekle = new Promise((resolve) => {
  setTimeout(() => {
    resolve("3 saniye sonra tamamlandı.");
  }, 3000);
});

bekle.then((mesaj) => {
  console.log(mesaj);
});
```

---

## ⛔ Hatalı Durumu Yönetmek

```js
const hataPromise = new Promise((resolve, reject) => {
  const hataVar = true;

  if (hataVar) {
    reject("Bir sorun oluştu.");
  } else {
    resolve("Sorun yok!");
  }
});

hataPromise
  .then(sonuc => console.log("Başarılı:", sonuc))
  .catch(hata => console.error("Hata:", hata));
```

---

## 🧪 Gerçekçi Senaryo: Yemek Hazırlama

```js
function yemekHazirla() {
  return new Promise((resolve, reject) => {
    setTimeout(() => {
      const malzemeVar = true;

      if (malzemeVar) {
        resolve("Yemek hazır!");
      } else {
        reject("Malzeme yok!");
      }
    }, 2000);
  });
}

yemekHazirla()
  .then((mesaj) => console.log("✅", mesaj))
  .catch((hata) => console.error("❌", hata));
```

---

## 🔁 `.then()` Zincirleme (Chaining)

```js
new Promise((resolve) => {
  resolve(2);
})
  .then((sayi) => sayi * 3)
  .then((sayi) => sayi + 1)
  .then((sayi) => console.log("Sonuç:", sayi)); // Sonuç: 7
```