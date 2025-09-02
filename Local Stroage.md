
`localStorage`, tarayıcıda **kalıcı** olarak veri saklamanızı sağlar. Sayfa yenilense, hatta tarayıcı kapatılıp açılsa bile veriler kaybolmaz.

- Anahtar–değer (key–value) şeklinde çalışır.
- Sadece **string** veri saklar.

---

## 📌 Temel Metotlar

|Metot|Açıklama|
|---|---|
|`setItem(key, value)`|Veri ekler/günceller|
|`getItem(key)`|Veriyi okur|
|`removeItem(key)`|Belirli bir veriyi siler|
|`clear()`|Tüm verileri temizler|
|`key(index)`|Belirtilen sıradaki anahtarı döner|

---

## 📘 1. Veri Ekleme / Güncelleme


```js
localStorage.setItem("kullaniciAdi", "Zeynep");
```

> Aynı anahtarla tekrar yazarsan üzerine yazar (günceller).

---

## 📘 2. Veri Okuma


```js
let ad = localStorage.getItem("kullaniciAdi"); 
console.log(ad); // Zeynep
```

---

## 📘 3. Veri Silme


```js
localStorage.removeItem("kullaniciAdi");
```

---

## 📘 4. Tüm localStorage’ı Temizleme


```js
localStorage.clear();
```

---

## 📘 5. Saklanan Anahtarları Listeleme



```js
for (let i = 0; i < localStorage.length; i++) {
  let key = localStorage.key(i);
  console.log(`Key: ${key}, Value: ${localStorage.getItem(key)}`);
}
```

---
## 📦 Obje ve Dizi Saklama

`localStorage` sadece string sakladığı için, **nesne ve dizileri saklarken JSON kullanılır**.

### 🧪 Nesne Saklama:


```js
let ogrenci = { ad: "Ali", yas: 23 }; 
localStorage.setItem("ogrenci", JSON.stringify(ogrenci));`
```

### 🧪 Nesne Okuma:


```js
let veri = JSON.parse(localStorage.getItem("ogrenci")); 
console.log(veri.ad); // Ali
```

### 🧪 Dizi Saklama:



```js
let renkler = ["kırmızı", "yeşil", "mavi"]; 
localStorage.setItem("renkler", JSON.stringify(renkler));
```

### 🧪 Dizi Okuma:


```js
let renkler = JSON.parse(localStorage.getItem("renkler")); 
console.log(renkler[1]); // yeşil
```

---

## ⚠️ Önemli Notlar

- Sadece aynı **domain** altında çalışır (güvenlik).
- **Kapasite sınırı** yaklaşık 5-10 MB'dır.
- Sadece **string veri** saklar, bu yüzden JSON kullanılır.
- **Hassas veriler** (şifre, token) saklanmamalıdır.