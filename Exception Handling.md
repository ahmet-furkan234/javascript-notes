
**Exception Handling**, program çalışırken oluşabilecek hataların (exception) yakalanması ve uygun şekilde işlenmesi işlemidir.  
Bu sayede program beklenmedik hatalar yüzünden çökmez, kontrollü şekilde devam eder ya da kullanıcıya bilgi verir.

---

## 🔑 **JavaScript’te Hata Yakalama Yapısı**

### 1️⃣ **try...catch**

```js
try {
  // Hata çıkabilecek kod bloğu
  let x = y + 1; // y tanımlı değil, hata çıkar
} catch (error) {
  // Hata yakalandığında çalışacak kod
  console.log("Hata oluştu:", error.message);
}
```
### 2️⃣ **finally**

`try` veya `catch` bloklarından sonra mutlaka çalışacak kod bloğudur:

```js
try {
  console.log("Deneme");
} catch (e) {
  console.log("Hata");
} finally {
  console.log("Her durumda çalışır");
}
```

---

## 🎨 **Hata Fırlatma (throw)**

Kendi hatanı oluşturup fırlatabilirsin:

```js
function sayHello(name) {
  if (!name) {
    throw new Error("İsim parametresi gerekli!");
  }
  console.log("Merhaba " + name);
}

try {
  sayHello();
} catch(e) {
  console.log("Hata yakalandı:", e.message);
}
```

---

## ⚡ **Hata Türleri**

- **SyntaxError:** Kod yazım hatası (genelde try-catch ile yakalanamaz, çünkü kod çalışmaz)
- **ReferenceError:** Tanımlanmamış değişkene erişim
- **TypeError:** Yanlış tipte işlem
- **RangeError:** Geçersiz sayı aralığı
- **Custom Error:** Kendi oluşturduğun hata objeleri

---

## 🎯 **Exception Handling’in Önemi**

- Uygulama stabil çalışır, çökmez
- Hatalar loglanabilir, kullanıcı bilgilendirilebilir
- Hata durumlarında farklı akışlar sağlanabilir
- Debug ve bakım kolaylaşır

---

## 💡 **Özet**

|Yapı|Açıklama|Örnek|
|---|---|---|
|try|Hata oluşabilecek kod bloğu|`try { ... }`|
|catch|Hata yakalama bloğu|`catch (e) { ... }`|
|finally|Her durumda çalışacak blok|`finally { ... }`|
|throw|Hata fırlatma|`throw new Error("Hata")`|

---

## 💻 **Küçük Örnek**

```js
function bölme(a, b) {
  if (b === 0) throw new Error("Sıfıra bölme hatası!");
  return a / b;
}

try {
  console.log(bölme(10, 0));
} catch (e) {
  console.log("Hata:", e.message);
} finally {
  console.log("İşlem tamamlandı.");
}
```