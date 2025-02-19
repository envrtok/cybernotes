## **📌 1. What is DNS**
### **📌 DNS (Domain Name System) Nedir?**

DNS, **karmaşık IP adreslerini hatırlamak yerine, alan adlarını kullanarak internette gezinmeyi kolaylaştıran bir sistemdir**.

📌 **Örnek:**

- **104.26.10.229** yerine **tryhackme.com** yazmak daha pratiktir.
- DNS, **alan adını ilgili IP adresine çevirerek** erişim sağlar.

🚀 **Özet:** **DNS, internetin telefon rehberi gibi çalışır ve alan adlarını IP adreslerine dönüştürerek cihazların iletişimini kolaylaştırır.**
## **📌 2.Domain Hierarchy**
### **📌 Domain Hiyerarşisi Nedir?**

Domainler, **ağaç yapısında bir hiyerarşiye sahiptir** ve en üstte **kök domain (.)** bulunur.

---

### **📌 TLD (Top-Level Domain) - Üst Düzey Alan Adı**

**TLD, bir domain adının en sağındaki bölümdür**.  
🔹 **Örnek:** `tryhackme.com` → TLD = `.com`

**TLD Türleri:**

- **gTLD (Genel TLD):** `.com, .org, .edu, .gov` gibi amaç bazlı kullanılır.
- **ccTLD (Ülke Kodu TLD):** `.ca (Kanada), .co.uk (İngiltere)` gibi coğrafi bazlıdır.

---

### **📌 Second-Level Domain (İkinci Düzey Alan Adı)**

🔹 **Örnek:** `tryhackme.com` → Second-Level Domain = `tryhackme`

- En fazla **63 karakter** olabilir.
- **a-z, 0-9 ve "-" karakterlerini** içerebilir.

---

### **📌 Subdomain (Alt Alan Adı)**

🔹 **Örnek:** `admin.tryhackme.com` → Subdomain = `admin`

- **Bir domainin soluna eklenerek oluşturulur.**
- **Sınırsız subdomain oluşturulabilir.**
- **Toplam uzunluk 253 karakteri geçmemelidir.**

🚀 **Özet:** **Domain hiyerarşisi, TLD → Second-Level Domain → Subdomain şeklinde sıralanır. Subdomain'ler, ana domaini bölerek organizasyonu kolaylaştırır.**
## **📌 3. Record Types**
### **📌 DNS Kayıt Türleri**

DNS, sadece web siteleri için değil, **farklı ağ hizmetleri için de kullanılır**. İşte en yaygın DNS kayıt türleri:

|**Kayıt Türü**|**Açıklama**|**Örnek**|
|---|---|---|
|**A Record**|**IPv4 adresine yönlendirir.**|`104.26.10.229`|
|**AAAA Record**|**IPv6 adresine yönlendirir.**|`2606:4700:20::681a:be5`|
|**CNAME Record**|**Başka bir domain adına yönlendirir.**|`store.tryhackme.com → shops.shopify.com`|
|**MX Record**|**E-posta sunucusunu belirler.**|`alt1.aspmx.l.google.com`|
|**TXT Record**|**Serbest metin içerir, doğrulama veya spam önleme için kullanılır.**|SPF, DKIM gibi e-posta güvenliği kayıtları|

🚀 **Özet:** **DNS kayıtları, IP yönlendirme, e-posta yönetimi ve kimlik doğrulama gibi birçok fonksiyon sağlar.**
## **📌 4.Making a Request**
### **📌 DNS Sorgusu Nasıl Çalışır?**

🔹 **1. Yerel Cache Kontrolü**

- Bilgisayarınız, **önbelleğinde (cache)** sorgulanan domain adını kontrol eder.
- **Eğer kayıt varsa**, doğrudan IP adresi döndürülür.

🔹 **2. Recursive DNS Sunucusu**

- Eğer önbellekte yoksa, **Recursive DNS Server** (genellikle ISP tarafından sağlanır) devreye girer.
- **Önbelleğinde varsa**, cevap döndürülür. Yoksa **arama süreci başlar**.

🔹 **3. Root DNS Sunucusu**

- İnternetin **temel DNS sunucularıdır**.
- **İlgili TLD (Top-Level Domain) sunucusuna yönlendirir**.

🔹 **4. TLD DNS Sunucusu**

- **.com, .org, .net** gibi **TLD sunucuları**, **hangi isim sunucusunun yetkili olduğunu** belirler.

🔹 **5. Yetkili DNS Sunucusu (Authoritative Name Server)**

- **Domainin gerçek DNS kayıtlarını** tutar.
- **İlgili IP adresini Recursive DNS Server’a döndürür.**

🔹 **6. Cache & Sonuç Gönderimi**

- Recursive DNS Server **cevabı cache’ler** ve istemciye (bilgisayarınıza) geri yollar.
- **İstemci artık ilgili IP adresiyle bağlantı kurabilir.**

📌 **TTL (Time To Live)**: **Yanıtın önbellekte ne kadar süre saklanacağını belirler**.

🚀 **Özet:** **DNS sorgusu, Recursive → Root → TLD → Yetkili DNS sunucuları zincirinde ilerler ve önbelleğe alınarak süreci hızlandırır.**
