## **📌 1. Other Components**
### **📌 Load Balancer Nedir?**

Load balancer, **trafik yükünü birden fazla sunucuya dağıtarak performansı artırır ve yedeklilik sağlar**.

🔹 **Çalışma Prensibi:**  
1️⃣ **İstek önce load balancer’a gider.**  
2️⃣ **Algoritmalara göre en uygun sunucuya yönlendirilir.** (Örn: Round-robin, en az yoğun sunucu seçimi)  
3️⃣ **Health check yaparak çalışmayan sunucuları devre dışı bırakır.**

---

### **📌 CDN (Content Delivery Network) Nedir?**

CDN, **statik içerikleri (CSS, JavaScript, görseller) dünya çapındaki sunuculara dağıtarak yükleme hızını artırır**.

📌 **Örnek:** Bir kullanıcı Avrupa’daysa, içerikler ABD yerine Avrupa’daki bir sunucudan yüklenir.

---

### **📌 Veritabanı (Database) Nedir?**

Web siteleri, **kullanıcı verilerini ve içeriklerini veritabanlarında saklar**.

🔹 **Yaygın Veritabanları:**

- **MySQL, PostgreSQL** (İlişkisel)
- **MongoDB** (NoSQL, esnek yapı)
- **MSSQL** (Microsoft tabanlı)

---

### **📌 WAF (Web Application Firewall) Nedir?**

WAF, **web sunucusunu saldırılara ve aşırı yüklenmeye karşı koruyan güvenlik katmanıdır**.

🔹 **Temel İşlevleri:**

- **SQL Injection, XSS gibi saldırıları tespit eder ve engeller.**
- **Bot trafiğini analiz eder.**
- **Rate limiting ile çok fazla istek gönderen IP’leri engeller.**

🚀 **Özet:** **Load balancer yük dağıtır, CDN hız kazandırır, veritabanları veri saklar, WAF ise saldırılara karşı koruma sağlar.**
## **📌 2. How Web Servers Work**
### **📌 Web Sunucusu Nedir?**

Web sunucusu, **gelen HTTP isteklerini karşılayan ve web içeriklerini istemcilere sunan bir yazılımdır**.

🔹 **Yaygın Web Sunucuları:**

- **Apache, Nginx** (Linux) → Varsayılan dizin: `/var/www/html`
- **IIS (Windows)** → Varsayılan dizin: `C:\inetpub\wwwroot`

📌 **Bir web sunucusu, istenen dosyayı yerel diskten alır ve istemciye gönderir.**

---

### **📌 Virtual Hosts (Sanal Hostlar)**

Web sunucuları **farklı domainler için birden fazla site barındırabilir**.

📌 **Örnek:**

- `one.com → /var/www/website_one`
- `two.com → /var/www/website_two`

🔹 **Web sunucusu, HTTP isteğindeki domain adına göre doğru içeriği sunar.**

---

### **📌 Statik vs. Dinamik İçerik**

|**Tür**|**Açıklama**|**Örnek**|
|---|---|---|
|**Statik İçerik**|**Değişmez** içerikler. Sunucu **doğrudan dosyayı gönderir**.|HTML, CSS, JavaScript, resimler|
|**Dinamik İçerik**|**Kullanıcıya göre değişen içerikler**. Backend tarafından **işlenerek oluşturulur**.|Blog yazıları, arama sonuçları|

📌 **Statik içerik doğrudan sunulur, dinamik içerik backend tarafından üretilir.**

---

### **📌 Backend & Scripting Dilleri**

🔹 **Backend, kullanıcının göremediği, işlemlerin yapıldığı sunucu tarafıdır.**

📌 **Yaygın Backend Dilleri:**

- **PHP, Python, Ruby, NodeJS, Perl**

📌 **Örnek PHP Kodu:**

```php
<html><body>Hello <?php echo $_GET["name"]; ?></body></html>
```

İstek: `http://example.com/index.php?name=adam`  
Çıktı:

```html
<html><body>Hello adam</body></html>
```

📌 **Kullanıcı sadece sonucu görür, backend kodunu göremez.**

🚀 **Özet:** **Web sunucuları statik ve dinamik içerikleri işler. Backend dilleri, web sitelerini interaktif hale getirir.**