
JavaScript’te `Math` nesnesi, matematiksel işlemler ve hesaplamalar yapmak için hazır metotlar ve sabitler sunar. `Math` bir **nesne (object)** olduğu için `new` ile oluşturulmaz. Direkt kullanılır.

---

## 📌 Genel Yapı


```js
Math.methodName(değer);
```

---

## 🧾 1. Sayı Yuvarlama Metotları

|Metot|Açıklama|Örnek|
|---|---|---|
|`Math.round(x)`|En yakın tam sayıya yuvarlar|`Math.round(4.6) → 5`|
|`Math.ceil(x)`|Yukarı yuvarlar|`Math.ceil(4.2) → 5`|
|`Math.floor(x)`|Aşağı yuvarlar|`Math.floor(4.8) → 4`|
|`Math.trunc(x)`|Ondalığı siler (sıfıra yuvarlar)|`Math.trunc(4.9) → 4`|

---

## ➕➖ 2. Sayısal İşlemler

|Metot|Açıklama|Örnek|
|---|---|---|
|`Math.abs(x)`|Mutlak değer|`Math.abs(-5) → 5`|
|`Math.pow(x, y)`|Üs alma|`Math.pow(2, 3) → 8`|
|`Math.sqrt(x)`|Karekök|`Math.sqrt(16) → 4`|
|`Math.cbrt(x)`|Küpkök|`Math.cbrt(27) → 3`|

---

## 🔢 3. Min & Max

|Metot|Açıklama|Örnek|
|---|---|---|
|`Math.max(a, b, c...)`|En büyük değeri bulur|`Math.max(1, 5, 3) → 5`|
|`Math.min(a, b, c...)`|En küçük değeri bulur|`Math.min(1, 5, 3) → 1`|

---

## 🎲 4. Rastgele Sayı

|Metot|Açıklama|Örnek|
|---|---|---|
|`Math.random()`|0 ile 1 arasında rastgele sayı üretir|`Math.random() → 0.378...`|
### 📌 Örnek: 1 ile 10 arasında sayı



```js
let sayi = Math.floor(Math.random() * 10) + 1;
```

---

## 🧮 5. Trigonometrik Metotlar (Radyan cinsinden)

|Metot|Açıklama|
|---|---|
|`Math.sin(x)`|Sinüs|
|`Math.cos(x)`|Kosinüs|
|`Math.tan(x)`|Tanjant|
|`Math.asin(x)`|Arcsin|
|`Math.acos(x)`|Arccos|
|`Math.atan(x)`|Arctan|

---

## 🧮 6. Logaritma & Üs

|Metot|Açıklama|Örnek|
|---|---|---|
|`Math.log(x)`|Doğal log (e tabanlı)|`Math.log(1) → 0`|
|`Math.log10(x)`|10 tabanında log|`Math.log10(100) → 2`|
|`Math.exp(x)`|`e^x` hesaplar|`Math.exp(1) → 2.718...`|

---

## 🧷 7. Sabitler (Constants)

|Sabit|Açıklama|Değer|
|---|---|---|
|`Math.PI`|π sayısı|`3.14159...`|
|`Math.E`|Euler sabiti|`2.718...`|
|`Math.SQRT2`|√2|`1.414...`|
|`Math.LN2`|ln(2)|`0.693...`|
|`Math.LN10`|ln(10)|`2.302...`|

---

## 🧪 Mini Uygulama: Sayı Tahmin Oyunu

```js
const random = Math.floor(Math.random() * 10) + 1;
const tahmin = prompt("1-10 arası bir sayı tahmin et:");
if (Number(tahmin) === random) {
  alert("Tebrikler! Bildiniz 🎉");
} else {
  alert(`Bilemediniz 😔 Doğru sayı: ${random}`);
}
```

---

## 🔚 Özet

- `Math` nesnesi sayı yuvarlama, mutlak değer, üs, kök, rastgele sayı ve trigonometrik işlemleri içerir.
- `Math.random()` sık kullanılır ama sonucu 0-1 arasında verir; aralıklar için çarpma ve yuvarlama yapılır.

- Tüm `Math` metotları **statiktir**, yani `Math.method()` şeklinde doğrudan kullanılır.