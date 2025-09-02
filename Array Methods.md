
JavaScript dizilerinin en güçlü yanı, sunduğu **Array Methods (dizi metodları)**'dır.  
Bunlar dizilerle **işlem yapmayı**, **filtrelemeyi**, **arama yapmayı** ve **yeni diziler oluşturmayı** çok kolaylaştırır.

---

## 🔸 1. **`forEach()`**

Her eleman için belirtilen fonksiyonu çalıştırır. Dizi **değiştirmez**, sadece döner.

```js
let sayilar = [1, 2, 3];

sayilar.forEach((sayi) => {
  console.log(sayi * 2);
});
```

---

## 🔸 2. **`map()`**

Her elemanı değiştirerek **yeni bir dizi** oluşturur.

```js
let sayilar = [1, 2, 3 , 4, 5];
let kareler = sayilar.map(x => x * x);

console.log(kareler); // [1, 4, 9 , 16, 25]
```

---

## 🔸 3. **`filter()`**

Koşula uyan elemanlarla **yeni bir dizi** oluşturur.

```js
let sayilar = [5, 12, 8, 130, 44];

let buyukler = sayilar.filter(x => x > 10);
console.log(buyukler); // [12, 130, 44]
```

---

## 🔸 4. **`find()`**

Koşulu sağlayan **ilk elemanı** döner.

```js
let sayilar = [4, 19, 16, 25];

let sonuc = sayilar.find(x => x > 10);
console.log(sonuc); // 19
```

---

## 🔸 5. **`some()`**

En az **bir eleman** koşulu sağlıyorsa `true` döner.

```js
let yaslar = [14, 17, 20];

console.log(yaslar.some(y => y >= 18)); // true
```

---
## 🔸 6. **`every()`**

**Tüm elemanlar** koşulu sağlıyorsa `true` döner.

```js
let notlar = [75, 60, 90];

console.log(notlar.every(n => n >= 70)); // false
```

---

## 🔸 7. **`reduce()`**

Dizideki elemanları **tek bir değere** indirger (toplam, çarpım, vs).

```js
let sayilar = [1, 2, 3, 4];

let toplam = sayilar.reduce((acc, curr) => acc + curr, 0);
console.log(toplam); // 10
```

---

## 🔸 8. **`includes()`**

Belirli bir değer dizide var mı? → `true / false`

```js
let renkler = ["Kırmızı", "Mavi"];

console.log(renkler.includes("Mavi")); // true
```

---

## 🔸 9. **`sort()`**

Diziyi sıralar (varsayılan: string’e göre).

```js
let sayilar = [10, 5, 20];
sayilar.sort(); // [10, 20, 5] → yanlış sonuç!
sayilar.sort((a, b) => a - b); // doğru: [5, 10, 20]
```

---

## 🔸 10. **`reverse()`**

Diziyi **ters çevirir**.

```js
let isimler = ["Ali", "Zeynep", "Can"];

isimler.reverse(); // ["Can", "Zeynep", "Ali"]
```

---

## 🔸 11. **`concat()`**

Dizileri **birleştirir**, yeni dizi döner.

```js
let a = [1, 2];
let b = [3, 4];

let c = a.concat(b); // [1, 2, 3, 4]
```

---

## 🔸 12. **`slice()`**

Belirli aralıktaki elemanlarla **yeni dizi oluşturur** (orijinal diziyi bozmaz).

```js
let meyveler = ["Elma", "Muz", "Kivi" , "Deneme","Furkan"];

let kesit = meyveler.slice(1, 3); // ["Muz", "Kivi" , "Deneme"]
```

---

## 🔸 13. **`splice()`**

Diziyi **değiştirir**: Eleman ekler, siler veya değiştirir.

```js
let dizi = ["a", "b", "c" , "d"];

	dizi.splice(0, 2, "x"); // 0. indexten 2 eleman sil, yerine "x" koy
console.log(dizi); // ["x", "c", "d"]
```

---

## 🎯 Kısa Özet Tablolar

| Metot       | Ne işe yarar?             | Yeni dizi döner mi? |
| ----------- | ------------------------- | ------------------- |
| `forEach()` | Elemanları tek tek işler  | ❌                   |
| `map()`     | Elemanları dönüştürür     | ✅                   |
| `filter()`  | Koşula göre eleman seçer  | ✅                   |
| `find()`    | İlk eşleşeni döner        | ❌                   |
| `reduce()`  | Tek bir değer üretir      | ❌                   |
| `some()`    | En az bir eşleşme var mı? | ❌ (true/false)      |
| `every()`   | Hepsi koşula uyuyor mu?   | ❌ (true/false)      |