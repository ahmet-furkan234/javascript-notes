
- JavaScript’te hata (exception) bilgilerini taşımak için kullanılan **standart nesnelerdir**.
- Hata mesajı, adı, yığını (stack trace) gibi bilgiler içerir.
- `throw` ile genellikle `Error` nesnesi veya alt türleri fırlatılır.

---

## 🔑 **Temel Error Nesnesi Oluşturma**

```js
const err = new Error("Bir hata oluştu!");
console.log(err.name);    // "Error"
console.log(err.message); // "Bir hata oluştu!"
console.log(err.stack);   // Hatanın oluştuğu yeri gösteren iz (stack trace)
```

---

## 🎨 **Error Object Türleri**

JavaScript’te bazı hazır hata tipleri vardır:

|Hata Türü|Açıklama|
|---|---|
|`Error`|Genel hata sınıfı|
|`ReferenceError`|Tanımsız değişkene erişim|
|`TypeError`|Yanlış türde işlem|
|`SyntaxError`|Yazım (sentaks) hatası|
|`RangeError`|Geçersiz sayı aralığı (örn: dizin dışı)|
|`URIError`|URI ile ilgili hatalar|

---

## ⚡ **Error Nesnesi Fırlatma Örneği**

```js
function divide(a, b) {
  if (b === 0) {
    throw new Error("Sıfıra bölme hatası!");
  }
  return a / b;
}

try {
  divide(10, 0);
} catch (error) {
  console.log(error.name);    // "Error"
  console.log(error.message); // "Sıfıra bölme hatası!"
  console.log(error.stack);   // Hatanın çağrıldığı yer
}
```

---

## 🎯 **Özel (Custom) Error Sınıfı Oluşturma**

```js
class ValidationError extends Error {
  constructor(message) {
    super(message); // Error sınıfının constructor'ını çağır
    this.name = "ValidationError"; // Hata adı
  }
}

try {
  throw new ValidationError("Geçersiz giriş!");
} catch (err) {
  console.log(err.name);    // "ValidationError"
  console.log(err.message); // "Geçersiz giriş!"
}
```

---

## 📌 **Error Nesnesi Özellikleri**

|Özellik|Açıklama|
|---|---|
|`name`|Hata türü adı (ör. "Error")|
|`message`|Hata mesajı|
|`stack`|Hata oluşan çağrı yığını (trace)|

---

## 💡 **Neden Error Object Kullanmalıyız?**

- Hataları standart ve tutarlı şekilde yönetmek için.
- Hata mesajını, türünü ve yığın bilgisini kolayca almak için.
- Özelleştirilmiş hata türleri oluşturup daha anlamlı hatalar yapabilmek için.

---

## 💻 **Kısa Örnek**

```js
try {
  throw new TypeError("Yanlış türde parametre!");
} catch (err) {
  console.log(err.name);    // "TypeError"
  console.log(err.message); // "Yanlış türde parametre!"
  console.log(err.stack);
}
```