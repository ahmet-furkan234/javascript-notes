
**Dizi**, birden fazla veriyi tek bir değişkende saklamamıza olanak tanıyan bir yapıdır.  
Her eleman, sıfırdan başlayan bir **indekse** sahiptir.

---

## 🔹 Dizi Oluşturma

### 1. Köşeli parantez ile (en yaygın):

```js
let renkler = ["Kırmızı", "Mavi", "Yeşil"];
```

### 2. `new Array()` ile:

```js
let sayilar = new Array(10, 20, 30);
```

---

## 🔹 Elemanlara Erişim

```js
let meyveler = ["Elma", "Armut", "Muz"];

console.log(meyveler[0]); // Elma
console.log(meyveler[2]); // Muz
```

>  ✅ **İndeksler 0'dan başlar!**

---

## 🔹 Eleman Ekleme

```js
let liste = [];

liste[0] = "İlk";
liste.push("Son");     // sona ekler
liste.unshift("Baş");  // başa ekler
```

---

## 🔹 Eleman Silme

```js
let dizi = ["A", "B", "C"];

dizi.pop();      // sondan siler ("C")
dizi.shift();    // baştan siler ("A")
```

---

## 🔹 Dizi Uzunluğu

```js
let dizi = [5, 6, 7];
console.log(dizi.length); // 3
```

---

## 🔹 Dizi İçinde Döngü

```js
let sayilar = [1, 2, 3];

for (let i = 0; i < sayilar.length; i++) {
  console.log(sayilar[i]);
}
```

Ya da:

```js
sayilar.forEach(s => console.log(s));
```

---

## 🔹 Dizi Türü Kontrolü

```js
let dizi = [1, 2, 3];

console.log(Array.isArray(dizi)); // true
```

---

## 🔹 Çok Boyutlu Dizi

```js
let tablo = [
  [1, 2],
  [3, 4]
];

console.log(tablo[1][0]); // 3
```

---
## 🔹 İçeriyor mu?

```js
let renkler = ["Mavi", "Sarı"];

console.log(renkler.includes("Sarı")); // true
```

---

## 🔹 Örnek Uygulama

```js
let sepet = [];

sepet.push("Ekmek");
sepet.push("Süt");

if (sepet.includes("Süt")) {
  console.log("Süt sepette var!");
}
```
