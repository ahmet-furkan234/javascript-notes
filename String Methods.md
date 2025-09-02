
JavaScript’te string (metin) veri tipi üzerinde işlem yapmamızı sağlayan birçok yerleşik (built-in) metot vardır. Aşağıda en sık kullanılanları gruplar halinde inceleyelim.

---

## 📏 1. Uzunluk ve Erişim

| Metot / Özellik  | Açıklama                                                  | Örnek                   |     |
| ---------------- | --------------------------------------------------------- | ----------------------- | --- |
| `.length`        | String’in karakter sayısını verir                         | `"Merhaba".length → 7`  |     |
| `[index]`        | Belirli karaktere ulaşmak için köşeli parantez kullanılır | `"abc"[1] → "b"`        |     |
| `.charAt(index)` | Belirli index’teki karakteri döner                        | `"abc".charAt(1) → "b"` | -   |

---


## 🔍 2. Arama & Kontrol

| Metot                   | Açıklama                        | Örnek                                |
| ----------------------- | ------------------------------- | ------------------------------------ |
| `.includes("metin")`    | Belirtilen metin var mı?        | `"selam".includes("la") → true`      |
| `.startsWith("metin")`  | Belirtilen metinle başlıyor mu? | `"merhaba".startsWith("mer") → true` |
| `.endsWith("metin")`    | Belirtilen metinle bitiyor mu?  | `"merhaba".endsWith("ba") → true`    |
| `.indexOf("metin")`     | Metnin ilk görüldüğü index      | `"merhaba".indexOf("a") → 3`         |
| `.lastIndexOf("metin")` | Metnin son görüldüğü index      | `"keklik".lastIndexOf("k") → 5`      |

---



## 🔠 3. Dönüştürme

| Metot            | Açıklama                            | Örnek                                 |     |
| ---------------- | ----------------------------------- | ------------------------------------- | --- |
| `.toUpperCase()` | Büyük harfe çevirir                 | `"merhaba".toUpperCase() → "MERHABA"` |     |
| `.toLowerCase()` | Küçük harfe çevirir                 | `"MERHABA".toLowerCase() → "merhaba"` |     |
| `.trim()`        | Baştaki ve sondaki boşlukları siler | `" selam ".trim() → "selam"`          |     |
| `.trimStart()`   | Sadece baştaki boşlukları siler     |                                       |     |
| `.trimEnd()`     | Sadece sondaki boşlukları siler     |                                       | -   |

---

## ✂️ 4. Parçalama & Bölme

| Metot                    | Açıklama                                              | Örnek                                |     |
| ------------------------ | ----------------------------------------------------- | ------------------------------------ | --- |
| `.slice(start, end)`     | Belirtilen aralığı döner                              | `"abcdef".slice(1, 4) → "bcd"`       |     |
| `.substring(start, end)` | `slice` gibidir ama negatif index desteklemez         |                                      |     |
| `.substr(start, length)` | Başlangıçtan itibaren uzunluk kadar alır (ES5 – eski) |                                      |     |
| `.split("ayırıcı")`      | String’i diziye çevirir                               | `"a,b,c".split(",") → ["a","b","c"]` | -   |


---

## 🔁 5. Değiştirme

|Metot|Açıklama|Örnek|
|---|---|---|
|`.replace("eski", "yeni")`|İlk geçen ifadeyi değiştirir|`"merhaba".replace("a", "o") → "merhoba"`|
|`.replaceAll("eski", "yeni")`|Tüm geçen ifadeleri değiştirir|`"aaa".replaceAll("a", "b") → "bbb"`|
|`.repeat(n)`|String’i n kez tekrarlar|`"ha".repeat(3) → "hahaha"`|

---


## 🧩 6. Birleştirme

|Metot|Açıklama|Örnek|
|---|---|---|
|`+`|İki string’i birleştirir|`"Merhaba " + "Dünya"`|
|`.concat()`|`+` gibi birleştirir|`"Merhaba".concat(" Dünya")`|

---

## 📌 Örnek Uygulama



```js
let ad = "  Zeynep  "; 
console.log(ad.trim().toUpperCase()); // "ZEYNEP"

let mesaj = "Merhaba dünya, nasılsın dünya?"; 
console.log(mesaj.replaceAll("dünya", "evren"));  // Merhaba evren, nasılsın evren?
```

---

## 🎯 Notlar

- String’ler **immutable** (değiştirilemez) olduğundan metotlar **yeni bir string** döner.
- `.replaceAll()` tarayıcı desteği bakımından `.replace(/x/g, "y")` regex alternatifi ile de yapılabilir.