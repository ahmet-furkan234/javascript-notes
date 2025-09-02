
JavaScript'te değişken tanımlamak için üç temel anahtar kelime kullanılır:

---

## 🔹 1. `var`

## 🔹 2. `let`

## 🔹 3. `const`

Bunlar arasında **kapsam (scope)**, **yeniden tanımlama** ve **değer değiştirme (mutability)** açısından önemli farklar vardır.

---
## ✅ 1. `var` – Eski yöntem (ES5 ve öncesi)

- Fonksiyon kapsamına sahiptir.
- Blok seviyesinde çalışmaz.
- Aynı isimle tekrar tanımlanabilir.
- `Hoisting` (yukarı taşınma) özelliği vardır.

```js
var mesaj = "Merhaba";
var mesaj = "Selam"; // tekrar tanımlanabilir
console.log(mesaj); //Selam"
```

```js
function test() {
  if (true) {
	var a = 5;
  }
  console.log(a); // 5 (blok dışına sızar!)
}
```

---

## ✅ 2. `let` – Modern yöntem (ES6+)

- **Blok kapsamlıdır.**
- Yeniden tanımlanamaz ama değeri değiştirilebilir.
- `Hoisting` vardır ama **tanımlanmadan önce kullanılamaz**.

```js
let isim = "Ahmet";
isim = "Mehmet"; // değeri değiştirilebilir

// let isim = "Ali"; // ❌ Hata: aynı blokta tekrar tanımlanamaz

{
  let x = 10;
  console.log(x); // 10
}
// console.log(x); // ❌ Hata: x tanımlı değil

```

---

## ✅ 3. `const` – Sabit değerli değişken

- **Blok kapsamlıdır.**
- Tanımlandıktan sonra **değeri değiştirilemez.**
- **Mutlaka bir değerle tanımlanmalıdır.**

```js
const pi = 3.14;
// pi = 3.1415; // ❌ Hata: const ile tanımlanan değeri değiştiremezsiniz
```

```js 
const dizi = [1, 2, 3];
dizi.push(4);      // ✅ çalışır
console.log(dizi); // [1, 2, 3, 4]

const kisi = { ad: "Ali" };
kisi.ad = "Veli";  // ✅ çalışır
```

---

## 🔸 Özet Tablosu

| Özellik          | `var`     | `let`     | `const`               |
| ---------------- | --------- | --------- | --------------------- |
| Kapsam (scope)   | Fonksiyon | Blok      | Blok                  |
| Tekrar tanımlama | ✅ Evet    | ❌ Hayır   | ❌ Hayır               |
| Değer değiştirme | ✅ Evet    | ✅ Evet    | ❌ Hayır (ilkel değer) |
| Hoisting         | ✅ Evet    | ⚠️ Kısmen | ⚠️ Kısmen             |

---

## Hangi Durumda Hangisi Kullanılır?

🔸 `let`: Değişkenin değerinin değişmesi gerekiyorsa  
🔸 `const`: Sabit kalacaksa (özellikle sabit referanslar)  
🔸 `var`: ❌ Artık önerilmez, eski kodlar dışında kullanılmamalı

---

