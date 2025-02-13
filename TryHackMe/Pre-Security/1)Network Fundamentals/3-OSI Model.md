🔹 **Veri her katmanda işlenir ve alt katmana ek bilgiler eklenir (Encapsulation).**

### **1️⃣ Fiziksel Katman (Physical Layer)**

- **İnternet kabloları, sinyaller, bağlantı türleri** bu katmandadır.
- **Örnek:** Ethernet kablosu, Wi-Fi sinyalleri.

### **2️⃣ Veri Bağı Katmanı (Data Link Layer)**

- **Cihazlar birbirine nasıl veri gönderecek?** Bu katman belirler.
- **MAC adresi** burada kullanılır. (Her cihazın benzersiz fiziksel adresi)
- **Hata tespiti yapar ve veriyi çerçeve (frame) hâline getirir.**
- **Örnek:** Switch'ler, MAC adresleriyle cihazları birbirine bağlar.

### **3️⃣ Ağ Katmanı (Network Layer)**

- **Veriler en kısa ve en hızlı yoldan nasıl gider?**
- **IP adresleri ve yönlendirme (Routing) bu katmanda gerçekleşir.**
- **Router’lar (Yönlendiriciler) burada çalışır.**
- **Örnek Protokoller:** OSPF, RIP

🚀 **Özet:** **IP adresleriyle cihazları bulur, en iyi yolu seçer.**

### **4️⃣ Taşıma Katmanı (Transport Layer)**

- **Veriyi böler, sıralar ve alıcıya ulaştığından emin olur.**
- **İki ana protokol vardır:**
    - **TCP (Güvenilir, yavaş) → Web, e-posta, dosya transferi.**
    - **UDP (Hızlı, güvensiz) → Oyunlar, canlı yayınlar.**

🚀 **Özet:** **TCP güvenilir, UDP hızlı.**

### **5️⃣ Oturum Katmanı (Session Layer)**

- **İki cihaz arasındaki bağlantıyı açar, yönetir ve kapatır.**
- **Kesinti olursa sadece eksik verileri tekrar gönderir (Checkpoints).**

🚀 **Özet:** **Bağlantı yönetimi sağlar.**

### **6️⃣ Sunum Katmanı (Presentation Layer)**

- **Veriyi sistemlerin anlayabileceği hâle getirir.**
- **Şifreleme & güvenlik burada yapılır (HTTPS gibi).**

🚀 **Özet:** **Veriyi formatlar ve şifreler.**

### **7️⃣ Uygulama Katmanı (Application Layer)**

- **Kullanıcıya en yakın katmandır.**
- **E-posta, web tarayıcıları, dosya transferi burada gerçekleşir.**
- **Örnek Protokoller:** HTTP, FTP, DNS

🚀 **Özet:** **Kullanıcının doğrudan etkileşimde olduğu katmandır.**