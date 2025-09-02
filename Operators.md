
## 🔹 1. #Aritmetik Operatörler

Sayısal değerlerle matematiksel işlemler yapmak için kullanılır.

|Operatör|Anlamı|Örnek|Açıklama|
|---|---|---|---|
|`+`|Toplama|`5 + 2` → `7`|İki sayıyı toplar|
|`-`|Çıkarma|`5 - 2` → `3`|Bir sayıdan diğerini çıkarır|
|`*`|Çarpma|`5 * 2` → `10`|İki sayıyı çarpar|
|`/`|Bölme|`5 / 2` → `2.5`|Bir sayıyı diğerine böler|
|`%`|Mod (kalan)|`5 % 2` → `1`|Bölümden kalan|
|`**`|Üs alma|`2 ** 3` → `8`|Üs hesabı yapar|
|`++`|Arttırma|`a++`|a’yı 1 arttırır|
|`--`|Azaltma|`a--`|a’yı 1 azaltır|

---

## 🔹 2. #Atama Operatörleri

Bir değişkene değer atamak için kullanılır.

|Operatör|Anlamı|Örnek|Açıklama|
|---|---|---|---|
|`=`|Atama|`x = 5`|x’e 5 değeri atanır|
|`+=`|Toplayarak atama|`x += 2`|`x = x + 2` ile aynıdır|
|`-=`|Çıkararak atama|`x -= 2`|`x = x - 2` ile aynıdır|
|`*=`|Çarparak atama|`x *= 2`|`x = x * 2` ile aynıdır|
|`/=`|Bölerek atama|`x /= 2`|`x = x / 2` ile aynıdır|
|`%=`|Mod alarak atama|`x %= 2`|`x = x % 2` ile aynıdır|

---

## 🔹 3. #Karşılaştırma Operatörleri

İki değeri karşılaştırır, sonuç `true` veya `false` döner.

| Operatör | Anlamı                       | Örnek         | Sonuç   |
| -------- | ---------------------------- | ------------- | ------- |
| `==`     | Eşit mi (tipine bakmaz)      | `5 == '5'` →  | `true`  |
| `===`    | Hem değer hem tip eşit mi    | `5 === '5'` → | `false` |
| `!=`     | Eşit değil mi                | `5 != '5'` →  | `false` |
| `!==`    | Değer veya tip eşit değil mi | `5 !== '5'` → | `true`  |
| `>`      | Büyük mü                     | `5 > 3` →     | `true`  |
| `<`      | Küçük mü                     | `5 < 3` →     | `false` |
| `>=`     | Büyük veya eşit mi           | `5 >= 5` →    | `true`  |
| `<=`     | Küçük veya eşit mi           | `5 <= 4` →    | `false` |

---

## 🔹 4. #Mantıksal Operatörler

Koşulları birleştirmek veya kontrol etmek için kullanılır.

| Operatör | Anlamı      | Örnek                     | Açıklama                      |
| -------- | ----------- | ------------------------- | ----------------------------- |
| `&&`     | VE (and)    | `true && false` → `false` | İkisi de doğruysa sonuç doğru |
| \|       |             | `                         | VEYA (or)                     |
| `!`      | DEĞİL (not) | `!true` → `false`         | Sonucun tersini döndürür      |
|          |             |                           |                               |

---


## 🔹 5. #Karar Operatörü (Ternary Operator)

Kısa if/else yazımı.

```js
let age = 18;
let result = (age >= 18) ? "Yetişkin" : "Çocuk";
console.log(result); // Yetişkin
```

---

## 🔹 6. #typeof ve #instanceof

Tür kontrolü yapmak için kullanılır.

| Operatör     | Anlamı                                  | Örnek                       |
| ------------ | --------------------------------------- | --------------------------- |
| `typeof`     | Değişkenin tipini verir                 | `typeof "hello"` → `string` |
| `instanceof` | Bir nesne belirli bir sınıfın örneği mi | `x instanceof Array`        |

---

## 🔹 7. #Nullish Coalescing (`??`)

Null (`null` veya `undefined`) ise sağdaki değeri döner.

```js
let name = null;
let result = name ?? "İsimsiz"; // "İsimsiz"
```

---

## 🔹 8. #Optional Chaining (`?.`)

Eğer değer mevcutsa devam eder, yoksa `undefined` döner.

```js
let user = {};
console.log(user.address?.city); // undefined (hata vermez)
```