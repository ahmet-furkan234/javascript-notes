
- Virgül operatörü `,` **birden fazla ifadeyi tek bir ifade gibi yazmana izin verir.**
- Soldan sağa doğru tüm ifadeleri çalıştırır, **son ifadenin değerini döner**.
- Genellikle **birden fazla işlemi tek satırda yapmak** veya **for döngüsünde birden fazla değişken kullanmak** için kullanılır.

---

## 🔑 **Temel Kullanımı**

```js
let x = (1, 2, 3);
console.log(x); // 3
```

Burada:

- Önce `1`, sonra `2`, sonra `3` değerlendirilir.
- Sonuç olarak `3` atanır.

---

## 🎨 **Örnekler**

### 1️⃣ **Birden fazla ifadeyi tek satırda çalıştırmak**

```js
let a = 5;
let b = 10;
let c = (a++, b++, a + b);

console.log(a); // 6
console.log(b); // 11
console.log(c); // 17 (6 + 11)
```

### 2️⃣ **For döngüsünde birden fazla ifade**

```js
for (let i = 0, j = 10; i < 5; i++, j--) {
  console.log(i, j);
}
```

**Çıktı:**

```text
0 10
1 9
2 8
3 7
4 6
```

### 3️⃣ **Fonksiyonlarda virgül operatörü ile işlem**

```js
function test() {
  return (console.log("Birinci"), console.log("İkinci"), 42);
}

let result = test(); 
console.log(result); // 42
```

---

## ⚡ **Dikkat Edilmesi Gerekenler**

- Virgül operatörü **okunabilirliği düşürebilir**, çok karmaşık ifadelerde tavsiye edilmez.
- Değişkenleri ayrı satırlarda tanımlamak çoğunlukla daha temizdir.
- En çok **for döngülerinde** ve **birden çok ifadeyi tek satırda çalıştırmak için** kullanılır.

---

## 💡 **Özet**

|Özellik|Açıklama|
|---|---|
|`,` operatorü|Birden fazla ifadeyi tek satırda yazma|
|İşleyiş|Soldan sağa tüm ifadeleri çalıştırır, sonuncunun sonucunu döner|
|Kullanım alanları|For döngü, çoklu işlem, kısa ifadeler|