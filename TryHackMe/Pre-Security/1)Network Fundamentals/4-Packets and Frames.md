## **📌 1. Packets and Frames**
### **📌 Packet ve Frame Nedir?**

**Packet (Paket) ve Frame (Çerçeve)**, büyük veri parçalarını küçük parçalara bölerek iletişim sağlayan veri birimleridir. Ancak, **OSI modelinde farklı katmanlarda** bulunurlar:

🔹 **Frame (Çerçeve) → OSI Katman 2 (Veri Bağlantı Katmanı)**

- **IP adresi içermez** (Sadece MAC adresleri ile çalışır).
- **Bir zarfın içine koyulan bir mektup gibi düşünülebilir**: Zarf açıldığında içindeki veri hala çerçeve olarak kalır.

🔹 **Packet (Paket) → OSI Katman 3 (Ağ Katmanı)**

- **IP adresleri içerir** ve **cihazlar arası veri taşımada kullanılır**.
- **Encapsulation (Kapsülleme)** sürecinde, çerçevenin içine paket yerleştirilir.

---

### **📌 Packet Kullanımının Avantajları**

- **Ağ tıkanıklığını önler**: Büyük veri blokları yerine küçük paketler gönderildiğinde, ağ üzerindeki yük dengelenir.
- **Hızlı veri iletimi sağlar**: Web siteleri, resimler ve videolar parçalara bölünerek gönderilir ve cihazda tekrar birleştirilir.
- **Hata kontrolü yapılabilir**: Paketler belirli standartlara uyarak iletilir ve gerekirse eksik olanlar tekrar istenir.

📌 **Örnek:** Bir web sitesindeki bir resmi yüklerken, resim **bütün olarak değil**, **küçük veri paketleri halinde** gönderilir ve cihazda yeniden birleştirilir.

---

### **📌 Paket Yapısı ve Başlık Bilgileri (Headers)**

Bir **IP paketi**, verinin yanı sıra **başlık (header)** içerir. Bu başlık, paketin nasıl yönlendirileceği ve işleneceği hakkında bilgi taşır:

|**Başlık**|**Açıklama**|
|---|---|
|**Time to Live (TTL)**|Paketin ağda kaç **düğüme (hop)** kadar gidebileceğini belirler. Süresi dolan paket silinir.|
|**Checksum**|Veri bütünlüğünü kontrol eder. Eğer paket değişirse, bozuk olduğu tespit edilir.|
|**Source Address (Kaynak Adresi)**|Paketi gönderen cihazın IP adresi.|
|**Destination Address (Hedef Adresi)**|Paketin ulaşması gereken cihazın IP adresi.|

🚀 **Özet:** **Paketler, cihazlar arası veri iletişimini sağlar ve ağın verimli çalışmasını destekleyen standart başlık bilgilerinden oluşur.**
## **📌 2.TCP/IP**
### **📌 TCP (Transmission Control Protocol) Nedir?**

TCP, cihazlar arasında güvenilir veri iletişimi sağlayan **bağlantı tabanlı** bir protokoldür. Veri iletimi öncesinde **Three-Way Handshake** süreciyle bağlantı kurar ve iletilen verinin eksiksiz ulaşmasını garanti eder.

🔹 **TCP/IP Modeli Katmanları:**  
1️⃣ **Application**  
2️⃣ **Transport (TCP burada çalışır)**  
3️⃣ **Internet**  
4️⃣ **Network Interface**

---

### **📌 TCP'nin Avantajları ve Dezavantajları**

|**Avantajlar**|**Dezavantajlar**|
|---|---|
|Veri bütünlüğünü garanti eder.|Yavaş bağlantılarda gecikmelere sebep olabilir.|
|Veri sırasını korur.|UDP'ye kıyasla daha yavaş çalışır.|
|Hata kontrolü yapar.|Güvenilirlik için daha fazla işlem gerektirir.|

---

### **📌 TCP Başlıkları (Headers)**

|**Başlık**|**Açıklama**|
|---|---|
|**Source/Destination Port**|Gönderen ve alıcı uygulamanın port numaraları.|
|**Source/Destination IP**|Paketi gönderen ve alan cihazın IP adresleri.|
|**Sequence & Acknowledgement Number**|Veri sırasını belirler ve onaylar.|
|**Checksum**|Verinin bozulup bozulmadığını kontrol eder.|
|**Flag**|Bağlantının nasıl yönetileceğini belirler.|

---

### **📌 Three-Way Handshake (Bağlantı Kurulumu)**

1️⃣ **SYN:** İstemci, bağlantı isteği gönderir.  
2️⃣ **SYN/ACK:** Sunucu, isteği kabul eder.  
3️⃣ **ACK:** İstemci, bağlantıyı onaylar ve veri iletimi başlar.

---

### **📌 TCP Bağlantıyı Kapatma**

🔹 **FIN-ACK-FIN-ACK Süreci:**  
1️⃣ **FIN:** Bağlantıyı kapatma isteği.  
2️⃣ **ACK:** Diğer taraf isteği onaylar.  
3️⃣ **FIN:** Karşı taraf da bağlantıyı sonlandırır.  
4️⃣ **ACK:** Son onay verilir ve bağlantı kapanır.

🚀 **Özet:** **TCP, güvenilir veri iletimi sağlar, ancak yavaş olabilir. Bağlantı kurulumu ve kapatılması belirli adımlarla gerçekleşir.**
## **📌 3. UDP**
### **📌 UDP (User Datagram Protocol) Nedir?**

UDP, **bağlantısız (stateless)** bir protokoldür ve **TCP'nin aksine veri kaybına karşı bir garanti sunmaz**. Bu nedenle, **video akışı, online oyunlar ve sesli görüşmeler** gibi hızın önemli olduğu yerlerde tercih edilir.

---

### **📌 UDP'nin Avantajları ve Dezavantajları**

|**Avantajlar**|**Dezavantajlar**|
|---|---|
|TCP'ye göre çok daha hızlıdır.|Veri kaybı yaşanabilir, iletilen veri doğrulanmaz.|
|Bağlantıyı sürekli açık tutmaz, sistem kaynaklarını daha az kullanır.|Dengesiz bağlantılarda performans düşebilir.|
|Uygulamalar, paketlerin nasıl gönderileceğini kontrol edebilir.|Hata kontrolü ve sıralama işlemi yapılmaz.|

---

### **📌 UDP Paket Başlıkları (Headers)**

|**Başlık**|**Açıklama**|
|---|---|
|**TTL (Time to Live)**|Paketin süresini belirler, süresi dolunca silinir.|
|**Source/Destination Address**|Gönderen ve alıcı IP adresleri.|
|**Source/Destination Port**|Paketin hangi porttan gönderildiği ve nereye ulaştığı.|
|**Data**|İletilen verinin bulunduğu alan.|

---

### **📌 UDP Bağlantı Süreci**

🔹 **UDP'de bağlantı kurulumu yoktur.** TCP'deki **Three-Way Handshake süreci gerçekleşmez** ve **veri doğrudan gönderilir**.

🚀 **Özet:** **UDP, hız odaklı bir protokoldür ancak veri kaybına karşı koruma sağlamaz. Online oyunlar, video akışı ve VoIP gibi uygulamalarda yaygın olarak kullanılır.**
## **📌 4.Ports**
### **📌 Port Nedir?**

Portlar, cihazların **belirli kurallar çerçevesinde veri alışverişi yapmasını sağlayan** sayısal değerlerdir (**0-65535** arasında). Liman ve iskele benzetmesiyle, her geminin sadece uygun iskeleye yanaşabileceği gibi, her veri türü de belirli portlardan iletilir.

---

### **📌 Yaygın Kullanılan Portlar ve Protokoller**

|**Protokol**|**Port Numarası**|**Açıklama**|
|---|---|---|
|**FTP**|21|Dosya transferi sağlar.|
|**SSH**|22|Güvenli uzaktan erişim.|
|**HTTP**|80|Web siteleri için veri iletimi.|
|**HTTPS**|443|Şifreli web veri iletimi.|
|**SMB**|445|Dosya ve cihaz paylaşımı.|
|**RDP**|3389|Uzak masaüstü bağlantısı.|

📌 **0-1024 arasındaki portlar "common (yaygın) portlar" olarak bilinir.**

---

### **📌 Özel ve Alternatif Port Kullanımı**

Standart portlar kullanılabilirken, **alternatif portlar da atanabilir** (örneğin, web sunucusu **80 yerine 8080** portunda çalıştırılabilir). Ancak, varsayılan port dışında çalıştırılan hizmetler **port numarasıyla belirtilmelidir** (örnek: `http://example.com:8080`).

🚀 **Özet:** **Portlar, cihazların belirli kurallar çerçevesinde haberleşmesini sağlar. Yaygın protokoller için standart portlar belirlenmiştir, ancak isteğe bağlı değiştirilebilir.**

