
👉 **Immediately Invoked Function Expression** demektir.  
👉 **Tanımlandığı anda çalışan fonksiyon ifadesidir.**  
👉 Yani fonksiyonu yazarsın ve hemen çağırırsın, ayrıca bir `call` yapmana gerek kalmaz.

---

## 🔑 **Yapısı**

```js
(function() {
    console.log("Ben hemen çalıştım!");
})();
```

veya

```js
(() => {
    console.log("Ben de hemen çalıştım! (Arrow ile)");
})();
```

➡ **Parantezler ( ) fonksiyonu ifadesi (expression) yapar.**  
➡ Sonundaki `()` hemen çalıştırır.

---

## 🎯 **Neden kullanılır?**

✅ Bir **izole alan (scope)** yaratmak için.  
✅ Global değişken kalabalığını engellemek için.  
✅ Değişkenlerin dışarı sızmasını engellemek için.

---

## 💡 **Örnek**

```js
(function() {
    let mesaj = "Bu değişken sadece burada geçerli";
    console.log(mesaj);
})();

console.log(typeof mesaj);  // undefined
```

👉 `mesaj` dışarıdan erişilemez, çünkü IIFE bir kapsama alanı oluşturdu.

---

## ⚠ **IIFE olmadan ne olurdu?**

```js
function calistir() {
    console.log("Ben normal bir fonksiyonum");
}
calistir();
```

👉 Burada fonksiyonu tanımladın ve sonra ayrıca çağırdın.

---

## 📝 **Kullanım yerleri**

🔹 Modül yazmak (ES6 öncesi)  
🔹 Geçici işlemler yapmak  
🔹 Global scope’u kirletmemek

---

## 🎁 **Örnek IIFE ile sayacı başlat**

```js
(function() {
    let sayac = 0;
    setInterval(() => {
        sayac++;
        console.log("Sayı: ", sayac);
    }, 1000);
})();
```

✅ `sayac` değişkeni dışarıdan görünmez ama içeride çalışır.

---

## 🌟 **Özet**

| Özellik           | Açıklama                                           |
| ----------------- | -------------------------------------------------- |
| IIFE ne demek?    | Hemen çalışan fonksiyon ifadesi                    |
| Neden kullanılır? | Scope yaratır, global değişken kalabalığını önler  |
| Söz dizimi        | `(function(){ ... })();` veya `(() => { ... })();` |