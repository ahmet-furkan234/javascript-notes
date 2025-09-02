
**Callback**, başka bir fonksiyona **parametre olarak verilen fonksiyondur**. Genellikle bir işlem tamamlandığında çağrılması için kullanılır.

> 📌 Basitçe: "İşlem bitince bunu çalıştır."

----

## ✅ Basit Bir Callback Örneği


```js
function selamVer(isim, callback) {
  console.log("Merhaba " + isim);
  callback(); // işlemi bitirince çağır
}

function bitince() {
  console.log("İşlem tamamlandı.");
}

selamVer("Ali", bitince);

// Çıktı:
// Merhaba Ali
// İşlem tamamlandı.
```

Burada `bitince`, `selamVer` fonksiyonuna **callback** olarak veriliyor.

---

## ⏱ Asenkron Yapıda Callback Kullanımı

```js
console.log("İşlem başlıyor...");

setTimeout(function () {
  console.log("3 saniye bekledi");
}, 3000);

console.log("İşlem bitti.");
```

Bu örnekte, `setTimeout` fonksiyonu bir **callback alıyor**: `function () { console.log(...) }`

---

## 🎯 Callback Fonksiyonların Kullanım Amaçları

- İşlem tamamlandığında haber vermek
- Kod tekrarını azaltmak
- Asenkron işlem tamamlandığında başka bir işlem başlatmak

---

## ⚠️ Callback Hell (Callback Cehennemi)

Birden fazla iç içe callback yazıldığında **okunabilirlik bozulur**:

```js
login(user, function () {
  getData(function () {
    processData(function () {
      showResult();
    });
  });
});
```

Bu gibi durumlar için **Promise** ve **async/await** yapıları tercih edilir. Onlara da geçeceğiz. 👍

---

## 🧪 Uygulamalı Örnek

```js
function yemekHazirla(callback) {
  console.log("Yemek hazırlanıyor...");
  setTimeout(() => {
    console.log("Yemek hazır!");
    callback();
  }, 2000);
}

function yemekYe() {
  console.log("Yemeğe başla!");
}

yemekHazirla(yemekYe);

// Çıktı:
// Yemek hazırlanıyor...
// (2 saniye sonra)
// Yemek hazır!
// Yemeğe başla!
```
