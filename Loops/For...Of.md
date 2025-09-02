
`for...of`, **diziler (arrays)** ve **diğer yinelenebilir (iterable)** yapılarda, her elemanı **doğrudan** almak için kullanılır.  
Sayaç yok, indeksle uğraşılmaz → sadece elemanın kendisiyle ilgilenilir.

---

## 🔹 Söz Dizimi (Syntax)

```js
for (let eleman of iterableYapi) {
  // eleman: her turda sıradaki değeri alır
}
```

>  `iterableYapi` → array, string, Map, Set gibi yinelenebilir yapılar

---

## 🔸 Dizi Örneği

```js
let meyveler = ["Elma", "Armut", "Muz"];

for (let meyve of meyveler) {
  console.log(meyve);
}
```

**Çıktı:**

```
Elma
Armut
Muz
```

---

## 🔸 String Örneği

```js
let kelime = "Merhaba";

for (let harf of kelime) {
  console.log(harf);
}
```

Çıktı:

```js
M
e
r
h
a
b
a
```

---

## 🔸 `Set` (tekrarsız küme) ile

```js
let sayilar = new Set([1, 2, 3, 3, 2]);

for (let s of sayilar) {
  console.log(s);
}
```

**Çıktı:**

```js
1
2
3
```

---

## 🔸 `Map` ile

```js
let kisiler = new Map([
  ["ad", "Ali"],
  ["yas", 25]
]);

for (let [anahtar, deger] of kisiler) {
  console.log(`${anahtar}: ${deger}`);
}
```

---

## 🔸 Ne Zaman `for...of` Kullanılır?

|Amaç|Tercih Et|
|---|---|
|Dizi, string, Set veya Map üzerinde gezinmek|✅ `for...of`|
|İndekse ihtiyaç yoksa|✅|
|İndeks gerekiyorsa (`i`, `j` gibi)|❌ `for` kullanılır|
