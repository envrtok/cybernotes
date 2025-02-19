## **📌 1. What is HTTP(s)**
### **📌 HTTP ve HTTPS Nedir?**

🔹 **HTTP (HyperText Transfer Protocol)**

- **Web sayfalarının iletilmesini sağlayan protokoldür.**
- **HTML, resimler, videolar gibi içerikleri aktarır.**
- **Şifreleme yoktur**, veriler **düz metin olarak iletilir**.

🔹 **HTTPS (HyperText Transfer Protocol Secure)**

- **HTTP’nin şifreli ve güvenli versiyonudur.**
- **Veriler şifrelenerek aktarılır**, böylece **dinlenemez veya değiştirilemez**.
- **Web sitesinin doğruluğunu garanti eder**, sahte sunuculara karşı koruma sağlar.

🚀 **Özet:** **HTTP veri iletir, ancak güvenli değildir. HTTPS, verileri şifreleyerek güvenliği sağlar.**
## **📌 2.Requests And Responses**
### **📌 URL (Uniform Resource Locator) Nedir?**

URL, **internette bir kaynağa nasıl ve nereden erişileceğini belirten adres sistemidir**.

🔹 **URL Bileşenleri:**

|**Bileşen**|**Açıklama**|**Örnek**|
|---|---|---|
|**Scheme**|Kullanılacak protokolü belirler.|`http`, `https`, `ftp`|
|**User**|Kimlik doğrulama için kullanıcı adı ve şifre.|`user:password@`|
|**Host**|Alan adı veya IP adresi.|`tryhackme.com`|
|**Port**|Bağlanılacak port numarası.|`:80`, `:443`|
|**Path**|Kaynağın dosya konumu.|`/view-room`|
|**Query String**|Ekstra veri göndermek için kullanılır.|`?id=1`|
|**Fragment**|Sayfa içindeki belirli bir noktaya yönlendirir.|`#task3`|

---

### **📌 HTTP İstek ve Yanıt Süreci**

🔹 **İstek Örneği:**

```http
GET / HTTP/1.1  
Host: tryhackme.com  
User-Agent: Mozilla/5.0 Firefox/87.0  
Referer: https://tryhackme.com/  
```

📌 **Bu istek, `tryhackme.com` ana sayfasını GET metodu ile istemektedir.**

🔹 **Yanıt Örneği:**

```http
HTTP/1.1 200 OK  
Server: nginx/1.15.8  
Date: Fri, 09 Apr 2021 13:34:03 GMT  
Content-Type: text/html  
Content-Length: 98  
```

📌 **Bu yanıt, isteğin başarılı olduğunu (`200 OK`) ve döndürülen içeriğin HTML formatında olduğunu belirtmektedir.**

🚀 **Özet:** **URL, internet kaynaklarına erişimi sağlar. HTTP istekleri sunucuya veri gönderirken, yanıtlar talep edilen içeriği döndürür.**
## **📌 3.HTTP Methods**
### **📌 HTTP Metodları Nedir?**

HTTP metodları, **istemcinin (tarayıcı veya uygulama) web sunucusuna ne yapmak istediğini bildirir**.

🔹 **En Yaygın HTTP Metodları:**

|**Metod**|**Açıklama**|**Kullanım Alanı**|
|---|---|---|
|**GET**|**Veri almak için kullanılır.**|Web sayfası yükleme|
|**POST**|**Yeni veri göndermek veya oluşturmak için kullanılır.**|Form gönderimi|
|**PUT**|**Mevcut veriyi güncellemek için kullanılır.**|Profil bilgisi güncelleme|
|**DELETE**|**Veriyi silmek için kullanılır.**|Hesap veya içerik silme|

🚀 **Özet:** **GET veri alır, POST yeni veri ekler, PUT günceller, DELETE siler.**
## **📌 4.HTTP Status Codes**
### **📌 HTTP Durum Kodları (Status Codes)**

HTTP yanıtlarında **ilk satır, istemcinin talebinin sonucunu belirten bir durum kodu içerir**.

🔹 **HTTP Durum Kodu Kategorileri:**

|**Kod Aralığı**|**Anlamı**|
|---|---|
|**100-199**|Bilgilendirme (İstek kabul edildi, devam edebilirsiniz)|
|**200-299**|Başarı (İstek başarılı şekilde tamamlandı)|
|**300-399**|Yönlendirme (Başka bir kaynağa yönlendirildi)|
|**400-499**|İstemci Hataları (İstek hatalı veya eksik)|
|**500-599**|Sunucu Hataları (Sunucuda bir problem var)|

---

🔹 **En Yaygın HTTP Kodları:**

|**Kod**|**Anlamı**|**Açıklama**|
|---|---|---|
|**200**|OK|Talep başarıyla tamamlandı.|
|**201**|Created|Yeni bir kaynak oluşturuldu.|
|**301**|Moved Permanently|Sayfa kalıcı olarak taşındı.|
|**302**|Found|Geçici yönlendirme yapıldı.|
|**400**|Bad Request|Hatalı veya eksik istek.|
|**401**|Not Authorized|Kimlik doğrulama gerekiyor.|
|**403**|Forbidden|Erişim izni yok.|
|**404**|Not Found|Sayfa veya kaynak bulunamadı.|
|**500**|Internal Server Error|Sunucu tarafında bilinmeyen bir hata.|
|**503**|Service Unavailable|Sunucu yoğun veya bakımda.|

🚀 **Özet:** **200 başarı, 300 yönlendirme, 400 istemci hatası, 500 sunucu hatası anlamına gelir.**
## **📌 5.Headers**
### **📌 HTTP Headers (Başlıklar) Nedir?**

HTTP başlıkları, **istemciden sunucuya veya sunucudan istemciye ek bilgiler gönderen veri parçalarıdır**.

---

### **📌 Yaygın HTTP İstek (Request) Başlıkları**

|**Başlık**|**Açıklama**|
|---|---|
|**Host**|Hangi web sitesine erişilmek istendiğini belirtir.|
|**User-Agent**|Tarayıcı adı ve sürümünü bildirir, siteyi uygun şekilde görüntülemek için kullanılır.|
|**Content-Length**|Gönderilen verinin boyutunu belirler.|
|**Accept-Encoding**|Desteklenen veri sıkıştırma yöntemlerini belirtir.|
|**Cookie**|Kullanıcıya ait bilgileri sunucuya iletir.|

---

### **📌 Yaygın HTTP Yanıt (Response) Başlıkları**

|**Başlık**|**Açıklama**|
|---|---|
|**Set-Cookie**|Kullanıcı bilgilerini saklar ve sonraki isteklerde geri gönderir.|
|**Cache-Control**|Tarayıcının içeriği ne kadar süre önbellekte tutacağını belirler.|
|**Content-Type**|Dönen verinin türünü açıklar (HTML, JSON, resim, video vb.).|
|**Content-Encoding**|Verinin hangi sıkıştırma yöntemiyle gönderildiğini gösterir.|

🚀 **Özet:** **İstek başlıkları sunucuya bilgi gönderirken, yanıt başlıkları istemciye gerekli bilgileri iletir.**
## **📌 6.Cookies**
### **📌 Cookies Nedir?**

Cookies, **web sitelerinin kullanıcı bilgilerini saklamasına ve hatırlamasına yardımcı olan küçük veri parçalarıdır**. HTTP **stateless** (durumsuz) olduğu için, **kimlik doğrulama, kişisel ayarlar ve oturum takibi** için kullanılır.

---

### **📌 Cookie Nasıl Çalışır?**

1️⃣ **Sunucu, "Set-Cookie" başlığı ile tarayıcıya bir cookie gönderir.**  
2️⃣ **Tarayıcı, bu cookie’yi saklar ve sonraki isteklerde sunucuya geri gönderir.**  
3️⃣ **Sunucu, gelen cookie’ye göre kullanıcıyı tanır ve uygun içeriği sunar.**

---

### **📌 Cookie Kullanım Alanları**

🔹 **Kimlik Doğrulama:** Kullanıcının giriş yaptığını hatırlar.  
🔹 **Oturum Yönetimi:** Kullanıcının alışveriş sepeti gibi verilerini saklar.  
🔹 **Kişiselleştirme:** Tema, dil gibi kullanıcı tercihlerini hatırlar.

🚀 **Özet:** **Cookies, web sitelerinin kullanıcı bilgilerini saklamasına ve hatırlamasına yardımcı olur, özellikle kimlik doğrulamada kullanılır.**
