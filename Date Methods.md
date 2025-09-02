
JavaScript’te `Date` nesnesi, tarih ve saat bilgisiyle çalışmak için kullanılır. Bu nesneyle hem **şu anki tarihi** alabilir hem de **özelleştirilmiş tarih** oluşturabiliriz.

---

## 🛠️ 1. `Date` Nesnesi Oluşturma


```js
let simdi = new Date();                         // Şu anki tarih ve saat
let tarih1 = new Date("2023-12-31");           // ISO formatında tarih
let tarih2 = new Date(2024, 0, 15);            // Yıl, Ay (0–11), Gün → 15 Ocak 2024
let tarih3 = new Date(2024, 5, 8, 14, 30);     // Yıl, Ay, Gün, Saat, Dakika
```

📌 Not: Aylar **0'dan başlar** (0 = Ocak, 11 = Aralık)

---

## 📤 2. Tarih Bilgilerini Alma (Getter Methods)

| Metot                | Açıklama                         | Örnek           |
| -------------------- | -------------------------------- | --------------- |
| `.getFullYear()`     | Yılı döner                       | `2025`          |
| `.getMonth()`        | Ayı döner (0–11)                 | `5` → Haziran   |
| `.getDate()`         | Gün (1–31)                       | `8`             |
| `.getDay()`          | Haftanın günü (0–6) → Pazar = 0  | `6` → Cumartesi |
| `.getHours()`        | Saat (0–23)                      | `14`            |
| `.getMinutes()`      | Dakika                           | `30`            |
| `.getSeconds()`      | Saniye                           | `12`            |
| `.getMilliseconds()` | Milisaniye                       | `654`           |
| `.getTime()`         | 1 Ocak 1970'ten bu yana geçen ms | `1724823823456` |

---

## 📥 3. Tarih Bilgilerini Ayarlama (Setter Methods)

| Metot                  | Açıklama             |
| ---------------------- | -------------------- |
| `.setFullYear(yil)`    | Yılı ayarlar         |
| `.setMonth(ay)`        | Ayı ayarlar (0–11)   |
| `.setDate(gun)`        | Günü ayarlar         |
| `.setHours(saat)`      | Saati ayarlar        |
| `.setMinutes(dakika)`  | Dakikayı ayarlar     |
| `.setSeconds(saniye)`  | Saniyeyi ayarlar     |
| `.setMilliseconds(ms)` | Milisaniyeyi ayarlar |

---

## 🧾 4. Tarihi Yazıya Çevirme

| Metot                   | Açıklama         | Örnek                                 |
| ----------------------- | ---------------- | ------------------------------------- |
| `.toString()`           | Tam tarih & saat | `"Sat Jun 08 2025 14:20:00 GMT+0300"` |
| `.toDateString()`       | Sadece tarih     | `"Sat Jun 08 2025"`                   |
| `.toTimeString()`       | Sadece saat      | `"14:20:00 GMT+0300"`                 |
| `.toLocaleDateString()` | Bölgesel tarih   | `"8.6.2025"`                          |
| `.toLocaleTimeString()` | Bölgesel saat    | `"14:20:00"`                          |
| `.toISOString()`        | ISO 8601 formatı | `"2025-06-08T11:20:00.000Z"`          |

---

## ⏱️ 5. Tarihler Arası Fark (ms)

```js
let t1 = new Date("2025-06-08");
let t2 = new Date("2025-06-01");

let farkMs = t1 - t2;
let farkGun = farkMs / (1000 * 60 * 60 * 24); // ms → gün
console.log(`Fark: ${farkGun} gün`); // 7 gün
```

---

## 🧪 Mini Örnek: Yaş Hesaplama

```js
function yasHesapla(dogumYili) {
  let simdi = new Date();
  return simdi.getFullYear() - dogumYili;
}
console.log(yasHesapla(1998)); // Örn: 27
```

---

## 🎯 Notlar

- Tarihler karşılaştırılabilir: `t1 > t2`, `t1 === t2` gibi
- `.getTime()` → tarihleri karşılaştırmak ve sıralamak için idealdir
- `Date` nesnesi zaman dilimi (timezone) farklarına dikkat eder