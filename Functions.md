
Fonksiyonlar, belirli bir görevi gerçekleştiren **kod bloklarıdır**. Çağrıldığında çalışırlar.

---

## 🔹 1. Fonksiyon Tanımlama

### Klasik Fonksiyon Tanımı (Function Declaration)

```js
function selamVer() {
  console.log("Merhaba!");
}
```

Çağırmak için:

```js
selamVer(); // Merhaba!
```

---

## 🔹 2. Parametreli Fonksiyon

```js
function topla(a, b) {
  console.log(a + b);
}

topla(3, 5); // 8
```


---
## 🔹 3. Geri Dönen (return) Fonksiyon

```js
function kare(x) {
  return x * x;
}

let sonuc = kare(4); // 16
```

---

## 🔹 4. Arrow Function (Ok Fonksiyonu)

Modern ve kısa yazım şeklidir:

```js
const topla = (a, b) => a + b;

console.log(topla(2, 3)); // 5
```

Tek parametreli örnek:

```js
const kare = x => x * x;
```

Bloklu versiyon (return gerek):

```js
const topla = (a, b) => {
  let sonuc = a + b;
  return sonuc;
};
```

---

## 🔹 5. Anonim Fonksiyon (İsimsiz)

Genellikle **değişkene atanır** veya **callback** olarak kullanılır:

```js
const mesaj = function() {
  console.log("Merhaba dünya!");
};

mesaj(); // Merhaba dünya!
```

---

## 🔹 6. Fonksiyona Varsayılan Parametre Verme

```js
function selam(isim = "Ziyaretçi") {
  console.log("Merhaba, " + isim);
}

selam();         // Merhaba, Ziyaretçi
selam("Ahmet");   // Merhaba, Ahmet
```

---

## 🔹 7. Rest Parametreler (`...`)

Bilinmeyen sayıda parametre almak için kullanılır:

```js
function topla(...sayilar) {
  return sayilar.reduce((a, b) => a + b, 0);
}

console.log(topla(1, 2, 3)); // 6
```

---

## 🔹 8. Fonksiyonların Fonksiyon Döndürmesi


```js
function selamla(mesaj) {
  return function(isim) {
    console.log(`${mesaj}, ${isim}`);
  };
}

const merhaba = selamla("Merhaba");
merhaba("Ali"); // Merhaba, Ali
```

---

## 🔹 9. Fonksiyonları Parametre Olarak Verme (Callback)

```js
function islemYap(sayi, islem) {
  return islem(sayi);
}

function ikiyleCarp(n) {
  return n * 2;
}

console.log(islemYap(5, ikiyleCarp)); // 10
```

---
## 🎯 Özet

|Tür|Açıklama|
|---|---|
|Function Declaration|Geleneksel tanım|
|Function Expression|Değişkene atanmış fonksiyon|
|Arrow Function|Kısa, modern yazım|
|Anonymous Function|İsimsiz, genelde callback’lerde|
|Callback|Fonksiyon parametre olarak geçilir|
