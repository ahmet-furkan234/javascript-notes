

Bir diziyi, nesneyi veya string’i **ayırmak** için kullanılır.

---

## 📌 Dizilerde Spread

```js
const dizi1 = [1, 2, 3];
const dizi2 = [4, 5];

const birlesik = [...dizi1, ...dizi2];

console.log(birlesik); // [1, 2, 3, 4, 5]
```

---
### 📌 Kopyalama (Shallow Copy)


```js
const orijinal = [10, 20, 30];
const kopya = [...orijinal];

console.log(kopya); // [10, 20, 30]
```

>   ⚠️ Not: Derin kopya (nested objelerde) yapmaz, sadece yüzeysel (shallow) kopyadır.

---

### 📌 String’i Karakterlerine Ayırma

```js
**const kelime = "merhaba";
const harfler = [...kelime];

console.log(harfler); // ["m", "e", "r", "h", "a", "b", "a"]
```

---

### 📌 Nesnelerde Spread

```js
const ogrenci = { ad: "Ali", yas: 22 };
const ekBilgi = { okul: "Üniversite" };

const yeniOgrenci = { ...ogrenci, ...ekBilgi };

console.log(yeniOgrenci); // { ad: "Ali", yas: 22, okul: "Üniversite" }
```

---

