""
Fonksiyon içinde `this`’in değeri **fonksiyonun nasıl çağrıldığına bağlıdır**. Yani fonksiyonun yazılış biçimi değil, çağrılış biçimi önemlidir.

---

### 1. **Normal Fonksiyonlarda (Non-strict mode)**

```js
function showThis() {
  console.log(this);
}
showThis(); // 👉 global nesne (Tarayıcıda: window, Node.js'te: global)
```

### 2. **Strict Mode ile**

```js
"use strict";

function showThis() {
  console.log(this);
}
showThis(); // 👉 undefined
```

Strict mode açıkken, `this` normal fonksiyonlarda **global yerine `undefined` olur**.

---

### 3. **Bir Nesne İçinden Çağrılırsa**

```js
const person = {
  name: "TkMatE",
  showName: function() {
    console.log(this.name);
  }
};

person.showName(); // 👉 "TkMatE"
```

- `this` burada `person` nesnesini gösterir. Yani fonksiyon **hangi nesne üzerinden çağrıldıysa**, `this` o nesneyi gösterir.

---

### 4. **Function'ı Referans Olarak Alırsan**

```js
const person = {
  name: "TkMatE",
  showName: function() {
    console.log(this.name);
  }
};

const fn = person.showName;
fn(); // 👉 undefined (veya global nesnede name yoksa)
```

- Fonksiyon **bir nesneden koparıldığında**, `this` artık o nesneyi göstermez. Tekrar bağlanması gerekir (`bind`, `call`, `apply` ile yapılır).
    

---

### 5. **Arrow Function İçinde `this`**

Arrow function'lar **kendi `this` değerini oluşturmaz**, dış bağlamdan (lexical scope) alır:

```js
const person = {
  name: "TkMatE",
  showName: () => {
    console.log(this.name);
  }
};

person.showName(); // 👉 undefined (çünkü arrow function dıştaki this'e bakar)
```

- Bu örnekte `this`, global nesneyi gösterir çünkü arrow function'ın kendi `this`'i yoktur.

---

### 6. **Event içinde `this`**

```js
document.querySelector("button").addEventListener("click", function() {
  console.log(this); // 👉 Tıklanan <button> öğesi
});
```

```js
document.querySelector("button").addEventListener("click", () => {
  console.log(this); // 👉 Arrow function olduğundan this dıştaki scope'u alır
});
```

---

## 🧠 Özet

|Ortam/Fonksiyon Şekli|`this` neyi gösterir?|
|---|---|
|Normal fonksiyon (non-strict)|Global nesne (`window` veya `global`)|
|Normal fonksiyon (strict)|`undefined`|
|Nesne içindeki fonksiyon|Çağıran nesne|
|Arrow function|Dış (lexical) bağlamdan `this` alır|
|`bind`, `call`, `apply` ile|Elle belirlenmiş `this`|
|DOM Event fonksiyonu (normal)|Olayı tetikleyen DOM öğesi|
