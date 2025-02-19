## **📌 1. How Websites Work**
### **📌 Web Sitesi Nasıl Çalışır?**

Bir web sitesini ziyaret ettiğinizde:  
🔹 **Tarayıcınız (Chrome, Safari vb.)** bir **web sunucusuna** istekte bulunur.  
🔹 **Web sunucusu**, istenen sayfanın bilgilerini içeren bir yanıt döndürür.  
🔹 **Tarayıcı**, aldığı veriyi işler ve sayfayı size gösterir.

### **📌 Web Sitesinin Bileşenleri**

1️⃣ **Front-End (İstemci Tarafı):** Tarayıcınızın web sitesini nasıl görüntülediği ile ilgilidir.  
2️⃣ **Back-End (Sunucu Tarafı):** İsteklerin işlendiği ve yanıtların döndürüldüğü sunucu tarafıdır.

🚀 **Özet:** Tarayıcınız bir web sunucusuna istek yapar, sunucu yanıt verir ve tarayıcı bu yanıtı kullanarak sayfayı görüntüler.
## **📌 2.HTML**

Web siteleri üç temel teknoloji ile oluşturulur:

🔹 **HTML (HyperText Markup Language)** → Web sitelerinin yapısını oluşturur.  
🔹 **CSS (Cascading Style Sheets)** → Sayfanın görünümünü ve tasarımını belirler.  
🔹 **JavaScript** → Sayfaya etkileşim ve dinamik özellikler ekler.

### **📌 HTML Yapısı ve Temel Elemanlar**

📌 **HTML, web sitelerinin iskeletini oluşturan bir işaretleme dilidir.**

Basit bir HTML belgesinin yapısı:

1️⃣ **`<!DOCTYPE html>`** → Sayfanın HTML5 ile yazıldığını belirtir.  
2️⃣ **`<html>`** → HTML belgesinin kök öğesidir, tüm diğer öğeleri içerir.  
3️⃣ **`<head>`** → Sayfa hakkında bilgiler içerir (örn. başlık).  
4️⃣ **`<body>`** → Sayfanın görünen içeriğini barındırır.  
5️⃣ **`<h1>`** → Büyük başlıkları belirtir.  
6️⃣ **`<p>`** → Paragrafları tanımlar.

### **📌 HTML Etiketleri ve Özellikleri (Attributes)**

HTML'de birçok farklı **etiket (tag)** ve bunlara eklenebilen **özellikler (attributes)** bulunur:

|**Etiket**|**Açıklama**|**Örnek**|
|---|---|---|
|`<button>`|Buton ekler|`<button>Click Me</button>`|
|`<img>`|Görsel ekler|`<img src="cat.jpg">`|
|`<p class="bold-text">`|**class** özelliğiyle stil ekler|`<p class="red-text">Red Text</p>`|
|`<p id="example">`|**id** ile benzersiz tanımlama yapar|`<p id="unique-text">Unique Text</p>`|

🚀 **Özet:** HTML, web sayfalarının temel yapısını oluşturur. Etiketler içerik belirlerken, **class** ve **id** gibi özellikler stil ve işlevsellik eklemek için kullanılır.
## **📌 3.JavaScript**

📌 **JavaScript (JS), web sayfalarına interaktif özellikler kazandıran en popüler programlama dillerinden biridir.**

### **📌 JavaScript’in Rolü**

🔹 **HTML** → Sayfanın yapısını ve içeriğini oluşturur.  
🔹 **CSS** → Sayfanın tasarımını belirler.  
🔹 **JavaScript** → Sayfaya **dinamik ve interaktif** özellikler ekler.

📌 **JS olmadan, web sayfaları statik kalır ve etkileşim içermez.**

JavaScript ile:  
✅ **Gerçek zamanlı güncellemeler** yapılabilir.  
✅ **Butonlara tıklanınca renk değiştirme** gibi etkileşimler eklenebilir.  
✅ **Animasyonlar** ve **dinamik içerik yükleme** sağlanabilir.

### **📌 JavaScript Nasıl Eklenir?**

JS kodları:  
1️⃣ **HTML içinde doğrudan `<script>` etiketleri** ile eklenebilir.  
2️⃣ **Harici bir dosya (`.js`) olarak** tanımlanabilir:

```html
<script src="/js/script.js"></script>
```

---

### **📌 JavaScript ile HTML Manipülasyonu**

📌 **HTML içeriğini değiştirme:**

```javascript
document.getElementById("demo").innerHTML = "Hack the Planet";
```

📌 **Butona tıklanınca içerik değiştirme:**

```html
<button onclick='document.getElementById("demo").innerHTML = "Button Clicked";'>Click Me!</button>
```

📌 **Etkinlikler (`onclick`, `onhover`) kullanılarak dinamik değişiklikler yapılabilir.**

🚀 **Özet:** JavaScript, web sayfalarına **etkileşim, animasyon ve dinamik içerik** eklemek için kullanılır. HTML ve CSS ile birlikte çalışarak modern web sitelerinin temelini oluşturur.
## **📌 4.Sensitive Data Exposure**

📌 **Hassas veri açığı, bir web sitesinin kullanıcıya açık bir şekilde gizli bilgileri sızdırması durumudur.**

### **📌 Hassas Veri Açığının Sebepleri**

🔹 **Güvenli olmayan HTML veya JavaScript kodları** → Kaynak kodda gizli bilgiler olabilir.  
🔹 **Geliştiricinin unuttuğu giriş bilgileri veya özel bağlantılar** → Sayfa kaynağında saklanmış olabilir.  
🔹 **Açıkta kalan API anahtarları ve erişim token’ları** → Saldırganlar tarafından kötüye kullanılabilir.

### **📌 Nasıl Bir Tehdit Oluşturur?**

✅ **Açıkta bırakılan giriş bilgileri**, saldırganların sisteme yetkisiz erişim sağlamasına neden olabilir.  
✅ **HTML veya JavaScript içinde gizli veriler**, web uygulamasının diğer bölümlerine sızmak için kullanılabilir.  
✅ **Gizli linkler**, yetkisiz kullanıcıların özel sayfalara ulaşmasını sağlayabilir.

### **📌 Güvenlik Değerlendirmesi Yaparken Dikkat Edilmesi Gerekenler**

🔹 **Sayfa kaynağını görüntüleyerek** (`View Page Source`) gizli veriler olup olmadığını kontrol edin.  
🔹 **HTML yorumlarını ve gizli input alanlarını inceleyin** (`<!-- Bu bir yorum -->`).  
🔹 **JavaScript dosyalarında gizli değişken veya anahtar olup olmadığını araştırın.**

🚀 **Özet:** Web sayfalarının kaynak kodlarında gizli bilgilerin açık bırakılması, saldırganların sisteme yetkisiz erişim sağlamasına neden olabilir. Güvenlik kontrollerinde sayfa kaynağı detaylıca incelenmelidir.
## **📌 5.HTML Injection**

📌 **HTML Injection, kullanıcının girdiği verilerin filtrelenmeden doğrudan sayfaya eklenmesiyle ortaya çıkan bir güvenlik açığıdır.**

---

### **📌 HTML Injection Nasıl Çalışır?**

🔹 **Web sitesi kullanıcı girdilerini filtrelemezse**, kötü niyetli kişiler HTML veya JavaScript kodlarını girdi olarak ekleyebilir.  
🔹 **Tarayıcı bu girdiyi bir metin yerine HTML olarak işler**, böylece saldırgan sayfanın görünümünü ve işlevselliğini değiştirebilir.  
🔹 **Örneğin, bir giriş alanına `<h1>Hacked!</h1>` yazılırsa**, bu komut tarayıcıda başlık olarak gösterilir.

---

### **📌 HTML Injection Örneği**

Aşağıdaki JavaScript kodu, kullanıcıdan aldığı girdiyi doğrudan HTML içeriği olarak ekler:

```html
<script>
  function sayHi() {
    const name = document.getElementById('name').value;
    document.getElementById("welcome-msg").innerHTML = "Welcome " + name;
  }
</script>
```

Eğer kullanıcı şu girdiyi girerse:

```html
<h1>Hacked!</h1>
```

Bu HTML kodu sayfada büyük bir başlık olarak görüntülenir. Eğer kötü niyetli bir saldırgan `<script>` etiketleriyle JavaScript eklerse, sayfanın işlevselliğini tamamen değiştirebilir!

---

### **📌 HTML Injection Nasıl Önlenir?**

✅ **Kullanıcı girdilerini her zaman filtreleyin!**  
✅ **HTML özel karakterlerini kaçış karakterleriyle değiştirin.**  
✅ **Kullanıcı girdilerini doğrudan innerHTML yerine, metin olarak ekleyin.**  
✅ **Girdi doğrulama ve beyaz listeleme yaparak sadece güvenli girişlere izin verin.**

🚀 **Özet:** HTML Injection, kullanıcı girdilerinin filtrelenmemesi nedeniyle tarayıcının bu girdileri HTML olarak işlemesiyle ortaya çıkar. Güvenli bir web uygulaması için, tüm kullanıcı girdileri filtrelenmeli ve HTML/JavaScript enjeksiyonuna karşı korunmalıdır.