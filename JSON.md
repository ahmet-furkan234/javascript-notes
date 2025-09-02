JSON, verileri **anahtar-değer (key-value)** çiftleriyle temsil eden, **dil bağımsız** ama JavaScript'e çok benzeyen, **hafif ve kolay okunabilir** bir veri formatıdır.

Kullanım alanı:

- API’lerle veri alışverişi
- localStorage/sessionStorage ile veri saklama
- Nesnelerin dışa aktarımı

---

## 🧱 JSON Söz Dizimi (Syntax)



```JSON
{
  "ad": "Ahmet",
  "yas": 25,
  "diller": ["JavaScript", "Python"],
  "adres": {
    "sehir": "İstanbul",
    "ulke": "Türkiye"
  }
}
```

> 🔹 Anahtarlar **çift tırnak** içinde olmalıdır  
> 🔹 Sadece veri (fonksiyon yok)  
> 🔹 Noktalı virgül yok

---

## 🔁 JavaScript ↔ JSON Dönüştürme

### 1. 🧬 JS → JSON (Serialize)

```js
const kisi = { ad: "Ali", yas: 30 };
const jsonVeri = JSON.stringify(kisi);
console.log(jsonVeri); // {"ad":"Ali","yas":30}
```

> `JSON.stringify()` → JS nesnesini JSON formatına çevirir (string olur)

---

### 2. 🔬 JSON → JS (Parse)

```js
const jsonStr = '{"ad":"Ali","yas":30}';
const obj = JSON.parse(jsonStr);
console.log(obj.ad); // Ali
```

> `JSON.parse()` → JSON stringini JavaScript nesnesine çevirir

---

## 🧪 Uygulama Örneği – localStorage ile JSON Kullanımı


```js
let ogrenci = {
  ad: "Zeynep",
  yas: 22,
  sehir: "Ankara"
};

localStorage.setItem("veri", JSON.stringify(ogrenci));

let alinan = JSON.parse(localStorage.getItem("veri"));
console.log(alinan.sehir); // Ankara
```

---

## ⚠️ JSON.stringify Seçenekleri


```js
const data = {
  ad: "Mehmet",
  yas: 27,
  sifre: "1234"
};

const sade = JSON.stringify(data, ["ad", "yas"]); // sadece ad ve yas
const guzel = JSON.stringify(data, null, 2);      // girintili, okunabilir
console.log(guzel);
```

---

## ✅ JSON ile Dizi


```js
let kisiler = [
  { ad: "Ali", yas: 25 },
  { ad: "Ayşe", yas: 28 }
];

let json = JSON.stringify(kisiler);
let geri = JSON.parse(json);
console.log(geri[1].ad); // Ayşe
```

---

## JSON ile Ne Yapılamaz?

- Fonksiyonlar saklanmaz
- Date nesnesi direkt dönüştürülemez (string olur)
- Döngüsel referanslı objeler hata verir