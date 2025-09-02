
JavaScript’te **şart blokları (koşullu ifadeler)**, belirli bir koşula göre kodun çalışmasını sağlar. En yaygın kullanılan şart blokları şunlardır:

---

### 🔹 1. `if` - `else if` - `else`

```js
if (koşul) {
  // Koşul doğruysa burası çalışır
} else if (başka_koşul) {
  // İlk koşul yanlış ama bu doğruysa burası
} else {
  // Hiçbiri doğru değilse burası
}
```

### ✅ Örnek:

```js
let yas = 20;

if (yas < 18) {
  console.log("Reşit değilsin.");
} else if (yas >= 18 && yas < 65) {
  console.log("Yetişkinsin.");
} else {
  console.log("Emekli yaşındasın.");
}
```

---

## 🔹 2. Ternary Operator (`? :`)

Kısa if-else yazımıdır. Genellikle **değişken atamak** veya **kısa koşul kontrolü** için kullanılır.

```js
 koşul ? doğruysa : yanlışsa;
```

### ✅ Örnek:

```js
let not = 75;
let sonuc = not >= 50 ? "Geçti" : "Kaldı";
console.log(sonuc); // Geçti
```

___

## 🔹 3. `switch` Bloğu

Çok sayıda `if-else` yerine kullanılır. `case` değer eşleşmesine göre çalışır.

```js
let gun = "Çarşamba";

switch (gun) {
  case "Pazartesi":
    console.log("Haftanın ilk günü");
    break;
  case "Çarşamba":
    console.log("Haftanın ortası");
    break;
  case "Cuma":
    console.log("Hafta sonuna az kaldı");
    break;
  default:
    console.log("Belirsiz gün");
}
```

---

## 🔹 4. Koşul Tipleri

| Operatör          | Anlamı                    | Örnek               |
| ----------------- | ------------------------- | ------------------- |
| `==`              | Değer eşit mi?            | `5 == "5"` ✅ true   |
| `===`             | Tür + Değer eşit mi?      | `5 === "5"` ❌ false |
| `!=`              | Değer eşit değil mi?      | `5 != "5"` ❌ false  |
| `!==`             | Tür veya değer farklı mı? | `5 !== "5"` ✅ true  |
| `>` `<` `>=` `<=` | Karşılaştırmalar          | `x > 10`            |

---
## 🔹 Örnek: Not Sistemi

```js
let not = 85;

if (not >= 90) {
  console.log("AA");
} else if (not >= 80) {
  console.log("BA");
} else if (not >= 70) {
  console.log("BB");
} else if (not >= 60) {
  console.log("CB");
} else if (not >= 50) {
  console.log("CC");
} else {
  console.log("FF - Kaldınız");
}
```

---

## 🔸 `if`, `else`, `switch`, `?` Ne Zaman Kullanılır?

| Durum                                   | Kullanım         |
| --------------------------------------- | ---------------- |
| Birkaç koşul                            | `if` / `else if` |
| Eşitlik karşılaştırmaları (sabit değer) | `switch`         |
| Tek satır, kısa ifade                   | `ternary (?:)`   |