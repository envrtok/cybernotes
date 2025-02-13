### **📌 1.What are Packets and Frames** 

📌 **Paketler (Packets) ve Çerçeveler (Frames), veriyi küçük parçalara bölerek iletişimi hızlandırır.** Ancak, **farklı OSI katmanlarında çalışırlar**:

- **Frame (Çerçeve) → Katman 2 (Data Link Layer)** → **MAC adresleriyle çalışır, IP bilgisi içermez.**
- **Packet (Paket) → Katman 3 (Network Layer)** → **IP adresleriyle çalışır.**

💡 **Zarf Analojisi:**

- **Paket** = Postaya verilen dış zarf (IP adresiyle yönlendirilir).
- **Çerçeve** = Zarfın içindeki başka bir zarf (veri, MAC adresiyle taşınır).

📌 **Encapsulation (Kapsülleme):**

- **Veri, her katmanda ek bilgilerle sarılarak** gönderilir.
- **IP adreslerinden bahsediyorsak → Paketten bahsediyoruz.**
- **Ek bilgiler çıkarıldığında geriye çerçeve kalır.**

📌 **Paketler neden önemlidir?**  
✅ **Büyük veriler küçük parçalara bölündüğünde ağ tıkanmaz.**  
✅ **Örn:** Bir web sitesinden resim yüklerken, tüm resim tek parça değil **küçük paketler hâlinde** gelir ve cihazında birleştirilir.

📌 **Paket Header (Başlık) Alanları:**

- **Time to Live (TTL):** Paket sonsuza kadar dolaşmasın diye bir süre sınırı koyar.
- **Checksum:** Verinin bozulup bozulmadığını kontrol eder.
- **Source Address:** Paketin **geldiği cihazın IP adresi**.
- **Destination Address:** Paketin **gideceği cihazın IP adresi**.

🚀 **Özet:** **Paketler IP adresleriyle yönlendirilir, çerçeveler MAC adresleriyle taşınır. Kapsülleme sayesinde veri küçük parçalara bölünerek güvenli ve verimli bir şekilde iletilir!** 😎
### **📌 2. TCP/IP (The Three-Way Handshake)**
📌 **TCP, veri iletiminde güvenilirlik sağlayan, bağlantı tabanlı bir protokoldür.**

🔹 **TCP/IP Katmanları (4 Katman)**  
1️⃣ **Application (Uygulama)** → Web tarayıcıları, e-posta, dosya transferi  
2️⃣ **Transport (Taşıma)** → **TCP & UDP buradadır.**  
3️⃣ **Internet (İnternet)** → **IP adresleri ve yönlendirme burada gerçekleşir.**  
4️⃣ **Network Interface (Ağ Arayüzü)** → Ethernet, Wi-Fi gibi fiziksel bağlantılar

🚀 **TCP Özellikleri:**  
✅ **Bağlantı tabanlıdır.** Veri göndermeden önce bağlantı kurar.  
✅ **Verinin eksiksiz ve sıralı ulaşmasını garanti eder.**  
✅ **Hata kontrolü yapar.** Kaybolan paketleri tekrar gönderir.

---

#### **📌 TCP Üçlü El Sıkışma (Three-Way Handshake)**

1️⃣ **SYN** → İstemci sunucuya bağlantı isteği yollar.  
2️⃣ **SYN/ACK** → Sunucu isteği kabul eder ve kendi onayını gönderir.  
3️⃣ **ACK** → İstemci onaylar ve veri iletimi başlar.

📌 **Özet:** **TCP, bağlantıyı güvenli hâle getirmek için önce iki cihazın anlaşmasını sağlar.**

---

#### **📌 TCP Paketleri ve Başlık Bilgileri**

| **Başlık (Header)**        | **Açıklama**                                           |
| -------------------------- | ------------------------------------------------------ |
| **Source Port**            | Gönderen cihazın rastgele seçtiği port numarası.       |
| **Destination Port**       | Hedef cihazın kullandığı port (ör. Web için 80).       |
| **Source IP**              | Paketi gönderen cihazın IP adresi.                     |
| **Destination IP**         | Paketin ulaşacağı cihazın IP adresi.                   |
| **Sequence Number**        | İlk gönderilen veri parçasına atanmış numara.          |
| **Acknowledgement Number** | Gelen verinin doğrulandığı numara (Sequence +1).       |
| **Checksum**               | Paketin bozulmadığını doğrulayan matematiksel kontrol. |
| **Flag**                   | Paket ile ilgili özel bilgiler (SYN, ACK, FIN vb.).    |

---

#### **📌 TCP Bağlantı Kapatma Süreci**

1️⃣ **FIN** → Cihaz bağlantıyı kapatmak istediğini belirtir.  
2️⃣ **ACK** → Karşı taraf isteği onaylar.  
3️⃣ **FIN** → Karşı taraf da bağlantıyı sonlandırmak ister.  
4️⃣ **ACK** → Bağlantı düzgün şekilde kapanır.

📌 **Özet:** **TCP bağlantıyı açarken ve kapatırken iki cihazın anlaşmasını sağlar.**

🚀 **Genel Özet:** **TCP, veri bütünlüğünü ve sıralamasını garanti eden bir protokoldür. Bağlantıyı güvenli şekilde açar, yönetir ve kapatır.** 🔥
### **📌 3. UDP/IP**

📌 **UDP, TCP’den farklı olarak bağlantısız (stateless) bir protokoldür.**

🔹 **UDP’nin Özellikleri:**  
✅ **Hızlıdır.** Bağlantı kurma süreci olmadığı için anında veri gönderir.  
✅ **Bağlantıyı sürekli açık tutmaz.** Kaynak tüketimi azdır.  
✅ **Uygulamalar veri kaybına tolerans gösterebilir.** (Örn: Video akışı, sesli aramalar)

❌ **Veri kaybını umursamaz.** Alıcıya ulaşamayan paketler tekrar gönderilmez.  
❌ **Bağlantı kontrolü yoktur.** Zayıf bağlantılarda kötü performans verebilir.

📌 **Özet:** **UDP, hız ve düşük gecikme gerektiren durumlarda kullanılır, ancak veri güvenilirliği garanti edilmez.**

---

#### **📌 UDP ve TCP Karşılaştırması**

|**Özellik**|**TCP**|**UDP**|
|---|---|---|
|**Bağlantı Kurma**|Üçlü el sıkışma (Three-Way Handshake) gerektirir.|Bağlantı kurmadan doğrudan veri gönderir.|
|**Hız**|Daha yavaş ama güvenilir.|Çok hızlı ama güvenilir değil.|
|**Veri Bütünlüğü**|Paket kaybolursa tekrar gönderir.|Kaybolan paketleri umursamaz.|
|**Kullanım Alanları**|Web, e-posta, dosya transferi.|Video akışı, online oyunlar, VoIP.|

---

#### **📌 UDP Paket Yapısı**

UDP başlıkları TCP’ye göre daha basittir:

|**Başlık (Header)**|**Açıklama**|
|---|---|
|**Time to Live (TTL)**|Paketin belirli bir süre sonra silinmesini sağlar.|
|**Source Address**|Gönderen cihazın IP adresi.|
|**Destination Address**|Alıcı cihazın IP adresi.|
|**Source Port**|Gönderen cihazın rastgele seçtiği port.|
|**Destination Port**|Hedef cihazın uygulamasının çalıştığı port (ör. 80).|
|**Data**|İletilen dosya veya mesaj içeriği.|

📌 **Özet:** **UDP, hızlı ve verimli bir protokoldür ama veri kaybına karşı savunmasızdır.** 🎯
### **📌 4.Portlar (Bağlantı Noktaları) ve Kullanımı**

🔹 **Portlar, cihazların belirli uygulamalar için veri alışverişi yapmasını sağlayan numaralardır.**  
🔹 **0-65535** arasında değişen port numaraları vardır.  
🔹 **0-1024 arası portlar, "well-known ports" (bilinen portlar) olarak standart protokoller için kullanılır.**

💡 **Gemi Limanı Analojisi:**

- **Gemi (veri paketi)**, **uygun limana (porta) yanaşmazsa iletişim gerçekleşmez.**
- **Web tarayıcıları HTTP için 80. portu kullanır, SSH için 22. port kullanılır.**

---

#### **📌 Önemli Portlar ve Kullanım Alanları**

|**Protokol**|**Port Numarası**|**Açıklama**|
|---|---|---|
|**FTP (File Transfer Protocol)**|**21**|Dosya paylaşımı için kullanılır.|
|**SSH (Secure Shell)**|**22**|Uzak sistemlere güvenli metin tabanlı erişim sağlar.|
|**HTTP (HyperText Transfer Protocol)**|**80**|Web sitelerini görüntülemek için kullanılır.|
|**HTTPS (Secure HTTP)**|**443**|Şifrelenmiş ve güvenli web bağlantıları sağlar.|
|**SMB (Server Message Block)**|**445**|Dosya ve yazıcı paylaşımı için kullanılır.|
|**RDP (Remote Desktop Protocol)**|**3389**|Uzak masaüstü bağlantıları için kullanılır.|

📌 **Özet:** **Portlar, belirli uygulamalara veri yönlendiren numaralardır. Standart portlar kullanılabilir ama gerektiğinde özel portlar da atanabilir (Örn: Web sunucusu 8080’de çalıştırılabilir).** 🚀