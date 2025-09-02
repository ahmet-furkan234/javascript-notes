
- `async`: Bir fonksiyonu **asenkron hale getirir**. Bu fonksiyon otomatik olarak bir `Promise` döner.
- `await`: Sadece `async` fonksiyonu içinde kullanılır. **Bir Promise'in çözülmesini (resolve edilmesini) bekler.** Kodu duraklatır ve sonuç gelene kadar diğer işlemler devam eder (bloklamaz).

---


## 🔧 Temel Kullanım

```js
function bekle() {
  return new Promise(resolve => {
    setTimeout(() => {
      resolve("3 saniye geçti");
    }, 3000);
  });
}

async function basla() {
  console.log("⏳ Bekleniyor...");
  const sonuc = await bekle();
  console.log("✅", sonuc);
}

basla();
```

> `await bekle()` satırı çalışana kadar beklenir ama **diğer işlemler engellenmez** (non-blocking).

---

## 🎯 Promise Zincirinin `async/await` ile Yazımı

### Önceki Promise Zinciri:


```js
siparisAl()
  .then(hazirla)
  .then(pisir)
  .then(teslimEt)
  .then((mesaj) => console.log(mesaj))
  .catch((hata) => console.error(hata));
```

Aynı işlem `async/await` ile:

```js
async function siparisSureci() {
  try {
    const yemek = await siparisAl();
    await hazirla(yemek);
    await pisir(yemek);
    const sonuc = await teslimEt(yemek);
    console.log(sonuc);
  } catch (err) {
    console.error("🚨 Hata:", err);
  }
}

siparisSureci();
```

> 📌 Çok daha okunabilir ve mantıksal sıraya yakın değil mi?

---
## 🔁 await Ne Döner?

`await` kullandığında, `Promise`'in **çözülmüş (resolved)** değerini verir.

```js
const sonuc = await Promise.resolve(42);
console.log(sonuc); // 42
```

---

## ⚠️ Hataları try/catch ile Yakala

`await` ile çalışan bir `Promise` hata fırlatırsa (reject olursa), bu hata `try/catch` ile yakalanmalıdır:

```js
async function hataOrnegi() {
  try {
    const sonuc = await Promise.reject("Bir şeyler ters gitti");
    console.log(sonuc); // çalışmaz
  } catch (hata) {
    console.error("Hata:", hata);
  }
}
```


---

## 🆚 Promise vs async/await Kıyas

| Özellik           | Promise Zinciri          | async/await                |
| ----------------- | ------------------------ | -------------------------- |
| Okunabilirlik     | Orta                     | Yüksek                     |
| Hata Yönetimi     | `.catch()`               | `try/catch`                |
| Karmaşık işlemler | Daha karışık olabilir    | Daha temiz                 |
| Uygulama          | Her yerde kullanılabilir | Sadece `async` fonksiyonda |
