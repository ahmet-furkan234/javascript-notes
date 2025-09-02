
Birden fazla işlemi sırayla yapmak istiyorsan, her `.then()` bloğunda bir sonraki işlemi tanımlarsın.

```js
ilkIslem()
  .then(ikinciIslem)
  .then(ucuncuIslem)
  .then(dorduncuIslem)
  .catch(hata => console.error("Hata:", hata));
```

Her adım bir öncekinin sonucunu alır.

---

## 🎯 Örnek: Zincirli İşlem Adımları

### Senaryo: Sipariş sistemi

1. Siparişi al
2. Hazırlamaya başla
3. Pişir
4. Teslim et

```js
function siparisAl() {
  return new Promise((resolve) => {
    setTimeout(() => {
      console.log("1️⃣ Sipariş alındı");
      resolve("Pizza");
    }, 1000);
  });
}

function hazirla(yemek) {
  return new Promise((resolve) => {
    setTimeout(() => {
      console.log(`2️⃣ ${yemek} hazırlanıyor`);
      resolve(yemek);
    }, 1000);
  });
}

function pisir(yemek) {
  return new Promise((resolve) => {
    setTimeout(() => {
      console.log(`3️⃣ ${yemek} pişiriliyor`);
      resolve(yemek);
    }, 1000);
  });
}

function teslimEt(yemek) {
  return new Promise((resolve) => {
    setTimeout(() => {
      console.log(`4️⃣ ${yemek} teslim edildi`);
      resolve("✅ Afiyet olsun!");
    }, 1000);
  });
}

// Zincirli kullanım:
siparisAl()
  .then(hazirla)
  .then(pisir)
  .then(teslimEt)
  .then((sonMesaj) => console.log(sonMesaj))
  .catch((hata) => console.error("Bir hata oluştu:", hata));
```

---

### 🧠 Avantajı Nedir?

- Callback hell (içe gömülü fonksiyon cehennemi) ortadan kalkar.
- Okunaklılık artar.
- Hata yönetimi kolaylaşır (tek bir `.catch()` ile tüm zinciri kontrol edebilirsin).

---

## 🔁 Zincir içinde dönüş değeri değiştirme

Her `.then()` içinde sadece değer değil, başka Promise de döndürebilirsin:

```js
new Promise((resolve) => resolve(1))
  .then((sayi) => {
    console.log("Adım 1:", sayi); // 1
    return sayi + 1;
  })
  .then((sayi) => {
    console.log("Adım 2:", sayi); // 2
    return new Promise((resolve) => setTimeout(() => resolve(sayi * 2), 1000));
  })
  .then((sayi) => {
    console.log("Adım 3:", sayi); // 4
  });
```

---

## 🚨 Hata Yönetimi Zincirde Nasıl Olur?

```js
new Promise((resolve, reject) => {
  reject("İlk adımda hata!");
})
.then(() => {
	console.log("Bu çalışmaz.");
})
.catch((hata) => {
    console.error("Hata yakalandı:", hata);
});
```

> `.catch()` zincirde herhangi bir yerde hata olursa onu yakalar.