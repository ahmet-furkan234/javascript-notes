
Bir metot, bir nesnenin **özelliği olarak tanımlanan fonksiyondur**. Bu tür fonksiyonlar çağrıldığında `this`, o **metodu çağıran nesneyi** gösterir.

### 📌 Temel Tanım

```js
const person = {
  name: "TkMatE",
  sayHello() {
    console.log("Hello, I'm " + this.name);
  }
};

person.sayHello(); // Hello, I'm TkMatE
```

> Yukarıdaki örnekte `this.name`, `person.name` anlamına gelir.

---

## 📌 `this`, Yalnızca Çağrılma Şekline Göre Belirlenir

### 🔸 Doğrudan çağırma

```js
person.sayHello(); // this -> person
```

### 🔸 Atayarak çağırma (bağlam kaybı)

```js
const greet = person.sayHello;
greet(); // this -> undefined (strict modda), window (normalde)
```

> Çünkü `greet()` globalden çağrıldığı için `this` bağlamı kaybolur.

---

## 📌 Arrow Function Kullanımı (Yanlış bağlam)

```js
const person = {
  name: "Ersin",
  sayHi: () => {
    console.log(this.name); // undefined
  }
};

person.sayHi();
```

> ❌ `this` burada `person`’ı değil, **bir üst bağlamı** (genellikle `window`) referans alır.

---

## 📌 Çözüm: `function` kullan

```js
const person = {
  name: "TkMatE",
  sayHi() {
    console.log(this.name); // ✅ "TkMatE"
  }
};
```

---

## ⚠️ `this` Metot İçinde Kaybolabilir

### Problemli Senaryo:

```js
const user = {
  name: "TkMatE",
  printNameLater() {
    setTimeout(function () {
      console.log(this.name); // ❌ undefined
    }, 1000);
  }
};

user.printNameLater();
```

> setTimeout içinde `this`, global nesneye (ya da `undefined`) bağlanır.

---

## ✅ Çözüm 1: `self = this` yaklaşımı

```js
const user = {
  name: "TkMatE",
  printNameLater() {
    const self = this;
    setTimeout(function () {
      console.log(self.name); // ✅ "TkMatE"
    }, 1000);
  }
};
```

---

## ✅ Çözüm 2: Arrow function kullanmak

```js
const user = {
  name: "TkMatE",
  printNameLater() {
    setTimeout(() => {
      console.log(this.name); // ✅ "TkMatE"
    }, 1000);
  }
};
```

---

## ✅ Çözüm 3: `bind()` ile bağlamak

```js
const user = {
  name: "TkMatE",
  printNameLater() {
    setTimeout(function () {
      console.log(this.name);
    }.bind(this), 1000);
  }
};
```

---

## 📦 Örnek Uygulama: Kapsamı Koruma

```js
const counter = {
  count: 0,
  start() {
    setInterval(() => {
      this.count++;
      console.log(this.count);
    }, 1000);
  }
};

counter.start();
// 1
// 2
// 3 ...
```

> `this`, arrow function sayesinde `counter`’ı referans alır.

---

## 🧠 Özet

|Durum|`this` neyi gösterir?|
|---|---|
|Nesne metodu (`function`)|Metodu çağıran nesne|
|Arrow function|Üst bağlam (lexical scope)|
|`setTimeout`, `setInterval`|Global (`window`), ama arrow ile bağlanabilir|
|`bind`, `call`, `apply`|`this` açıkça belirtilir|

---

Devam etmek istersen:

- `this` + arrow function derinlemesine
    
- `bind`, `call`, `apply` farkları ve örnekler
    
- Class içinde `this` kullanımı
    

hangisiyle ilerleyelim TkMatE?