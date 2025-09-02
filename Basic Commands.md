## Çıktı komutları

---
### 1.Konsola yazdırmak 

```js
console.log("Merhaba dünya");
```

### 2.Kullanıcıya uyarı göstermek 


```js
alert("Merhaba Kullanıcı");
```

### 3.Html sayfasına yazdırmak için 

```js
documnet.write("Merhaba, bu HTML içeriğine yazıldı.");
```


---

## Diyalog kutuları

---
### 1. Alert() - Uyarı Kutusu

Kullanıcıya sadece bilgi vermek için kullanılır. Tamam (Ok) butonu içerir

```js
 alert("Hoş geldiniz");
```

#### Kullanımı :
- Form gönderilmeden önce uyarı verme
- Basit bilgilendirme mesajları

---
### 2.Prompt() - Giriş Kutusu

Kullanıcıdan veri almak için kullanılır. Bir metin kutusu ile birlikte gelir.

```js
 let isim = propmt("Adınızı giriniz : ");
 alert("Merhaba " + isim);
```

#### Kullanımı :
- Kullanıcıdan isim, yaş gibi bilgileri almak 
- Kullanıcıdan girdi gerektiren basit senaryolar
#### Dönüş değeri :
- Kullanıcı bir şey yazarsa string olarak döner
- İptal butonuna basılırsa null döner

---

### 3.Confirm() - Onay Kutusu

Kullanıcıdan evet-hayır (ok-cancel) gibi onay almak için kullanılır.

```js
 let cevap = confirm("Silmek istediğinize eminmisiniz");
 if(cevap){
	 alert("Silindi");
 }
 else{
 	alert("İşlem iptal edildi");
 }
```

#### Kullanımı :
- Silme, çıkış yapma gibi kritik işlemler öncesi onay isteme
#### Dönüş değeri :
- Tamam (Ok) --> true
- İptal (Cancel) --> false

---

### Notlar 
- Bu kutular **blocklayıcıdır**: açıldığında kullanıcı pencereyi kapatmadan sayfa ile etkileşime devam edemez.
- Daha gelişmiş dialoglar için **SweetAlert, Boostrap modal** gibi kütüphaneler kullanılır.

---

## Özet Tablo 

| Fonksiyon | Amaç        | Kullanıcı Etkileşimi         |
| --------- | ----------- | ---------------------------- |
| alert()   | Uyarı       | Sadece "Tamam"               |
| prompt()  | Veri isteme | Metin kutusu + "Tamam/İptal" |
| confirm() | Onay alma   | "Tamam/İptal"                |

---

