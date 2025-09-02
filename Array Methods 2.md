
## 🔹 1. **Diziyi Dönüştüren veya Kopyalayan Metotlar**

### `map()`

Her elemanı alır, dönüştürür ve yeni bir dizi döner.

```js
const numbers = [1, 2, 3];
const doubled = numbers.map(n => n * 2);
console.log(doubled); // [2, 4, 6]
```

---

### `filter()`

Koşulu sağlayan elemanları yeni dizi olarak döner.

```js
const numbers = [1, 2, 3, 4];
const evens = numbers.filter(n => n % 2 === 0);
console.log(evens); // [2, 4]
```

---

### `reduce()`

Diziyi tek bir değere indirger (toplama, çarpma, vb.).

```js
const numbers = [1, 2, 3];
const sum = numbers.reduce((acc, val) => acc + val, 0);
console.log(sum); // 6
```

---

### `flat()`

İç içe dizileri belirli derinliğe kadar düzleştirir.

```js
const nested = [1, [2, [3, [4]]]];
console.log(nested.flat(2)); // [1, 2, 3, [4]]
```

---

### `flatMap()`

Hem `map()` yapar hem de sonucu düzleştirir.

```js
const words = ["merhaba", "dünya"];
const chars = words.flatMap(word => word.split(""));
console.log(chars); // ['m','e',...,'a']
```

---

## 🔹 2. **Eleman Ekleme / Silme Metotları**

### `push()`

Dizinin sonuna eleman ekler.

```js
const arr = [1, 2];
arr.push(3);
console.log(arr); // [1, 2, 3]
```

---

### `pop()`

Son elemanı siler ve döner.

```js
const arr = [1, 2, 3];
arr.pop(); // 3
console.log(arr); // [1, 2]
```

---

### `unshift()`

Başa eleman ekler.

```js
const arr = [2, 3];
arr.unshift(1);
console.log(arr); // [1, 2, 3]
```

---

### `shift()`

Baştan eleman siler.

```js
const arr = [1, 2, 3];
arr.shift(); // 1
console.log(arr); // [2, 3]
```

---

### `splice(start, deleteCount, ...items)`

Eleman ekler/siler/değiştirir.

```js
const arr = [1, 2, 3, 4];
arr.splice(1, 2, 9, 8); 
console.log(arr); // [1, 9, 8, 4]
```

---

### `slice(start, end)`

Bölüp yeni dizi döner (orijinali bozmaz).

```js
const arr = [10, 20, 30, 40];
console.log(arr.slice(1, 3)); // [20, 30]
```

---

## 🔹 3. **Sıralama / Ters Çevirme**

### `sort()`

Alfabetik veya özel kurala göre sıralar.

```js
const nums = [5, 2, 9];
nums.sort((a, b) => a - b);
console.log(nums); // [2, 5, 9]
```

---

### `reverse()`

Diziyi tersine çevirir.

```js
const arr = [1, 2, 3];
arr.reverse();
console.log(arr); // [3, 2, 1]
```

---

## 🔹 4. **Arama ve Kontrol Metotları**

### `find()`

Koşulu sağlayan ilk elemanı döner.

```js
const users = [{id: 1}, {id: 2}];
const user = users.find(u => u.id === 2);
console.log(user); // {id: 2}
```

---

### `findIndex()`

İlk eşleşmenin indeksini döner.

```js
const arr = [10, 20, 30];
console.log(arr.findIndex(x => x > 15)); // 1
```

---

### `includes()`

Bir değerin içerilip içerilmediğini kontrol eder.

```js
const arr = [1, 2, 3];
console.log(arr.includes(2)); // true
```

---

### `indexOf() / lastIndexOf()`

İlk veya son eşleşmenin indeksini döner.

```js
const arr = [1, 2, 3, 2];
console.log(arr.indexOf(2)); // 1
console.log(arr.lastIndexOf(2)); // 3
```

---

### `some()`

En az bir eleman koşulu sağlıyor mu?

```js
const arr = [1, 2, 3];
console.log(arr.some(n => n > 2)); // true
```

---

### `every()`

Tüm elemanlar koşulu sağlıyor mu?

```js
const arr = [2, 4, 6];
console.log(arr.every(n => n % 2 === 0)); // true
```

---

## 🔹 5. **Birleştirme ve Dönüştürme Metotları**

### `join()`

Diziyi string’e çevirir.

```js
const arr = ['a', 'b', 'c'];
console.log(arr.join('-')); // "a-b-c"
```

---

### `toString()`

Diziyi string’e çevirir (virgülle ayırarak).

```js
const arr = [1, 2, 3];
console.log(arr.toString()); // "1,2,3"
```

---

### `concat()`

Dizileri birleştirir (yeni dizi döner).

```js
const a = [1, 2];
const b = [3, 4];
console.log(a.concat(b)); // [1, 2, 3, 4]
```

---

## 🔹 6. **Dizi Oluşturma ve Doldurma**

### `Array.from()`

Dizi benzeri/iterable bir yapıyı diziye çevirir.

```js
const str = "test";
console.log(Array.from(str)); // ['t', 'e', 's', 't']
```

---

### `Array.of()`

Verilen argümanlardan yeni dizi oluşturur.

```js
const arr = Array.of(1, 2, 3);
console.log(arr); // [1, 2, 3]
```

---

### `fill()`

Tüm diziyi (veya bir kısmını) sabit değerle doldurur.

```js
const arr = [1, 2, 3, 4];
arr.fill(0, 1, 3); 
console.log(arr); // [1, 0, 0, 4]
```

---

## 🔹 7. **İterasyon Metotları**

### `forEach()`

Her elemanı tek tek gezip işlem yapar (return etmez).

```js
[1, 2, 3].forEach(x => console.log(x * 2));
```

---

### `entries()`, `keys()`, `values()`

İteratör döner.

```js
const arr = ['a', 'b'];
for (const [i, val] of arr.entries()) {
  console.log(i, val); // 0 'a', 1 'b'
}
```

---

## 🔹 8. **Yapı Tespiti**

### `Array.isArray()`

Bir değerin dizi olup olmadığını kontrol eder.

```js
console.log(Array.isArray([1, 2])); // true
console.log(Array.isArray("hello")); // false
```

---

Bu listeyi istersen parça parça çalışabilir, her metodu ayrı başlık altında örneklerle işleyebiliriz.

İlk olarak hangi metot grubu ile başlamak istersin? (örn: `filter/map/reduce`, `find/some/every`, `splice/slice`, vs.)