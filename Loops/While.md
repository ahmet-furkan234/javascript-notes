
`while`, **koşul doğru olduğu sürece** döner. `for` döngüsüne göre daha esnektir ama dikkatli kullanılmalıdır çünkü sonsuz döngüye girme riski vardır.

---

## 🔹 Söz Dizimi (Syntax)

```js
while (koşul) {
  // Koşul doğruysa bu blok tekrar tekrar çalışır
}
```

---

## 🔸 Basit Örnek

```js
let i = 0;

while (i < 5) {
  console.log("i:", i);
  i++;
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

> 🔍 **Dikkat:** Sayaç (`i++`) arttırılmazsa sonsuz döngü olur.

---

## 🔸 Geriye Doğru Sayma

```js
let x = 3;

while (x > 0) {
  console.log(x);
  x--;
}
```

---
## 🔸 Kullanıcıdan Değer Alma (örnek) 


```js
let sifre = "";

while (sifre !== "1234") {
  sifre = prompt("Şifreyi girin:");
}

alert("Giriş başarılı!");
```

---

## 🔸 `break` ve `continue`



```js
let i = 0;

while (i < 5) {
  i++;
  if (i === 3) continue; // 3’ü atla
  if (i === 5) break;    // 5’e gelince dur
  console.log(i);
}
```

---

## 🔸 Ne Zaman `while` Kullanılır?

|Durum|Tercih|
|---|---|
|Döngü sayısı baştan belli **değilse**|✅ `while`|
|Koşula göre döngü **içeriden kontrol edilecekse**|✅ `while`|
|Sayaçlı, sabit tekrar gerekiyorsa|⚠️ `for` tercih edilir|