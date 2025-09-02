
`"use strict";` ifadesi, JavaScript'te **Strict Mode** (Sıkı Mod) olarak bilinen bir özelliği etkinleştirir. Bu mod, JavaScript’in daha **güvenli, temiz ve hataya karşı duyarlı** bir şekilde çalışmasını sağlar.

---

## 🔍 "use strict"; Ne İşe Yarar?

### ✅ Hataları erken yakalar

Normalde JavaScript bazı hataları sessizce kabul eder. `"use strict";` sayesinde bu tür hatalar derhal fırlatılır.

### ✅ Değişken tanımlamadan kullanımı engeller

```js
"use strict";
x = 5; // ❌ ReferenceError: x is not defined
```

Normal modda bu hata vermez ama strict modda **tanımsız değişken kullanımı yasaktır.**

### ✅ Bazı kötü sözdizimlerini engeller

```js
"use strict";
with (obj) {
  // kodlar
} // ❌ SyntaxError: Strict modda "with" kullanılamaz
```

### ✅ Global nesneye yanlışlıkla yazmayı engeller

```js
"use strict";
function myFunc() {
  this.message = "Hello"; // ❌ Global değilse hata verebilir
}
```

### ✅ `eval()` ile oluşturulan değişkenler sadece eval() bloğu içinde geçerli olur

```js
"use strict";
eval("var x = 2;");
console.log(x); // ❌ ReferenceError: x is not defined
```

---

## 🔧 Nasıl Kullanılır?

### Global Olarak (Dosyanın en üstüne yazılır)

```js
"use strict";

function test() {
  // burada strict mod aktif
}
```

### Fonksiyon Seviyesinde (Yalnızca bu fonksiyonda geçerli)

```js
function test() {
  "use strict";
  // sadece burada sıkı mod aktif
}
```

---

## ⚠️ Notlar

- `"use strict";` bir ifade (expression) olduğundan **mutlaka ilk satıra yazılmalıdır**, aksi takdirde etkisiz olur.
    
- ES6 (ES2015) ile birlikte **modül dosyalarında otomatik olarak strict mode aktiftir**. Yani `import/export` kullanıyorsan ayrıca yazmana gerek yoktur.
    

---

## 🎯 Ne Zaman Kullanmalısın?

- Yeni projelerde **her zaman** kullanılması önerilir.
    
- Daha güvenli, hatasız ve düzenli JavaScript kodu yazmak için en iyi uygulamalardan biridir.
    

---

İstersen örneklerle devam edebilirim.