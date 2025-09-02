
`do...while`, JavaScript'te en az **bir kere** çalışması **garantili** olan döngüdür.   Önce kod bloğu çalışır, sonra koşul kontrol edilir.

---

## 🔹 Söz Dizimi (Syntax)

```js
do {
  // Bu kod en az 1 kez çalışır
} while (koşul);
```

---

## 🔸 Basit Örnek

```js
let i = 0;

do {
  console.log("i:", i);
  i++;
} while (i < 5);
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

## 🔸 Farkı Gösterelim (`while` vs `do...while`)

```js
let x = 10;

while (x < 5) {
  console.log("while çalıştı"); // çalışmaz
}

do {
  console.log("do...while çalıştı"); // en az 1 kez çalışır
} while (x < 5);
```

Çıktı  :

```js
do...while çalıştı
```

---

## 🔸 Kullanıcı Girişi Örneği

```js
let isim;

do {
  isim = prompt("İsminizi girin:");
} while (!isim); // isim boşsa tekrar sor

console.log("Merhaba " + isim);

```

---

## 🔸 Nerelerde Kullanılır?

- Kullanıcının **en az bir kez** veri girmesi gereken durumlar
- Menü sistemleri
- Şifre doğrulama, tekrar sorulacak alanlar

---

## 🔸 `break` ve `continue` ile

```js
let i = 0;

do {
  i++;
  if (i === 2) continue; // 2 atlanır
  if (i === 4) break;    // 4’te durur
  console.log(i);
} while (i < 5);
```

Çıktı:

```js
1
3
```
