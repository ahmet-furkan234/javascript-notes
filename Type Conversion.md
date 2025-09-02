
JavaScript'te **Type Conversion (Tür Dönüştürme)**, bir veri tipinin başka bir veri tipine çevrilmesidir. Bu dönüşüm **otomatik (type coercion)** ya da **manuel (explicit conversion)** olabilir.

---

## 🔹 1. **Otomatik Tür Dönüştürme (Type Coercion)**

JavaScript bazı durumlarda **kendiliğinden** tür değiştirir.

### 🔸 Örnekler:

```js
"5" + 3        // "53"  → String birleştirme (number string'e döner)
"5" - 3        // 2     → String number'a döner
true + 1       // 2     → true → 1
false + "1"    // "false1" → boolean string'e döner
null + 1       // 1     → null → 0
undefined + 1  // NaN   → undefined sayıya çevrilemez
```

---

## 🔹 2. **Manuel Tür Dönüştürme (Explicit Conversion)**

### ✅ String'e Dönüştürme

```js
String(123);        // "123"
String(true);       // "true"
(123).toString();   // "123"
```

### ✅ Sayıya Dönüştürme

```js
Number("123");      // 123
Number(true);       // 1
Number(false);      // 0
Number("abc");      // NaN

parseInt("123abc"); // 123
parseFloat("3.14"); // 3.14
```

### ✅ Boolean’a Dönüştürme

```js
Boolean(1);        // true
Boolean(0);        // false
Boolean("");       // false
Boolean("abc");    // true
Boolean(null);     // false
Boolean(undefined);// false
```

---

## 🔸 Truthy ve Falsy Kavramı

#### ❗ JavaScript’te bazı değerler boolean dönüşümünde **false** olur. Bunlara **falsy** denir:

| Falsy Değerler    |
| ----------------- |
| `false`           |
| `0`               |
| `-0`              |
| `""` (boş string) |
| `null`            |
| `undefined`       |
| `NaN`             |

Bunların dışındaki tüm değerler **truthy** kabul edilir.

---

## 🔹 Özet Tablosu

| Değer       | Number() | String()      | Boolean() |
| ----------- | -------- | ------------- | --------- |
| `"123"`     | `123`    | `"123"`       | `true`    |
| `"abc"`     | `NaN`    | `"abc"`       | `true`    |
| `true`      | `1`      | `"true"`      | `true`    |
| `false`     | `0`      | `"false"`     | `false`   |
| `null`      | `0`      | `"null"`      | `false`   |
| `undefined` | `NaN`    | `"undefined"` | `false`   |
| `0`         | `0`      | `"0"`         | `false`   |
| `""`        | `0`      | `""`          | `false`   |

---

## 🔸 `==` vs `===` (Zayıf ve Sıkı Karşılaştırma)

```js
5 == "5"     // ✅ true → zayıf karşılaştırma, tür dönüşümü yapar
5 === "5"    // ❌ false → sıkı karşılaştırma, hem değer hem tür aynı olmalı
```

---

## 📌 Pratik Tavsiyeler

- `==` yerine **her zaman `===`** kullan.
- Tür dönüşümünü **sen yap**, JS’e bırakma.
- `Number()`, `String()`, `Boolean()` fonksiyonlarını öğren ve kullan.

---

