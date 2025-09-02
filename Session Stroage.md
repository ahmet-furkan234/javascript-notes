
## ✅ Nedir?

`sessionStorage`, tarayıcıda **geçici** olarak veri saklamanızı sağlar. **Tarayıcı sekmesi kapatıldığında veriler silinir.**

- Anahtar–değer (key–value) şeklinde çalışır.
- Sadece **string** veri saklar.
- Her sekme/karta özel depolamadır.

---

## 📌 Temel Metotlar

|Metot|Açıklama|
|---|---|
|`setItem(key, value)`|Veri ekler/günceller|
|`getItem(key)`|Veriyi okur|
|`removeItem(key)`|Belirli veriyi siler|
|`clear()`|Tüm verileri temizler|
|`key(index)`|Belirtilen sıradaki anahtarı döner|

---

## 📘 1. Veri Ekleme / Güncelleme


```js
sessionStorage.setItem("kullanici", "Ahmet");
```

---

## 📘 2. Veri Okuma

```js
let kullanici = sessionStorage.getItem("kullanici"); 
console.log(kullanici); // Ahmet
```

---

## 📘 3. Veri Silme


```js
sessionStorage.removeItem("kullanici");
```

---

## 📘 4. Tümünü Temizleme


```js
sessionStorage.clear();
```

---

## 📘 5. Anahtarları Listeleme,

```js
for (let i = 0; i < sessionStorage.length; i++) {
  let key = sessionStorage.key(i);
  console.log(`${key}: ${sessionStorage.getItem(key)}`);
}
```

---

## 📦 Obje / Dizi Saklama

Tıpkı `localStorage` gibi `sessionStorage` da **yalnızca string veri** saklar. Obje/dizi gibi veri türleri için `JSON.stringify` / `JSON.parse` kullanılır.

```js
let kullanici = {
  ad: "Deneme",
  email: "deneme@example.com"
};

sessionStorage.setItem("kullanici", JSON.stringify(kullanici));

let veri = JSON.parse(sessionStorage.getItem("kullanici"));
console.log(veri.ad); // Elif
```