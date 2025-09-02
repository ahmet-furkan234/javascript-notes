
Birden fazla değeri **tek bir değişkende toplar**.  
Fonksiyon parametrelerinde ya da destructuring içinde kullanılır.

---

## 📌 Fonksiyon Parametrelerinde Rest

```js
function topla(...sayilar) {
  return sayilar.reduce((toplam, s) => toplam + s, 0);
}

console.log(topla(1, 2, 3));     // 6
console.log(topla(5, 10, 20, 15)); // 50
```

📌 `...sayilar`, gelen tüm parametreleri bir **dizi** gibi yakalar.

---

### 📌 Destructuring ile Rest

```js
const [ilk, ikinci, ...kalanlar] = [1, 2, 3, 4, 5];

console.log(ilk);      // 1
console.log(ikinci);   // 2
console.log(kalanlar); // [3, 4, 5]
```

---

### 📌 Nesnede Rest

```js
const { ad, ...digerleri } = { ad: "Zeynep", yas: 23, sehir: "Ankara" };

console.log(ad);        // Zeynep
console.log(digerleri); // { yas: 23, sehir: "Ankara" }
```
