
**Symbol**, JavaScript’te **benzersiz ve değiştirilemez (immutable)** bir veri türüdür.  
ES6 (2015) ile birlikte gelmiştir.

👉 Symbol'ün temel amacı:  
➡️ Nesnelerde **benzersiz anahtar (property key)** olarak kullanılabilen bir değer oluşturmaktır.  
➡️ Her oluşturulan `Symbol`, birbirinden farklıdır, **aynı açıklama verilse bile**.

---

## 📝 **Symbol Nasıl Oluşturulur?**

```js
const id = Symbol();             // açıklamasız
const userId = Symbol("user id"); // açıklamalı (description)
```

> 🔑 Symbol açıklaması (description) sadece **debug (hata ayıklama)** içindir. Symbol değerinin kendisini etkilemez.

---

## 🎨 **Symbol’ün Özelliği: Benzersizlik**

```js
const sym1 = Symbol("test");
const sym2 = Symbol("test");

console.log(sym1 === sym2); // ❌ false
```

✅ İkisi de `"test"` açıklamasına sahip olsa da **farklı** Symbol'lerdir.

---

## 🌟 **Symbol Nesne Anahtarı Olarak Kullanımı**

Normalde nesne anahtarları string olur. Ama Symbol kullanırsan o anahtar **gizli ve çakışmaz** olur:

```js
const id = Symbol("id");

const user = {
  name: "TkMatE",
  [id]: 12345
};

console.log(user); 
// { name: 'TkMatE', [Symbol(id)]: 12345 }

console.log(user[id]); 
// 12345
```

💡 **Avantaj:** Symbol anahtarları `for...in`, `Object.keys()` gibi standart döngülerde görünmez:

```js
for (let key in user) {
  console.log(key); // sadece 'name' yazılır
}

console.log(Object.keys(user)); // ["name"]
```

👉 Symbol ile eklediğin property, **gizli bir property** gibi davranır.

---

## ⚡ **Symbol Nerede Kullanılır?**

✅ Nesne içinde özel/gizli alanlar yaratmak  
✅ Kütüphane ya da framework yazarken çakışmayan özel anahtarlar tanımlamak  
✅ JavaScript’in kendi yapılarında özel davranış tanımlamak

---

## 📌 **Bazı Yerleşik Symbol’ler**

JavaScript, bazı özellikleri özelleştirmek için Symbol’ler tanımlar:

```js
const myObj = {
  [Symbol.toPrimitive](hint) {
    if (hint === "number") return 42;
    if (hint === "string") return "TkMatE";
    return null;
  }
};

console.log(+myObj);     // 42
console.log(`${myObj}`); // "TkMatE"
```

🎯 Diğer örnekler:

- `Symbol.iterator` → nesnenin döngü ile nasıl gezileceğini tanımlar.
- `Symbol.toStringTag` → `Object.prototype.toString.call(obj)` çıktısını değiştirir.

---

## 💡 **Symbol’ün Özet Avantajları**

|Özellik|Açıklama|
|---|---|
|Benzersiz|Her Symbol kendine özgüdür|
|Çakışmaz anahtar|Nesne property’leri arasında çakışma olmaz|
|Gizli property|Normal döngü ve Object.keys ile görünmez|
|Immutable|Symbol değiştirilemez|

---

## 🔑 **Kısaca Symbol**

➡ **Primitive veri tipi**dir (string, number gibi).  
➡ **Nesne property’leri için güvenli ve çakışmaz anahtar sağlar.**  
➡ **Framework ve kütüphane geliştiricileri için vazgeçilmezdir.**