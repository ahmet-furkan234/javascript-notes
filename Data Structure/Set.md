

`Set`, ’te **tekrarsız (unique)** değerleri saklayan bir koleksiyon türüdür. Her değer sadece **bir kez** bulunabilir.

---

### 🎯 Ne zaman kullanılır?

- Aynı değerin tekrar etmesini istemediğinizde
- Dizi içindeki tekrar eden elemanları filtrelemek istediğinizde
- Küme işlemleri (kesişim, birleşim, fark) yapmak istediğinizde

---

## 🛠️ 2. Set Oluşturma

```javascript
const mySet = new Set();`
```

Ya da başlangıç değerleriyle:

```javascript
const mySet = new Set([1, 2, 3, 3, 4]);
// Set {1, 2, 3, 4} → tekrar eden 3 yalnızca 1 kez saklanır
```

---

## ➕ 3. Eleman Ekleme (`add`)

```javascript
mySet.add(10);
mySet.add("merhaba");
mySet.add(true);
```

> Aynı eleman tekrar eklenirse eklenmez (set'in doğası gereği):


```javascript
mySet.add(10);  // zaten varsa eklemez
```

---

## ❌ 4. Eleman Silme (`delete`)

```javascript
mySet.delete(10);
```

---

## 🧹 5. Tüm Elemanları Temizleme (`clear`)

```javascript
mySet.clear();
```

---

## ❓ 6. Eleman Varlığını Kontrol (`has`)

```javascript
console.log(mySet.has("merhaba")); // true veya false
```

---

## 📏 7. Eleman Sayısı (`size`)

```javascript
console.log(mySet.size);
```

---

## 🔁 8. Set Üzerinde Dönme

```javascript
for (const item of mySet) 
{   
console.log(item); 
}

```

Veya:

```javascript
mySet.forEach(value => 
{  
	console.log(value); 
});`
```

---

## 🔁 9. Dizi ↔ Set Dönüşümleri

### Array → Set (tekrarları siler)

```javascript
const dizi = [1, 2, 2, 3, 4, 4];
const benzersiz = new Set(dizi);  // Set {1, 2, 3, 4}
```

### Set → Array

```javascript
const diziYap = [...benzersiz];  // [1, 2, 3, 4]
```

---

## 🔬 10. Küme İşlemleri (Manual)

### 🔗 Birleşim (union)

```javascript
const a = new Set([1, 2, 3]);
const b = new Set([3, 4, 5]);

const union = new Set([...a, ...b]);  // Set {1, 2, 3, 4, 5}

```
### 🔀 Kesişim (intersection)

```javascript
const intersection = new Set([...a].filter(x => b.has(x)));  // Set {3}
```
### ➖ Fark (difference)

```javascript
const difference = new Set([...a].filter(x => !b.has(x)));  // Set {1, 2}
```

---

## 🆚 Set vs Array

|Özellik|`Set`|`Array`|
|---|---|---|
|Tekrarlı eleman|❌ Yok|✅ Var olabilir|
|Eleman kontrolü|`set.has()`|`array.includes()`|
|Performans|Büyük verilerde daha iyi|Orta düzey|
|Eleman sırası|✅ Korunur|✅ Korunur|

---

## ✅ Örnek Uygulama: Tekrarlı Elemanları Silme

```javascript
const numbers = [1, 2, 2, 3, 4, 4, 5];
const unique = [...new Set(numbers)];
console.log(unique); // [1, 2, 3, 4, 5]
```
---

## 📚 Özet

- `Set`, sadece benzersiz değerler içeren bir koleksiyondur.
- `.add`, `.delete`, `.has`, `.clear` gibi metodlarla yönetilir.
- Array dönüşümleri ve küme işlemleri ile güçlü bir araçtır.