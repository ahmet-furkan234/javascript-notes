
`this`, JavaScript'te **çalışma zamanında** belirlenen bir bağlamı ifade eder. Bulunduğu fonksiyonu veya metodu **hangi nesne çağırıyorsa**, `this` ona referans verir.

---

## 📌 1. Global Scope (Küresel Bağlam)

```js
console.log(this); // Browser'da: Window, Node.js'de: global
```

---

## 📌 2. Fonksiyon İçinde

```js
function show() {
  console.log(this);
}
show(); // Browser'da: Window, strict modda: undefined
```

> `this`, normal fonksiyonlarda **global nesneyi** (browser'da `window`) gösterir.

---

## 📌 3. Strict Mode

```js
"use strict";
function show() {
  console.log(this);
}
show(); // undefined
```

> `strict mode` aktifse, `this` globali göstermez, `undefined` olur.

---

## 📌 4. Nesne Metodu İçinde

```js
const user = {
  name: "TkMatE",
  showName() {
    console.log(this.name);
  }
};

user.showName(); // "TkMatE"
```

> `this`, **metodu çağıran nesneyi** işaret eder.

---

## 📌 5. Arrow Function İçinde

```js
const user = {
  name: "TkMatE",
  showName: () => {
    console.log(this.name);
  }
};

user.showName(); // undefined
```

> ⚠️ Arrow function'larda `this`, **kendi bağlamını almaz**, bir üst bağlamdan alır (lexical `this`).

---

## 📌 6. Constructor Function

```js
function Person(name) {
  this.name = name;
}
const p1 = new Person("Ersin");
console.log(p1.name); // "Ersin"
```

> `this`, `new` ile oluşturulan yeni nesneyi işaret eder.

---

## 📌 7. `call`, `apply`, `bind` ile `this` Değiştirme

```js
function greet() {
  console.log(`Hello, ${this.name}`);
}
const user = { name: "TkMatE" };

greet.call(user);  // Hello, TkMatE
greet.apply(user); // Hello, TkMatE
const bound = greet.bind(user);
bound();           // Hello, TkMatE
```

- `call`: Fonksiyonu hemen çalıştırır, `this` değerini belirler.
    
- `apply`: `call` ile aynı, sadece argümanları dizi olarak alır.
    
- `bind`: Yeni bir fonksiyon döndürür, `this` kalıcı olur.
    

---

## 📌 8. Event Listener içinde `this`

```js
const button = document.querySelector("button");
button.addEventListener("click", function () {
  console.log(this); // <button> elementini gösterir
});

button.addEventListener("click", () => {
  console.log(this); // dış bağlamı (genelde window) gösterir
});
```

---

## 📌 9. Class İçinde `this`

```js
class User {
  constructor(name) {
    this.name = name;
  }

  sayHi() {
    console.log(`Hi, I'm ${this.name}`);
  }
}

const u = new User("TkMatE");
u.sayHi(); // Hi, I'm TkMatE
```

> `this`, sınıfa ait olan örneği temsil eder.

---

## ✅ Özet Tablosu

|Durum|`this` Ne Gösterir?|
|---|---|
|Global scope|`window` (browser), `global` (Node.js)|
|Normal fonksiyon|Global (strict modda `undefined`)|
|Metot|O metodu çağıran nesne|
|Arrow function|Üst bağlamdaki `this`|
|Constructor (`new`)|Yeni oluşturulan nesne|
|Event Listener (normal)|O elementi|
|Event Listener (arrow)|Üst bağlam|
|`call`, `apply`, `bind`|Elle belirlenen nesne|
|Class içi metot|Sınıfın oluşturulan örneği (`instance`)|

---

İstersen bu bilgileri küçük bir örnek uygulama haline getirebiliriz ya da `bind`, `call`, `apply` konularını daha derinlemesine inceleyebiliriz. Nasıl devam edelim?