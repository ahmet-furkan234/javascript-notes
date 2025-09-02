
`WeakMap`, tıpkı `Map` gibi **anahtar-değer (key-value)** çiftleri tutar,  
ancak bazı önemli farkları vardır:

---
## 📌 Temel Özellikler

| Özellik                        | Açıklama                                           |
| ------------------------------ | -------------------------------------------------- |
| ✅ Anahtar sadece **object**    | `WeakMap`’te **sadece nesneler** anahtar olabilir. |
| ❌ Primitive (sayı, string) yok | Sayı, string, boolean anahtar O-LA-MAZ.            |
| ✅ Garbage Collector dostu      | Nesne referansı kalmazsa otomatik temizlenir.      |
| ❌ İterasyon (döngü) yok        | `forEach`, `for...of`, `.keys()` vs. **yok**.      |
| ✅ Gizli veri tutmak için ideal | Dışarıdan erişilemeyen özel veri saklanabilir.     |

---

## 🔧 Kullanım Şekli

### `set`, `get`, `has`, `delete` metodları vardır.


```js
let wm = new WeakMap();

let obj = { ad: "Ahmet" };

wm.set(obj, "Özel veri");

console.log(wm.get(obj));    // "Özel veri"
console.log(wm.has(obj));    // true

wm.delete(obj);              // Veriyi siler
console.log(wm.has(obj));    // false
```

---

## 🛑 Primitive Kullanılamaz

```js
let wm = new WeakMap();
wm.set("anahtar", "deger"); // ❌ Hata verir: Invalid value used as weak map key
```

---

## ♻️ Garbage Collector Etkisi

```js
let wm = new WeakMap();

(function() {
  let tempObj = { id: 1 };
  wm.set(tempObj, "geçici veri");
})(); // tempObj artık referanssız

// tempObj artık ulaşılabilir olmadığından Garbage Collector siler.
```

📌 `Map` kullansaydık bu veri bellekten silinmezdi.


---

## 🧪 Ne Zaman `WeakMap` Kullanılır?

- **DOM elementlerine bağlı özel veri** tutmak istiyorsan.
- **Verilerin dışarıdan erişilmesini istemiyorsan.**
- **Garbage collection avantajı** istiyorsan.

---

```js
const privateData = new WeakMap();

function Kisi(ad, yas) {
  let veri = { ad, yas };
  privateData.set(this, veri);
}

Kisi.prototype.bilgileriGoster = function () {
  let veri = privateData.get(this);
  console.log(`${veri.ad}, ${veri.yas} yaşında.`);
};

let k1 = new Kisi("Zeynep", 28);
k1.bilgileriGoster(); // Zeynep, 28 yaşında
```

📌 Dışarıdan `ad` veya `yas`’a ulaşılamaz. Gerçek gizlilik!

---

## 🎯 Özet

|Özellik|`Map`|`WeakMap`|
|---|---|---|
|Anahtar Türü|Her şey|Sadece object|
|Döngü/iterasyon|✅ Evet|❌ Hayır|
|Bellek yönetimi|Manuel|Otomatik|
|Gizli veri saklama|❌ Zor|✅ Mümkün|
