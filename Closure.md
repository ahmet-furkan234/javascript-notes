TkMatE, aşağıdaki anlatımı **doğrudan notlarına ekleyebileceğin**, akademik ama geliştirici bakış açısıyla hazırlanmış bir **Closure konu özeti** olarak yazıyorum.  
(JavaScript merkezli ama kavramsal anlatım.)

---

# 📌 Closure (Kapanım) Nedir?

**Closure**, bir fonksiyonun **tanımlandığı andaki lexical scope’u (kapsamı)** hatırlayarak, **o kapsam dışından bile erişilebilir kalmasıdır**.

👉 Kısaca:

> **Fonksiyon + Tanımlandığı çevredeki değişkenler = Closure**

---

## 🧠 Neden Closure Diye Ayrı Bir Kavram Var?

Normalde bir fonksiyon çalışıp bittiğinde:

- İçindeki **local değişkenler bellekten silinir**

Ama **closure varsa**:

- Fonksiyonun **referans verdiği değişkenler yaşamaya devam eder**    

Yani JS der ki:

> “Bu fonksiyon hâlâ kullanılıyor → ihtiyaç duyduğu scope’u yok edemem”

---

## 🔍 Temel Örnek

```js
function counter() {
  let count = 0;

  return function () {
    count++;
    console.log(count);
  };
}

const myCounter = counter();

myCounter(); // 1
myCounter(); // 2
myCounter(); // 3
```

### Burada Ne Oldu?

1. `counter()` çalıştı
2. `count = 0` oluşturuldu
3. İç fonksiyon **return edildi**
4. `counter()` bitti **AMA**
5. İç fonksiyon hâlâ `count` değişkenine **referans tutuyor**

📌 **Bu referans yüzünden `count` bellekten silinmez**

---

## 🧠 Kritik Nokta (En Çok Karıştırılan Yer)

```js
counter();      // SADECE bir kez çağrıldı
myCounter();    // tekrar tekrar çağrılan şey BU
```

❌ Yanlış düşünce:

> “Her myCounter() çağrısında counter çalışıyor”

✅ Doğru:

> `counter()` **1 kez çalıştı**,  
> dönen fonksiyon **aynı scope’u kullanmaya devam ediyor**

---

## 🧩 Lexical Scope ile İlişkisi

Closure = **Lexical Scope’un runtime’da korunmasıdır**

```js
function outer() {
  let x = 10;

  function inner() {
    console.log(x);
  }

  return inner;
}
```

- `inner`, **nerede çağrılırsa çağrılsın**
- `x`’i **outer’ın tanımlandığı yerden** alır

📌 **Çağrıldığı yer değil, TANIMLANDIĞI yer önemlidir**

---

## 🧠 “Fonksiyon Neden Obje Gibi Saklanıyor?”

JS’te:

- Fonksiyonlar **first-class object**’tir    

Yani:

- Değişkene atanabilir
- Parametre olarak geçilebilir
- Return edilebilir
- **Scope referanslarıyla birlikte saklanabilir**

```js
const fn = function () {
  let secret = 42;
  return () => secret;
};
```

Burada `fn`:

- Sadece bir kod bloğu değil
- **Kod + environment (scope referansı)**

---

## 📦 Closure Ne Sağlar?

### 1️⃣ Private Değişken (Encapsulation)

```js
function createUser() {
  let password = "123";

  return {
    check: (p) => p === password
  };
}
```

🔒 `password` dışarıdan erişilemez

---

### 2️⃣ State Saklama

```js
function createCounter() {
  let value = 0;
  return () => ++value;
}
```

State:

- Global değil
- Class değil
- Closure içinde

---

### 3️⃣ Factory Pattern

```js
function multiplier(factor) {
  return (n) => n * factor;
}

const double = multiplier(2);
const triple = multiplier(3);
```

---

## ⚠️ Dikkat Edilmesi Gerekenler

### 🔥 Memory Leak Riski

Closure:

- Scope’u **tuttuğu sürece**
- Bellek serbest bırakılmaz

```js
let fn;

function create() {
  let bigData = new Array(1000000);
  fn = () => bigData;
}
```

`fn` yaşadığı sürece `bigData` silinmez.

---

### 🔁 Loop İçinde Closure Tuzağı

```js
for (var i = 0; i < 3; i++) {
  setTimeout(() => console.log(i), 1000);
}
```

Çıktı:

```
3
3
3
```

📌 Çünkü:

- `var` → tek scope
- Closure **aynı `i`’yi tutar**

✅ Çözüm:

```js
for (let i = 0; i < 3; i++) {
  setTimeout(() => console.log(i), 1000);
}
```

---

## 🧠 Closure ≠ Class

|Closure|Class|
|---|---|
|Fonksiyon temelli|OOP temelli|
|Lightweight|Daha ağır|
|Private alan doğal|`#private` gerekir|
|Functional pattern|OOP pattern|

---

## 🧩 .NET / C# Karşılığı Var mı?

✔️ **Evet, var**

```csharp
Func<int> Counter()
{
    int count = 0;
    return () => ++count;
}
```

Ama:

- JS’te closure **dilin merkezinde**
- C#’ta daha kontrollü / sınırlı

---

## 📝 Kısa Özet (Notluk)

> Closure, bir fonksiyonun tanımlandığı lexical scope’u hatırlaması ve bu scope’un fonksiyon yaşadığı sürece bellekten silinmemesidir. Closure sayesinde private state, factory fonksiyonlar ve fonksiyonel programlama desenleri mümkün olur.
