
**AJAX** (Asynchronous JavaScript and XML), sayfanın tamamını yeniden yüklemeden, arka planda veri gönderip almayı sağlayan bir tekniktir.

### 🔹 Özellikleri:

- Sayfa yenilenmeden veri çekilebilir
- Arka planda çalışır
- JSON, XML, HTML gibi formatlarla çalışabilir (artık genellikle JSON)
- Kullanıcı deneyimini artırır

---

## 🔄 AJAX Ne İşe Yarar?

- Bir API'den veri almak
- Form verilerini arka planda sunucuya göndermek
- Liste, tablo, kart gibi içerikleri dinamik oluşturmak
- Arama filtreleme gibi işlemleri sayfa yenilemeden yapmak

---

## 🔧 AJAX Kullanım Yöntemleri

AJAX, JavaScript’te iki ana yöntemle uygulanır:

| Yöntem           | Açıklama                                       |
| ---------------- | ---------------------------------------------- |
| `XMLHttpRequest` | **Eski yöntem**, hala bazı yerlerde kullanılır |
| `fetch()`        | **Modern ve sade** yöntem (ES6+)               |

---

## 🔁 AJAX Ne Zaman Kullanılır?

- Kullanıcı butona bastığında sunucudan veri almak
- Sayfa yüklendiğinde API'den veri çekmek
- Dinamik içerik güncellemek (filtre, anket, yorum vs.)
- Form gönderiminde anlık doğrulama yapmak

---

## 🧠 AJAX İş Akışı

1. JavaScript, bir istek başlatır (XHR veya Fetch ile)
2. Sunucu isteği alır, yanıt hazırlar (JSON, XML vs.)
3. JavaScript yanıtı alır, işleyip DOM’a uygular

---

## 🛠 AJAX İçin Gerekenler

- JavaScript bilgisi
- Backend veya bir JSON API
- DOM işlemleri (veriyi ekrana yazmak için)