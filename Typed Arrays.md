
**Typed Arrays**, JavaScript’te **sabit türde ve sabit boyutta sayısal verileri bellekte verimli şekilde tutmaya yarayan özel veri yapılarıdır.**

- ES6 ile birlikte geldi.
- Performans gerektiren uygulamalarda (grafik, ses, video, WebGL, dosya işlemleri) kullanılır.
- Normal `Array`’lerden farklı olarak **tip güvenliği** ve **sabit uzunluk** sağlar.

---

## 📝 **Neden Typed Arrays?**

Normal JavaScript array’leri **her türlü veri tipini** tutabilir, ama:

- Bellek kullanımı esnektir (fazla yer kaplayabilir).
- Performans önemli durumlarda yetersiz kalabilir.

Typed Arrays, **aynı türden verileri arka arkaya ve sabit uzunlukta saklayarak hızlı işlem sağlar.**

---

## 🎨 **Typed Arrays Türleri**

|Typed Array Türü|Veri Tipi|Bit Sayısı|Açıklama|
|---|---|---|---|
|`Int8Array`|8-bit signed int|8|-128 ile 127 arası tamsayılar|
|`Uint8Array`|8-bit unsigned int|8|0 ile 255 arası pozitif tamlar|
|`Uint8ClampedArray`|8-bit unsigned clamped|8|0-255 arası, taşmalar engellenir|
|`Int16Array`|16-bit signed int|16|-32,768 ile 32,767 arası tamlar|
|`Uint16Array`|16-bit unsigned int|16|0 ile 65,535 arası pozitif tamlar|
|`Int32Array`|32-bit signed int|32|Daha geniş tam sayı aralığı|
|`Uint32Array`|32-bit unsigned int|32|Pozitif tam sayı|
|`Float32Array`|32-bit float|32|Tek duyarlıklı kayan nokta|
|`Float64Array`|64-bit float|64|Çift duyarlıklı kayan nokta|

---

## 💡 **Typed Arrays Nasıl Oluşturulur?**

### 1️⃣ **Yeni bir typed array oluşturma**


```js
const int8 = new Int8Array(4);  // 4 elemanlık boş Int8Array (tüm değerler 0)
console.log(int8); // Int8Array(4) [0, 0, 0, 0]
```

### 2️⃣ **Diziden typed array oluşturma**

```js
const nums = new Uint16Array([10, 20, 30]);
console.log(nums); // Uint16Array(3) [10, 20, 30]
```

### 3️⃣ **ArrayBuffer kullanarak oluşturma**

```js
const buffer = new ArrayBuffer(16); // 16 byte
const view = new Float32Array(buffer);
console.log(view.length); // 4 (çünkü her float32 4 byte)
```

---

## ⚙️ **Typed Arrays Özellikleri**

- **Uzunluk sabittir**: Oluşturulduktan sonra boyutu değişmez.
- **Tip garantilidir**: Sadece belirlenen veri tipinde veri tutar.
- **Bellekte arka arkaya saklanır**: Bu da performansı artırır.
- **ArrayBuffer ile birlikte kullanılır**: Buffer bellekteki ham veri, typed array ise o veriyi okuyan/yazan görünüm.

---

## 🎯 **Elemanlara Erişim**

```js
const arr = new Int16Array(3);
arr[0] = 1000;
arr[1] = 2000;
arr[2] = 3000;

console.log(arr[1]); // 2000
```

---

## 🧩 **Örnek Kullanım: Basit Float32Array**

```js
const floats = new Float32Array([0.5, 1.5, 2.5]);
floats[1] = 3.14;

console.log(floats); // Float32Array(3) [0.5, 3.14, 2.5]
```

---

## 📌 **ArrayBuffer ve Typed Arrays İlişkisi**

- **ArrayBuffer**: Ham ikili veri bloğu.
- **TypedArray**: Bu veriyi okuyan/yazan görünüm.

```js
const buffer = new ArrayBuffer(8); // 8 byte
const int32View = new Int32Array(buffer);
const int16View = new Int16Array(buffer);

int32View[0] = 42;
console.log(int16View[0]); // Bu 42'nin düşük 16 biti olur
```

---

## 💡 **Özet**

|Özellik|Açıklama|
|---|---|
|Tip garantisi|Sadece belirli tipte veri tutar|
|Sabit boyut|Oluşturulduktan sonra değişmez|
|Performans odaklı|Bellekte ardışık depolama|
|ArrayBuffer ile birlikte|Ham veriye erişim sağlar|
|Kullanım alanı|Grafik, ses, video, dosya, WebGL|

---

## 🔥 **Neden Typed Arrays Kullanılır?**

- Yüksek performans gereken uygulamalarda
- WebGL ve oyunlarda
- Ses/video işleme
- Binary dosya işlemlerinde