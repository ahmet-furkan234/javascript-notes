
`WeakSet`, sadece **nesneleri** (object) saklayabilen ve **geçici** olarak kullanılan özel bir koleksiyondur.

---

## 📌 Özellikleri

|Özellik|Açıklama|
|---|---|
|✅ Sadece **object** tutar|Primitive veri (string, number vs.) kabul etmez.|
|✅ Her nesne sadece 1 kere olur|Tekillik kuralı vardır.|
|✅ Garbage collector dostu|Nesne referansı yoksa otomatik silinir.|
|❌ Döngü yapılamaz|`forEach`, `for...of`, `.values()` gibi metodlar yoktur.|
|✅ `add`, `has`, `delete` vardır|Temel işlemler yapılabilir.|

---

## 🔧 Kullanımı

```js
let ws = new WeakSet();

let obj1 = { ad: "Ayşe" };
let obj2 = { ad: "Mehmet" };

ws.add(obj1);
ws.add(obj2);

console.log(ws.has(obj1));   // true

ws.delete(obj2);
console.log(ws.has(obj2));   // false
```

---

## 🚫 Primitive Değerler Kullanılamaz

```js
ws.add(123);      // ❌ Hata: Invalid value used in weak set
ws.add("test");   // ❌ Hata
```

---

## ♻️ Garbage Collector Etkisi

```js
let ws = new WeakSet();

(function() {
  let temp = { id: 1 };
  ws.add(temp);
})(); // temp artık referanssız

// temp nesnesi bellekte kalmaz, garbage collector tarafından temizlenir.
```

---

## ✅ Ne Zaman Kullanılır?

- DOM veya nesne tabanlı geçici verileri tutmak istediğinde
- `Set` gibi döngüye ihtiyacın yoksa
- Hafif ve otomatik temizlenen yapı istiyorsan

---

## 🔐 Örnek: DOM Elemanlarına Durum Takibi

```js
let tiklananlar = new WeakSet();

function tikla(elem) {
  if (tiklananlar.has(elem)) {
    console.log("Zaten tıklandı");
  } else {
    tiklananlar.add(elem);
    console.log("İlk defa tıklandı");
  }
}
```

📌 Böylece her DOM elemanına ait durum tutulabilir ama **otomatik olarak bellekten silinir**, ekstra temizlik gerekmez.

---

## 🎯 `Set` vs `WeakSet` Karşılaştırma

|Özellik|`Set`|`WeakSet`|
|---|---|---|
|Veri tipi|Her şey olabilir|Sadece nesne|
|Döngü|✅ Evet|❌ Hayır|
|`.size`|✅ Var|❌ Yok|
|Garbage collection|❌ Manüel|✅ Otomatik|

---

## ✔ Özet

- `WeakSet`, **hafif**, **nesne tabanlı** ve **geçici** veri tutar.
- Döngü yapılamaz, sayısı bilinemez.
- Belleği yormaz, çöp toplayıcı (GC) gereksiz nesneleri otomatik siler.