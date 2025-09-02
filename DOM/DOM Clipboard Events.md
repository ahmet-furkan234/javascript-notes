JavaScript’te form veya metin girişlerinde sıkça kullanılır. Hadi detaylı bakalım!

---

## 1. Clipboard Events Türleri

|Event|Açıklama|
|---|---|
|`copy`|Kopyalama işlemi gerçekleştiğinde|
|`cut`|Kesme işlemi gerçekleştiğinde|
|`paste`|Yapıştırma işlemi gerçekleştiğinde|

---

## 2. Örnek Kullanım


```html
<textarea id="myText" rows="5" cols="30"></textarea>
```


```js
const textarea = document.getElementById("myText");

textarea.addEventListener("copy", (e) => {
  console.log("Kopyalama yapıldı!");
});

textarea.addEventListener("cut", (e) => {
  console.log("Kesme yapıldı!");
});

textarea.addEventListener("paste", (e) => {
  console.log("Yapıştırma yapıldı!");

  // Yapıştırılan metni kontrol edip değiştirebilirsin:
  e.preventDefault(); // Varsayılan yapıştırmayı durdur
  const clipboardData = e.clipboardData || window.clipboardData;
  const pastedText = clipboardData.getData("text");

  // Mesela yapıştırılan metni büyük harfe çevir:
  const transformedText = pastedText.toUpperCase();

  // Kendi metnimizi ekleyelim:
  document.execCommand("insertText", false, transformedText);
});
```

---

## 3. Clipboard API (Modern ve Güçlü)

Modern tarayıcılarda Clipboard API ile panoya erişim sağlanır.

**Panoya yazmak:**

```js
navigator.clipboard.writeText("Merhaba Dünya!").then(() => {
  console.log("Panoya yazıldı!");
});
```

**Panodan okumak:**


```js
navigator.clipboard.readText().then(text => {
  console.log("Panodaki metin:", text);
});
```

**Not:** Bu API HTTPS sayfalarında çalışır ve kullanıcı izin isteyebilir.

---

## 4. Uygulama Örneği: Yapıştırmayı Engelleme

```js
textarea.addEventListener("paste", (e) => {
  e.preventDefault();
  alert("Yapıştırma engellendi!");
});
```

---

## 5. Özet

- `copy`, `cut`, `paste` eventleri kullanıcı panoyla etkileşiminde tetiklenir
- Yapıştırma sırasında `preventDefault()` ile içeriği kontrol edip değiştirebilirsin
- Modern Clipboard API ile panoya erişim kolaylaşıyor, fakat güvenlik izinleri var