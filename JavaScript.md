
**JavaScript (JS)**; web sayfalarına **dinamiklik**, **etkileşim** ve **programlanabilirlik** kazandıran **yüksek seviyeli bir programlama dilidir.**

✅ **1995 yılında Brendan Eich tarafından geliştirilmiştir.**  
✅ **Başta sadece tarayıcılar için yazılmıştı, ama artık sunucu tarafında (Node.js gibi) ve masaüstü/mobil uygulamalarda da kullanılır.**

---

## 🎨 **Ne İşe Yarar?**

JavaScript sayesinde:

- **Web sayfalarını dinamik hale getirirsin.**
- Kullanıcı hareketlerine (tıklama, klavye, fare hareketi) yanıt verebilirsin.
- Form kontrolleri ve doğrulamaları yapabilirsin.
- İçerikleri dinamik olarak değiştirebilir, yeni HTML/CSS üretebilirsin.
- Oyunlar, animasyonlar, etkileşimli grafikler hazırlayabilirsin.
- **API’lere istek atabilir**, sunucudan veri çekip ekrana yazdırabilirsin.

---

## 📝 **JavaScript’in Temel Özellikleri**

✅ **Dinamik ve zayıf tipli bir dildir**  
👉 Değişkenlerin türünü belirtmen gerekmez:

```js
let a = 5;
a = "Merhaba"; // geçerli
```

✅ **Yorumlanan bir dil**  
👉 Kodun çalışması için derleme (compile) gerekmez. Tarayıcı doğrudan çalıştırır.

✅ **Nesne tabanlıdır**  
👉 Nesneler, fonksiyonlar ve prototipler üzerine kuruludur.

✅ **Çapraz platformdur**  
👉 Tarayıcı fark etmeksizin çalışır (Chrome, Firefox, Edge, Safari…)

✅ **Olay tabanlıdır**  
👉 Kullanıcı etkileşimlerine yanıt verebilir:

```js
button.onclick = function() {
  alert("Tıklandı!");
};
```

✅ **Tarayıcıya gömülü çalışır**  
👉 HTML içine `<script>` etiketi ile yerleştirilir:

```html
<script>
  alert("JavaScript Çalışıyor!");
</script>
```

---

## ⚡ **JavaScript Nerelerde Kullanılır?**

🌐 Web siteleri (dinamik içerik, animasyonlar)  
📱 Mobil uygulamalar (React Native, Ionic)  
🖥️ Masaüstü uygulamaları (Electron)  
🖥️ Sunucu tarafı programlama (Node.js)  
🎮 Oyun geliştirme (Phaser, Babylon.js)

---

## 💡 **Basit Bir Örnek**

```html
<!DOCTYPE html>
<html>
  <head>
    <title>JavaScript Demo</title>
  </head>
  <body>
    <button onclick="sayHello()">Tıkla</button>

    <script>
      function sayHello() {
        alert("Merhaba TkMatE!");
      }
    </script>
  </body>
</html>
```

✅ Bu örnekte bir düğmeye tıklayınca ekrana bir mesaj çıkar.

---

## 📌 **Kısaca JavaScript’in Rolü**

📝 **HTML = iskelet**  
🎨 **CSS = görünüm**  
⚙️ **JavaScript = hareket, zeka, etkileşim**

---

## 🎯 **Özet**

|Özellik|Açıklama|
|---|---|
|Ne?|Dinamik, etkileşimli web içeriği için bir dil|
|Nerede çalışır?|Tarayıcı, Node.js, mobil, masaüstü|
|Ne sağlar?|Olay yönetimi, veri işleme, DOM kontrolü|
|Dosya uzantısı|`.js`|