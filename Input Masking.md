
Input Masking, kullanıcıların form alanlarına veri girerken belirli bir formatta yazmalarını sağlamak için kullanılan tekniktir.  
Örneğin telefon numarası, tarih, kredi kartı numarası gibi standart formatları zorunlu kılmak için.

---

## 2. Neden Kullanılır?

- Kullanıcının doğru formatta veri girmesini sağlamak
- Form verilerinin tutarlılığını artırmak
- Hatalı girişleri önlemek
- Kullanıcı deneyimini geliştirmek

---

## 3. Basit Örnek: Telefon Numarası Maskesi (JS ile)

```html
<input type="text" id="tel" placeholder="Telefon: (555) 555-5555" maxlength="14" />
```

```js
const telInput = document.getElementById("tel");

telInput.addEventListener("input", (e) => {
  let value = e.target.value.replace(/\D/g, ""); // Sadece rakamları al
  if (value.length > 10) value = value.slice(0, 10);

  let formatted = "";
  if (value.length > 0) formatted = "(" + value.substring(0, 3);
  if (value.length >= 4) formatted += ") " + value.substring(3, 6);
  if (value.length >= 7) formatted += "-" + value.substring(6, 10);

  e.target.value = formatted;
});
```

---
## 4. Popüler Kütüphaneler

Kendi maskeni yazmak yerine hazır kütüphaneleri de kullanabilirsin:

- Inputmask
- Cleave.js
- IMask.js

---

## 5. Örnek: Tarih Maskesi


```js
const dateInput = document.getElementById("date"); 
dateInput.addEventListener("input", (e) => {   
	let val = e.target.value.replace(/\D/g, "").slice(0, 8);   
	
	if (val.length >= 3) 
		val = val.slice(0, 2) + "/" + val.slice(2);  
		 
	if (val.length >= 6) 
		val = val.slice(0, 5) + "/" + val.slice(5);   
		
	e.target.value = val; 
});
```

---

## 6. Dikkat Edilmesi Gerekenler

- Maskeyi çok katı yapmak bazen kullanıcı deneyimini zorlaştırabilir
- Kopyala-yapıştır durumlarında beklenmeyen girişler olabilir
- HTML5 `pattern` ile birlikte kullanmak faydalı olur

---

