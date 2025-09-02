
`for` döngüsü, **belirli sayıda tekrar** gerektiğinde en çok kullanılan döngüdür.

---

## 🔹 Söz Dizimi (Syntax)


```js
for (başlangıç; koşul; artış)
{   
// Her turda çalışacak kodlar 
}
```

| Bölüm       | Görevi                                                      |
| ----------- | ----------------------------------------------------------- |
| `başlangıç` | Döngü sayacını tanımlar (genelde `let i = 0`)               |
| `koşul`     | Döngü çalışmaya devam edecek mi? (true olduğu sürece döner) |
| `artış`     | Her döngü sonunda sayaç değeri artırılır veya azaltılır     |

---

## 🔸 Basit Örnek

```js
for (let i = 0; i < 5; i++) {
  console.log("i:", i);
}
```

Çıktı:

```js
i: 0
i: 1
i: 2
i: 3
i: 4
```

---

## 🔸 Geriye Doğru Sayma

```js
for (let i = 5; i > 0; i--) {
  console.log(i);
}
```

---
## 🔸 Dizi Üzerinde Dönme

```js
let meyveler = ["Elma", "Armut", "Muz"];

for (let i = 0; i < meyveler.length; i++) {
  console.log(meyveler[i]);
}
```

---

## 🔸 İç içe `for` Döngüleri

```js
for (let i = 1; i <= 3; i++) {
  for (let j = 1; j <= 2; j++) {
    console.log(`i: ${i}, j: ${j}`);
  }
}
```

---

## 🔸 `break` ve `continue`

```js
// break → Döngüyü tamamen durdurur
for (let i = 0; i < 5; i++) {
  if (i === 3) break;
  console.log(i);
}

// continue → Sadece o turu atlar
for (let i = 0; i < 5; i++) {
  if (i === 2) continue;
  console.log(i);
}

```

---

## 📌 Nerelerde Kullanılır?

- Sayfa numaralama
- Dizi veya liste üzerinden geçmek
- Tekrar eden işlemler
- İç içe yapılarla tablo veya çarpım tablosu oluşturmak

---

