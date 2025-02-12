- Open Systems Interconnection Model
- Her katmanda veriye bilgi parçaları eklenir. Buna encapsulation denir.
### Layer 1 - Physical
- En alt katmandır. Fiziksel olarak internet kablolarıyla veri iletilir.
### Layer 2 - Data Link
- **Data Link Layer**, bilgisayar ağlarında iki cihazın **birbirine nasıl veri göndereceğini belirleyen** bir katmandır. Şunları yapar:

1. **Fiziksel adresleme**:
    
    - Bilgisayarlar internette **IP adresleriyle** tanımlanır ama yerel ağda (örneğin Wi-Fi veya Ethernet) **MAC adresleri kullanılır**.
    - **MAC adresi**, her ağ kartına (NIC-Network Interface Card) üretici tarafından atanmış **benzersiz bir numaradır** ve cihazları fiziksel olarak tanımlar.
    - Veri bağlantı katmanı, ağdan gelen pakete **doğru MAC adresini ekler**, böylece veri hedefe ulaşabilir.
2. **Veri paketlerini çerçeveleme (framing)**:
    
    - Üst katmanlardan gelen veriyi, iletime uygun **çerçeveler (frames)** haline getirir.
    - Çerçevenin içine hedef cihazın **MAC adresini**, gönderenin **MAC adresini** ve kontrol bilgilerini ekler.
3. **Hata tespiti ve düzeltme**:
    
    - Gönderilen verinin bozulup bozulmadığını kontrol eder ve **bazı hataları düzeltebilir**.

Yani veri bağlantı katmanı, IP adreslerini **fiziksel MAC adreslerine çevirerek** doğru cihazlara yönlendirme yapar ve verinin sorunsuz iletilmesini sağlar.
### Layer 3 - Network
- **Bu katmanda iki temel işlev vardır:**
    
    1. **Yönlendirme (Routing):** Verinin en **optimum** yolu kullanarak hedefe ulaşmasını sağlar.
    2. **Yeniden birleştirme (Re-assembly):** Küçük parçalara ayrılan veriyi tekrar birleştirir.
- **Bu süreçte kullanılan protokoller:**
    
    - **OSPF (Open Shortest Path First)**
    - **RIP (Routing Information Protocol)**
- **Katman 3 Cihazları:** **Router’lar (Yönlendiriciler)**, IP adreslerini kullanarak paketleri yönlendiren cihazlardır.
    

🚀 **Kısaca:** 3. katman, ağ üzerindeki **veri yönlendirme işlemlerini** gerçekleştirir ve IP adresleri ile çalışır!
### Layer 4 - Transport
OSI modelinin 4. katmanı olan Taşıma Katmanı, ağ üzerinden veri iletiminde önemli bir rol oynar. Bu katmanda, veri iletimi için iki ana protokol kullanılır: TCP (Transmission Control Protocol) ve UDP (User Datagram Protocol).

**TCP (Transmission Control Protocol):**

- **Güvenilirlik:** TCP, veri iletiminde yüksek güvenilirlik sunar. Verilerin doğru ve eksiksiz bir şekilde ulaşmasını garanti eder.
    
- **Hata Kontrolü:** Veri paketlerinin doğru sırayla alınıp birleştirilmesini sağlar.
    
- **Bağlantı Tabanlı:** İki cihaz arasında sürekli bir bağlantı gerektirir. Bir veri paketi alınmazsa, tüm veri bloğu kullanılamaz.
    
- **Yavaşlık:** Daha fazla işlem gerektirdiği için UDP'ye göre daha yavaştır.
    
- **Kullanım Alanları:** Dosya paylaşımı, internet tarama ve e-posta gönderme gibi veri bütünlüğünün önemli olduğu durumlarda kullanılır.
    

**UDP (User Datagram Protocol):**

- **Hızlı İletim:** UDP, hızlı veri iletimi için tasarlanmıştır. Verilerin ulaşıp ulaşmadığını kontrol etmez.
    
- **Bağlantısız:** İki cihaz arasında sürekli bir bağlantı gerektirmez. Veri paketleri kaybolabilir veya yanlış sırada ulaşabilir.
    
- **Esneklik:** Yazılım geliştiricilere, paketlerin ne kadar hızlı gönderileceği konusunda esneklik sağlar.
    
- **Kullanım Alanları:** Küçük veri paketlerinin gönderildiği durumlarda (cihaz keşfi protokolleri gibi) veya video akışı gibi bazı veri kayıplarının kabul edilebildiği durumlarda kullanılır.
    

Özetle, TCP güvenilir ve doğru veri iletimi için tercih edilirken, UDP hızlı ve esnek veri iletimi için kullanılır.
### Layer 5 - Session
- **Oturum Açma & Yönetme:**
    
    - **Bağlantıyı başlatır, yönetir ve sonlandırır.**
    - Başka bir bilgisayarla **iletişim kurarken bir oturum oluşturur** ve bu oturum açık kaldığı sürece bağlantıyı sürdürür.
- **Oturum Kapanışı:**
    
    - **Bağlantı uzun süre kullanılmazsa** veya **koparsa** oturum kapatılır.
- **Veri Kaybı Önleme (Checkpoints):**
    
    - **Checkpoints (kontrol noktaları) kullanarak**, bağlantı koparsa sadece **eksik veriler tekrar gönderilir**, böylece **bant genişliği korunur**.
- **Önemli Not:**
    
    - **Her oturum benzersizdir**, yani veriler **sadece kendi oturumları içinde** iletilir, farklı oturumlar arasında geçiş yapamaz.

🚀 **Özet:** 5. katman, **bağlantıları yönetir ve veri kaybını önleyerek** verimli bir iletişim sağlar!
### Layer 6 - Presentation
- **Standartlaştırma:**
    
    - **Farklı yazılımların aynı veriyi düzgün işleyebilmesini sağlar.**
    - Örneğin, farklı e-posta istemcileri olsa bile **gönderilen e-posta herkes tarafından okunabilir**.
- **Veri Çevirisi:**
    
    - **7. katman (Application Layer) ile iletişim kurar** ve veriyi **gönderilecek sisteme uygun formata çevirir**.
- **Güvenlik & Şifreleme:**
    
    - **HTTPS gibi veri şifreleme işlemleri bu katmanda yapılır.**

🚀 **Özet:** 6. katman, **verileri standart hale getirir, çeviri yapar ve güvenliği sağlar!**
### Layer 7 - Application
- **Kullanıcıya En Yakın Katman:**
    
    - Kullanıcıların doğrudan etkileşim kurduğu **uygulamalar ve servisler** bu katmanda çalışır.
    - Örneğin, **e-posta istemcileri, web tarayıcıları ve dosya aktarım yazılımları (FileZilla gibi)**.
    - Kullanıcı "Graphical User Interface" ile etkileşime girer.
- **Protokoller ve Kurallar:**
    
    - **Veri gönderme ve alma süreçlerini yönetir** ve kullanıcı deneyimini düzenler.
    - **DNS (Domain Name System)** gibi servisler, **web adreslerini IP adreslerine çevirir**.

🚀 **Özet:** 7. katman, **kullanıcıların ağ ile doğrudan etkileşimde bulunduğu katmandır** ve web, e-posta, dosya aktarımı gibi hizmetleri sağlar!