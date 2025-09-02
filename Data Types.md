
JavaScript'te **veri tipleri (data types)**, bir değişkende hangi tür verilerin saklanabileceğini belirler. JS dinamik tür yapısına sahiptir, yani bir değişkenin tipi çalışma zamanında değişebilir.

---

## 🔹 JavaScript Veri Tipleri

### ✅ 1. **İlkel (Primitive) Veri Tipleri**

Tek bir değer içerir, **değiştirilemez (immutable)** ve **değerle** taşınır.

| Tip         | Açıklama               | Örnek                  |
| ----------- | ---------------------- | ---------------------- |
| `string`    | Metin                  | `"Merhaba"`            |
| `number`    | Sayı (tam/sayısal)     | `42`, `3.14`           |
| `boolean`   | Mantıksal (true/false) | `true`, `false`        |
| `undefined` | Tanımsız değişken      | `let a;` → `undefined` |
| `null`      | Boş değeri temsil eder | `null`                 |
| `bigint`    | Çok büyük sayılar için | `123n`                 |
| `symbol`    | Benzersiz tanımlayıcı  | `Symbol("id")`         |

---

### ✅ 2. **Nesnel (Reference) Veri Tipleri**

Birden fazla değeri bir arada tutar, **değiştirilebilir (mutable)** ve **referansla** taşınır.

| Tip        | Açıklama                  | Örnek                   |
| ---------- | ------------------------- | ----------------------- |
| `object`   | Genel nesne               | `{ad: "Ali", yas: 25}`  |
| `array`    | Dizi                      | `[1, 2, 3]`             |
| `function` | Fonksiyon (bir tür nesne) | `function merhaba() {}` |
| `date`     | Tarih nesnesi             | `new Date()`            |

---

## 🔸 Veri Tipi Kontrolü – `typeof`

```js
console.log(typeof "Merhaba"); // string
console.log(typeof 42);        // number
console.log(typeof true);      // boolean
console.log(typeof undefined); // undefined
console.log(typeof null);      // ❗ "object" (bu JS’in eski bir hatası)
console.log(typeof {});        // object
console.log(typeof []);        // object (diziler de nesnedir)
console.log(typeof function() {}); // function
```

---

## 🔸 `null` ile `undefined` Farkı

| Özellik         | `undefined`                     | `null`            |
| --------------- | ------------------------------- | ----------------- |
| Otomatik atanır | Tanımsız bırakılan değişkenlere | El ile atanır     |
| Tip             | `undefined`                     | `object` (JS bug) |
| Anlam           | "Henüz değer atanmamış"         | "Kasıtlı boşluk"  |

```js
let a;
console.log(a); // undefined

let b = null;
console.log(b); // null
```

---

## 🔸 İlginç Bir Durum: `NaN`

- “Not a Number” anlamına gelir.
- Sayı olmayan bir şeyin sayıya çevrilmeye çalışılmasıyla oluşur.

```js
console.log("abc" / 2); // NaN
console.log(typeof NaN); // number
```

---

