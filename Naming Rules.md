
JavaScript’te değişken, fonksiyon, sınıf ve sabit adlarını yazarken belli kurallara ve iyi uygulamalara uyman kodunun **okunabilirliğini** ve **bakımını** kolaylaştırır.

---

### ✅ **Genel Kurallar**

1️⃣ **Harf, `$`, `_` ile başlar. Sayıyla başlayamaz.**

```js
let name;     // doğru
let _name;    // doğru
let $name;    // doğru
let 1name;    // ❌ yanlış (sayı ile başlayamaz)
```

2️⃣ **Büyük küçük harf duyarlıdır**

```js
let value = 10;
let Value = 20;

console.log(value); // 10
console.log(Value); // 20
```

> `value` ve `Value` iki farklı değişkendir.

3️⃣ **JavaScript anahtar kelimeleri kullanılamaz**

let let = 5;     // ❌ yanlış
let var = 10;    // ❌ yanlış

> `let`, `var`, `const`, `if`, `else`, `function` gibi kelimeleri değişken/fonksiyon adı yapamazsın.

---

### 📝 **İsimlendirme Stilleri**

#### 🌱 **camelCase (değişken, fonksiyon)**

👉 Küçük harfle başlar, her yeni kelimenin ilk harfi büyük olur.

```js
let firstName = "TkMatE";
function getUserName() { ... }
```

✅ **JavaScript’te en yaygın stil.**

---

#### 🌳 **PascalCase (sınıf ve constructor)**

👉 Her kelimenin baş harfi büyük olur.

```js
class StudentRecord { ... }
function MyComponent() { ... }
```

✅ **Sınıf ve özel yapıların adı bu şekilde olur.**

---

#### 🌵 **UPPER_SNAKE_CASE (sabitler/const’lar)**

👉 Bütün harfler büyük, kelimeler `_` ile ayrılır.

```js
const MAX_SIZE = 100;
const API_KEY = "abc123";
```

✅ **Sabit değerler için önerilir.**

---

### 💡 **Kötü örnekler**

❌ Anlamsız isimler

```js
let x = 10;  // neyi temsil ediyor belli değil
```

❌ Karmaşık ve okunmaz isimler

```js
let getusernameofuser = "TkMatE"; // zor okunur
```

---

### ✨ **İyi örnekler**

✅ Anlamlı ve okunur

```js
let userName = "TkMatE";
let userAge = 30;
```

✅ Fonksiyon isimleri genelde bir eylemi belirtir

```js
function calculateScore() { ... }
function sendEmail() { ... }
```

---

## ⚡ **İpucu**

👉 Değişken ve fonksiyon isimlerini **anlamlı, kısa ve açık** tut.  
👉 Kodunu okuyan biri sadece isme bakarak ne işe yaradığını anlayabilsin.  
👉 Tutarlı bir stil seç ve projede aynı stili kullan!

---

## 🎯 **Özet Tablo**

| Nerede kullanılır?  | Stil             | Örnek                     |
| ------------------- | ---------------- | ------------------------- |
| Değişken            | camelCase        | `userName`, `totalPrice`  |
| Fonksiyon           | camelCase        | `getUserData`, `sendMail` |
| Sınıf / Constructor | PascalCase       | `UserAccount`, `Product`  |
| Sabit / Const       | UPPER_SNAKE_CASE | `MAX_LENGTH`, `API_URL`   |