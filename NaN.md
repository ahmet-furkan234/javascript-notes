
JavaScript’te `NaN` (Not-a-Number), sayıya dönüştürülmeye çalışılan ama sayı olmayan bir değeri ifade eder.

---
## 🔹 `NaN` Nedir?

`NaN` bir sayısal değerdir ama **geçersiz bir sayı** anlamına gelir.

```js
console.log("abc" / 2); // NaN
console.log(0 / 0);     // NaN
console.log(Math.sqrt(-1)); // NaN
```

---

## 🔸 `typeof NaN` Neden "number"?

```js
console.log(typeof NaN); // "number"
```

> Bu, JavaScript’in tarihsel bir "tuhaflığı"dır. `NaN`, matematiksel bir "geçersiz sayı" olduğu için `typeof` sonucu yine `"number"` döner.

---
## 🔹 NaN Kontrolü Nasıl Yapılır?
####  ❌ Kötü Yol: `===` ile Karşılaştırma

```js
console.log(NaN === NaN); // ❌ false
```

> Çünkü `NaN`, kendisiyle **bile eşit değildir**.

---

## ✅ 1. `isNaN()` Fonksiyonu

```js
console.log(isNaN("abc"));     // true → sayı değil
console.log(isNaN(123));       // false
console.log(isNaN(NaN));       // true
console.log(isNaN("123"));     // false (çünkü string sayı olabilir)
```

>`isNaN()`, önce değeri **number'a çevirir**, sonra kontrol eder.

```js
isNaN("abc")   → isNaN(NaN) → true
isNaN("123")   → isNaN(123) → false
```

---

### ✅ 2. `Number.isNaN()` (ES6+)

- `isNaN()`'den daha güvenlidir. **Sadece gerçek `NaN`'leri kontrol eder.**
- **Tür dönüşümü yapmaz.**

```js
Number.isNaN(NaN);        // ✅ true
Number.isNaN("abc");      // ❌ false
Number.isNaN(undefined);  // ❌ false
Number.isNaN(0 / 0);      // ✅ true
```

---

## 🔹 Örnek Kullanmalar

### Kullanıcıdan gelen değerin sayı olup olmadığını kontrol et:

```js
let input = "abc";
let sayi = Number(input);

if (Number.isNaN(sayi)) {
  console.log("Geçerli bir sayı girilmedi!");
} else {
  console.log("Sayı:", sayi);
}
```

---

## 🔸 Özet

|Yöntem|Ne Yapar?|
|---|---|
|`NaN === NaN`|❌ `false` (NaN kendine bile eşit değil)|
|`isNaN(x)`|✅ Ama tür dönüşümü yapar (dikkat!)|
|`Number.isNaN(x)`|✅ Yalnızca saf `NaN` ise true döner|
