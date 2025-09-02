`Map`, JavaScript'te anahtar-değer (key-value) çiftlerini saklamak için kullanılan özel bir veri yapısıdır. `Object` gibi görünse de daha gelişmiş ve esnek bir yapıdır.

---
### 🎯 Neden `Map` kullanılır?

- Anahtar olarak **herhangi bir veri tipi** kullanılabilir (sayı, string, object, boolean, vs.).
- Eklenen verilerin **sırası korunur**.
- Boyutunu öğrenmek için `.size` özelliği kullanılır.
- Performans açısından büyük veri yapılarında daha verimlidir.

## 🛠️ 2. Map Oluşturma

```javascript
const myMap = new Map();
```

İsteğe bağlı olarak, başlangıç değerleriyle de oluşturulabilir:

```javascript
const myMap = new Map([
  ["ad", "Ahmet"],
  ["yaş", 25],
  [true, "aktif"]
]);
```


## ➕ 3. Veri Ekleme (`set`)

```javascript
myMap.set("şehir", "İstanbul");
myMap.set(123, "numara");
myMap.set(true, "doğru");
```

## 🔍 4. Veri Erişimi (`get`)

```javascript
console.log(myMap.get("şehir"));   // "İstanbul"
console.log(myMap.get(123));       // "numara"
```

## ❓ 5. Anahtar Varlığını Kontrol Etme (`has`)

```javascript
console.log(myMap.has("şehir"));  // true
console.log(myMap.has("ülke"));   // false
```

## ❌ 6. Veri Silme (`delete`)

```javascript
myMap.delete(123);  // true döner
```

## 🧹 7. Tüm Verileri Temizleme (`clear`)

```javascript
myMap.clear();
```

## 🔁 9. Map Üzerinde Dönme (İterasyon)

### Tüm elemanlar:

```javascript
for (const [key, value] of myMap) {
  console.log(key, value);
}
```

### Sadece anahtarlar:

```javascript
for (const key of myMap.keys()) {
  console.log(key);
}
```

### Sadece değerler:

```javascript
for (const value of myMap.values()) {
  console.log(value);
}
```

### `forEach` ile:

```javascript
myMap.forEach((value, key) => {
  console.log(key, value);
});
```

## 🔁 10. Array ↔ Map Dönüşümü

### Array'den Map'e:

```javascript
const dizi = [["renk", "kırmızı"], ["boyut", "büyük"]]; const renkMap = new Map(dizi);
```
### Map'ten Array'e:

```javascript
const renkler = new Map([   ["birinci", "kırmızı"],   ["ikinci", "mavi"] ]);  
const arr = [...renkler];  // [["birinci", "kırmızı"], ["ikinci", "mavi"]]
```

---

## 🆚 11. Map ve Object Karşılaştırması

|Özellik|`Map`|`Object`|
|---|---|---|
|Anahtar veri tipi|Her tür|Sadece string/symbol|
|Eleman sırası korunur mu?|✅ Evet|❌ Hayır|
|Boyut bilgisi nasıl alınır?|`.size`|`Object.keys(obj).length`|
|İterasyon kolaylığı|✅ Kolay (`for..of`)|Daha zahmetli|
|Performans (set/get işlemleri)|Genelde daha hızlı|Daha yavaş olabilir|

---

## 📌 Örnek Uygulama: Kullanıcı Girişi Sistemi


```javascript
const users = new Map();

users.set("admin", "1234");
users.set("user1", "abcd");

function login(username, password) {
  if (users.has(username) && users.get(username) === password) {
    console.log("Giriş başarılı!");
  } else {
    console.log("Hatalı kullanıcı adı veya şifre.");
  }
}

login("admin", "1234");  // Giriş başarılı!
login("user1", "wrong"); // Hatalı kullanıcı adı veya şifre.
```

---

## 📚 Özet

- `Map`, modern JavaScript'te güçlü bir anahtar-değer koleksiyonudur.
- `Object`'e göre daha esnek ve işlevseldir.
- Veri tipi esnekliği, sıralama garantisi ve performans avantajı sunar.