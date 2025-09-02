
JavaScript’te bazı işlemleri **belirli bir süre sonra** veya **belirli aralıklarla** çalıştırmak için zamanlayıcı fonksiyonlar kullanılır.

İki temel zamanlayıcı vardır:

| Zamanlayıcı   | Açıklama                                         |
| ------------- | ------------------------------------------------ |
| `setTimeout`  | Belirli bir süre sonra **bir defa** çalıştırır   |
| `setInterval` | Belirli aralıklarla **tekrar tekrar** çalıştırır |

---

## 📌 1. `setTimeout()`

Belirli bir süre (milisaniye cinsinden) geçtikten sonra **bir kez** bir fonksiyonu çalıştırır.

### Söz Dizimi:

```js
setTimeout(callback, süre);
```

### Örnek:


```js
setTimeout(() => {   
	console.log("3 saniye sonra çalıştı"); 
}, 3000);
```

---

## ⛔ `clearTimeout()`

Bir `setTimeout` işlemini iptal eder.

### Örnek:

```js
let zamanlayici = setTimeout(() => {
  console.log("Bu yazı yazılmayacak");
}, 3000);

clearTimeout(zamanlayici); // iptal eder
```

---

## 🔁 2. `setInterval()`

Belirli aralıklarla **tekrar tekrar** bir fonksiyonu çalıştırır.

### Söz Dizimi:

```js
setInterval(callback, süre);
```
### Örnek:

```js
setInterval(() => {
  console.log("Her 2 saniyede bir çalışır");
}, 2000);
```

---

## ⛔ `clearInterval()`

Bir `setInterval` işlemini iptal eder.

```js
let sayaç = 0;
let intervalID = setInterval(() => {
  sayaç++;
  console.log(`Sayaç: ${sayaç}`);
  if (sayaç === 5) {
    clearInterval(intervalID); // durdur
    console.log("Durduruldu");
  }
}, 1000);
```

---

## 🎯 Notlar:

- Süreler **milisaniye (ms)** cinsindendir. 1000 ms = 1 saniye
- `setTimeout` ve `setInterval` asenkron çalışır (event loop ile çalışır).
- Uzun aralıklarla çalışan işlemleri yönetmek için `clearTimeout` ve `clearInterval` kullanmak önemlidir.

---
## 🧪 Mini Uygulama: Geri Sayım

```js
let kalan = 5;
let geriSay = setInterval(() => {
  console.log(kalan);
  kalan--;
  if (kalan < 0) {
    clearInterval(geriSay);
    console.log("Süre doldu ⏰");
  }
}, 1000);
```
