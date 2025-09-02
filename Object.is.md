
✅ ES6 (ES2015) ile gelmiştir.  
✅ **`===` (strict equality)** operatörüne çok benzer ama bazı özel durumlarda farklı davranır.

---

## 🔑 **Sözdizimi**

```js
Object.is(value1, value2)
```

> `value1` ve `value2` aynıysa `true`, değilse `false` döner.

---

## 🎨 **Temel Kullanım**

```js
console.log(Object.is(100, 100));          // true
console.log(Object.is("TkMatE", "TkMatE")); // true
console.log(Object.is([], []));             // false (referanslar farklı)
console.log(Object.is({}, {}));             // false (referanslar farklı)
```

---

## 💡 **`Object.is` ve `===` Arasındaki Farklar**

`Object.is`, `===` ile çoğu zaman aynı sonuçları verir.  
Ama iki özel durumda farklıdır:

---

### 1️⃣ **NaN Karşılaştırması**

```js
console.log(NaN === NaN);         // false
console.log(Object.is(NaN, NaN)); // ✅ true
```

✅ **`Object.is` NaN değerlerinin aynı olduğunu kabul eder.**  
❌ `===` NaN’ler için false verir.

---

### 2️⃣ **+0 ve -0**

```js
console.log(+0 === -0);         // true
console.log(Object.is(+0, -0)); // ❌ false
```

✅ **`Object.is` +0 ve -0’ı farklı kabul eder.**  
❌ `===` +0 ve -0’ı aynı kabul eder.

---

## 📌 **Özet Karşılaştırma**

|Karşılaştırma|`===` Sonucu|`Object.is` Sonucu|
|---|---|---|
|`NaN` vs `NaN`|`false`|`true`|
|`+0` vs `-0`|`true`|`false`|
|`"abc"` vs `"abc"`|`true`|`true`|
|`123` vs `123`|`true`|`true`|
|`[]` vs `[]`|`false`|`false`|

---

## 🎯 **Ne Zaman `Object.is` Kullanılır?**

👉 NaN kontrolü yapıyorsan:

```js
const value = NaN;
if (Object.is(value, NaN)) {
  console.log("Değer NaN!");
}
```

👉 +0 / -0 ayrımının önemli olduğu hassas hesaplamalarda.

---

## 💻 **Örnek Demo**

```js
console.log(Object.is("TkMatE", "TkMatE")); // true
console.log(Object.is([], []));             // false
console.log(Object.is(NaN, NaN));           // true
console.log(Object.is(+0, -0));             // false
```

---

## 💡 **Sonuç**

✅ `Object.is` çoğu durumda `===` gibi çalışır ama:

- **NaN değerlerini doğru karşılaştırır**
- **+0 ve -0 farkını gözetir**