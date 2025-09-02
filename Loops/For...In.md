
`for...in`, bir **nesnenin (object)** tüm **özellik adları** (property/key) üzerinde gezinmek için kullanılır.  
Diziyle de kullanılabilir ama genelde **nesneler** içindir.

---

## 🔹 Söz Dizimi (Syntax)

```js
for (let key in nesne) {
  // key: özelliğin adı (string)
  // nesne[key]: özelliğin değeri
}
```

---

## 🔸 Nesne Örneği

```js
let kisi = {
  ad: "Ali",
  soyad: "Yılmaz",
  yas: 28
};

for (let ozellik in kisi) {
  console.log(ozellik + ": " + kisi[ozellik]);
}

```

Çıktı:

```js
ad: Ali
soyad: Yılmaz
yas: 28
```

---

## 🔸 Dizi Üzerinde (Kullanılır ama Tavsiye Edilmez)

```js
let meyveler = ["Elma", "Armut", "Muz"];

for (let index in meyveler) {
  console.log(index + ": " + meyveler[index]);
}
```

> ⚠️ Not: Burada `index` bir **string** olarak gelir (örneğin `"0"`, `"1"`), sayısal değil.

✅ Dizi için → `for` ya da `for...of` daha uygundur.

---

## 🔸 Nesne İçindeki Fonksiyonları Atlamak

```js
let araba = {
  marka: "Toyota",
  model: "Corolla",
  yil: 2021,
  yazdir() {
    console.log("Araba");
  }
};

for (let key in araba) {
  if (typeof araba[key] !== "function") {
    console.log(key + ": " + araba[key]);
  }
}
```

---

## 🔸 Ne Zaman `for...in` Kullanılır?

|Amaç|Tercih Et|
|---|---|
|Object’in key’lerini gezmek|✅|
|Dizi için kullanmak|⚠️ Tavsiye edilmez|
|Değerleri doğrudan almak|❌ `for...of` kullan|