
Destructuring sayesinde **dizi veya nesnelerden** kolayca **veri çekebilir**, bu verileri **değişkenlere atayabilirsin**.

---

## ✳️ 1. Array Destructuring

### 🔸 Temel Kullanım:

```js
const sayilar = [10, 20, 30];

const [a, b, c] = sayilar;

console.log(a); // 10
console.log(b); // 20
console.log(c); // 30
```

## 🔸 Atlamalı Atama:

```js
const renkler = ["kırmızı", "yeşil", "mavi"];

const [, ikinci] = renkler;

console.log(ikinci); // yeşil
```

### 🔸 Varsayılan Değerler:

```js
const [x = 1, y = 2] = [];

console.log(x); // 1
console.log(y); // 2
```

---

## ✳️ 2. Object Destructuring

### 🔸 Temel Kullanım:

```js
const kullanici = {
  ad: "Ahmet",
  yas: 30,
};

const { ad, yas } = kullanici;

console.log(ad);  // Ahmet
console.log(yas); // 30
```

### 🔸 Farklı İsimle Atama:

```js
const { ad: isim, yas: yasi } = kullanici;

console.log(isim); // Ahmet
console.log(yasi); // 30
```

### 🔸 Varsayılan Değer:

```js
const { sehir = "Bilinmiyor" } = kullanici;

console.log(sehir); // Bilinmiyor
```

---

## ✳️ 3. Fonksiyon Parametrelerinde Destructuring

```js
function yazdir({ ad, yas }) {
  console.log(`${ad}, ${yas} yaşında`);
}

const kisi = { ad: "Zeynep", yas: 25 };
yazdir(kisi); // Zeynep, 25 yaşında
```

---

## ✳️ 4. Nested (İç İçe) Destructuring

```js
const ogrenci = {
  isim: "Mehmet",
  notlar: {
    vize: 80,
    final: 90,
  },
};

const {
  notlar: { vize, final },
} = ogrenci;

console.log(vize);  // 80
console.log(final); // 90
```

---

## ✳️ 5. Swap (Yer Değiştirme)


```js
let a = 1;
let b = 2;

[a, b] = [b, a];

console.log(a); // 2
console.log(b); // 1
```

---

## 🎯 Nerelerde Kullanılır?

- Dizi/nesneden veri çekmek
- Fonksiyonlara parametre almak
- API verisi işlerken
- React, Vue gibi framework’lerde prop ve state kullanımı
