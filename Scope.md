
JavaScript'te **kapsam (scope)**, bir değişkenin **nerede tanımlandığını ve nereden erişilebildiğini** belirler. Kapsam, kodun düzeni ve hatasız çalışması için çok önemlidir.

---

## 🔹 JavaScript’te 3 Ana Kapsam Türü

| Tür               | Açıklama                                                   |
| ----------------- | ---------------------------------------------------------- |
| 🔸 Global Scope   | Her yerden erişilebilir                                    |
| 🔸 Function Scope | Sadece tanımlandığı fonksiyon içinde geçerli               |
| 🔸 Block Scope    | `{}` süslü parantezler içinde geçerli (`let`, `const` ile) |

---

## ✅ 1. **Global Scope (Global Kapsam)**

- Her yerden erişilebilir.
- `var`, `let`, `const` ile dışarıda tanımlanırsa global olur.

```js
let mesaj = "Merhaba";

function selamla() {
  console.log(mesaj); // erişilir
}

selamla();
```

---

## ✅ 2. **Function Scope (Fonksiyon Kapsamı)**

- `var`, `let`, `const` ile fonksiyon içinde tanımlanan değişken sadece o fonksiyonda geçerlidir.
- `var` burada bloklara değil, sadece fonksiyonlara saygı duyar.

```js
function ornek() {
  var x = 10;
  console.log(x); // erişilir
}
console.log(x); // ❌ Hata: x tanımlı değil
```

---

## ✅ 3. **Block Scope (Blok Kapsamı)** → (`let`, `const` ile)

- `if`, `for`, `while`, `{}` gibi bloklar içinde tanımlanan `let` ve `const` sadece o blok içinde geçerlidir.

```js
if (true) {
  let a = 5;
  const b = 10;
  console.log(a, b); // erişilir
}
console.log(a); // ❌ Hata
```

> `var` kullanılsaydı blok dışına sızardı:

```js
if (true) {
  var x = 100;
}
console.log(x); // ✅ erişilir çünkü var blok kapsama saygı duymaz
```

---

## ⚠️ `var`, `let`, `const` Farkı Kapsamda Nasıl Görünür?

|Anahtar Kelime|Blok Kapsamı|Fonksiyon Kapsamı|Globalde Kullanım|
|---|---|---|---|
|`var`|❌ Yok|✅ Var|✅ Var|
|`let`|✅ Var|✅ Var|✅ Var|
|`const`|✅ Var|✅ Var|✅ Var|

---

## 🔸 Lexical Scope (Statik Kapsam)

JavaScript **lexical scoped** bir dildir, yani bir değişkene **nerede tanımlandığına göre** erişilir, **nerede çağrıldığına göre değil**.

```js
function disFonksiyon() {
  let mesaj = "Merhaba";

  function icFonksiyon() {
    console.log(mesaj); // ✅ dıştan içe erişim mümkün
  }

  icFonksiyon();
}
disFonksiyon();
```

>İçten dışa erişilebilir ama **dıştan içeri erişilemez**.


---

## 🔹 Özet

|Kapsam Türü|Tanımı|
|---|---|
|Global Scope|Tüm dosyada/geçerli scriptte geçerli|
|Function Scope|Sadece o fonksiyonda geçerli|
|Block Scope|Sadece `{}` içindeki alanda geçerli|
|Lexical Scope|Tanımlandığı konuma göre kapsam belirlenir|

---
