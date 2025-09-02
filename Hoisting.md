
**Hoisting**, JavaScript’in değişken ve fonksiyon bildirimlerini **derleme aşamasında (kod çalıştırılmadan önce)** belleğe “yukarı taşır” gibi davranmasıdır.

👉 **Yani, değişken ve fonksiyon bildirimleri kodun en üstüne taşınmış gibi kabul edilir.**  
👉 Bu yüzden, tanımlamadan önce değişken veya fonksiyonlara erişmeye çalıştığında beklenmedik davranışlarla karşılaşabilirsin.

---

## 📝 **Değişkenlerde Hoisting**

### `var`

```js
console.log(a); // undefined
var a = 5;
console.log(a); // 5
```

> `var a` bildirimi yukarı taşındı, ama **değer ataması taşınmadı.**
> 
> JavaScript bunu şöyle görür:

```c#
var a;
console.log(a); // undefined
a = 5;
console.log(a); // 5
```

---

### `let` ve `const`

```js
console.log(b); // ReferenceError: Cannot access 'b' before initialization
let b = 10;
let ve const bildirimleri de hoist edilir ama “Temporal Dead Zone (TDZ)” denen bir bölgede tutulur.
TDZ içinde değişkene erişmeye çalışırsan hata alırsın.
```

---

## 📝 **Fonksiyonlarda Hoisting**

### Fonksiyon bildirimleri (function declarations)

```js
greet(); // "Merhaba!"

function greet() {
  console.log("Merhaba!");
}
```

>Fonksiyon bildirimleri tamamen yukarı taşınır, tanımlamadan önce çağırabilirsin.

---

### Fonksiyon ifadeleri (function expressions)

```js
sayHello(); // TypeError: sayHello is not a function

var sayHello = function() {
  console.log("Selam!");
};
```

---
## 🎨 **Özet**

|Bildirim Türü|Hoist Edilir mi?|Başlangıçta Değer?|
|---|---|---|
|`var`|✅|`undefined`|
|`let`, `const`|✅ (TDZ içindedir)|Erişim hatası (ReferenceError)|
|**Fonksiyon Bildirimi**|✅|Fonksiyon tanımı ile hoist edilir|
|**Fonksiyon İfadesi**|✅ (değişken hoist edilir)|`undefined` olur, çağrı hatası verir|

---

## 📌 **Kafanda tutman gerekenler**

✅ **Değişkenlerin sadece bildirim kısmı hoist edilir, atama kısmı edilmez.**  
✅ **Fonksiyon bildirimleri tam olarak hoist edilir, önce çağırabilirsin.**  
✅ **let ve const TDZ yüzünden tanımlamadan önce erişilemez.**

---

## 🎯 **İpucu**

👉 Değişken ve fonksiyonlarını daima **kullanmadan önce tanımla** ki hoisting yüzünden hata yapma!