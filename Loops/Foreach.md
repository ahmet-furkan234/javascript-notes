

`forEach()`, yalnızca **diziler (Array)** üzerinde çalışır ve **her eleman için bir kez** verilen fonksiyonu çalıştırır.  
Yapı olarak `for...of` veya `for` döngüsüne benzer ama **daha sade ve fonksiyonel** bir yöntemdir.

---

## 🔹 Söz Dizimi

```js
dizi.forEach(function(eleman, index, dizi) {
  // eleman: o anki eleman
  // index: o anki elemanın indeks numarası
  // dizi: tüm dizinin kendisi (opsiyonel)
});
```

💡 Modern kullanımda genellikle **ok fonksiyonu** (`=>`) ile yazılır:

```js
dizi.forEach((eleman, index) => {
  // işlemler
});
```

---

## 🔸 Basit Örnek

```js
let sayilar = [10, 20, 30];

sayilar.forEach((sayi) => {
  console.log("Sayı:", sayi);
});
```

**Çıktı:**

```js
Sayı: 10
Sayı: 20
Sayı: 30
```

---

## 🔸 İndeks ile Kullanım

```js
let meyveler = ["Elma", "Muz", "Kivi"];

meyveler.forEach((meyve, i) => {
  console.log(`${i}. sıradaki meyve: ${meyve}`);
});
```

---

## 🔸 Object dizilerinde

```js
let kisiler = [
  { ad: "Ali", yas: 25 },
  { ad: "Ayşe", yas: 30 }
];

kisiler.forEach((kisi) => {
  console.log(`${kisi.ad}, ${kisi.yas} yaşında`);
});
```

---

## 🔸 Notlar

|Özellik|Açıklama|
|---|---|
|`return` kullanılamaz|Döngüyü durdurmaz|
|`break`, `continue` yok|Kullanılamaz|
|Sadece dizilerde çalışır|Obje için uygun değildir|

---

## 🔸 Alternatif: `map()` vs `forEach()`

- `forEach()` sadece **işlem yapmak** için kullanılır.
- `map()` yeni bir **dizi döndürür**, `forEach` döndürmez.

```js
let x = [1, 2, 3];

let kareler = x.map(n => n * n); // [1, 4, 9]
```

---

