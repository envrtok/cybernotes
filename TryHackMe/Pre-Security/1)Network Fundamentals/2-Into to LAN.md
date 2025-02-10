## *2.1)LAN Topolojileri*
### *2.1.1)Star Topoloji*
![[Pasted image 20250210154939.png]]
- Cihazlar, merkezi bir ağ cihazına ayrı ayrı bağlanır.
- Bir cihazın gönderdiği bilgi, merkez cihaz üzerinden iletilir.
- Kablolama ihtiyacı çok olduğundan maliyetlidir.
- Yeni cihaz eklemek çok kolaydır.
- Arıza ihtimali düşüktür, ancak olası arızanın giderilmesi zordur.
- Fazla bakım gerektirir.
### *2.1.2)Bus Topoloji*
![[Pasted image 20250210155419.png]]
- Cihazlar omurga kablosu olarak bilinen tek bir bağlantıya dayanır.
- Her cihaz aynı kabloyu kullandığından, veri talebi arttığında yavaşlama ve darboğaz olabilir.
- Sorun oluştuğunda hangi cihazdan kaynaklandığını bulmak zordur.
- Kurulumu kolay ve maliyeti düşüktür.
### *2.1.3)Ring/Token Topoloji*
![[Pasted image 20250210155841.png]]
- Az kablolama gerektirme ve merkezi cihaza bağlılık olmaması açısından Bus Topoloji'ye benzer.
- Cihazlar, kendi verilerini öncelikli olarak gönderirler. Eğer kendi verileri yoksa, başka cihazlardan gelen veriyi iletirler. Bu mekanizma, veri iletiminde bir tür öncelik sistemi oluşturur.
- Arızaları gidermek oldukça kolaydır.
- Verinin ulaşımı açısından verimli değildir, çünkü birçok cihazdan geçmek zorundadır.
- Veri trafiği arttığında darboğaz yaşanmaz.
- Kopuk bir cihaz veya kesik bir kablo olursa tüm ağ çöker.
### *2.1.4)Switch & Router*
![[Pasted image 20250210160637.png]]
- **Switch**ler, birden fazla cihazı bir araya getirmek için tasarlanmışlardır.
- Okullar, işletmeler gibi büyük ağlarda bulunurlar.
- Diğer ağ cihazlarına göre daha verimlidirler. Bir paket aldıklarında bu paketi sadece hedef cihaza gönderirler. (Hub ise aldığı paketi tüm cihazlara gönderir.)
- Switch ve router'ların birbirine bağlanabilir. Bu durum ağda birden fazla veri yolu oluştur, ağın güvenilirliğini artırır ve kesintisiz çalışmayı mümkün kılar. Performanstaki küçük bir düşüş, bu avantajlar karşısında kabul edilebilir bir durumdur.
![[Pasted image 20250210161432.png]] 
- **Router**'in görevi ağları birbirine bağlamak ve aralarında veri aktarmaktır.

## *2.2)Subnetting(Premier)*
#### **2.2.1) Subnetting (Alt Ağ Oluşturma) Nedir?**
Subnetting, büyük bir ağı **küçük parçalara** bölmektir.

Neden yaparız?  
✅ **Ağ trafiğini azaltır ve hızlandırır.**  
✅ **Daha güvenli ve yönetilebilir bir yapı oluşturur.**  
✅ **Farklı bölümlere ayrılmış şirketler, okullar, kafeler için gereklidir.**

Bir şirket düşünelim:

- **192.168.1.0/24** → **Muhasebe**
- **192.168.2.0/24** → **IT Departmanı**
- **192.168.3.0/24** → **Müşteriler için Wi-Fi**

Böylece muhasebe bilgisayarları sadece kendi ağıyla çalışırken, IT departmanı veya müşteriler ayrı ağlarda olur.

---

#### **2.2.2). Subnet Mask (Alt Ağ Maskesi) Nedir?**
Subnet mask, IP adresinin **hangi kısmının "ağ" hangisinin "cihaz" olduğunu** belirler.

Örneğin **192.168.1.1** IP adresini alalım:

- Eğer subnet mask **255.255.255.0** ise:
    - **192.168.1** → Ağ kısmı
    - **.1** → Cihaz kısmı
- Bu durumda **192.168.1.0 – 192.168.1.255** arası aynı ağdadır.

Ama eğer subnet mask **255.255.0.0** olsaydı:

- **192.168** → Ağ kısmı
- **.1.1** → Cihaz kısmı
- Bu durumda **192.168.0.0 – 192.168.255.255** arası aynı ağda olurdu.

**Subnet mask, ağı daha küçük veya büyük yapmak için kullanılır.**

---

#### **2.2.3). Özet: IP & Subnetting İlişkisi**
- **IP adresi**, bir cihazın ağdaki adresidir.
- **Subnet mask**, IP adresinin **hangi kısmının ağ, hangi kısmının cihaz olduğunu** belirler.
- **Subnetting**, büyük bir ağı daha küçük ağlara bölerek güvenlik ve verimlilik sağlar.

📌 **Gerçek Hayat Örneği:**  
Bir kafede:

- **192.168.1.0/24** → Çalışanlar için özel ağ
- **192.168.2.0/24** → Müşteri Wi-Fi ağı

Bu sayede çalışanların sistemleri müşterilerden izole edilir.
## *2.3)ARP(Address Resoluiton Protocol)*
- **ARP**, cihazların **IP adreslerini MAC adresleriyle eşleştirmesini** sağlayan bir protokoldür.
- **Her cihaz**, ağdaki diğer cihazların MAC adreslerini kaydettiği bir **ARP cache (önbellek)** tutar.
- **Cihazlar haberleşirken**, hedef cihazın MAC adresini bilmiyorsa, **ARP Request (istek)** gönderir.
- Bu istek, **"Bu IP adresine sahip cihaz kim?"** diye tüm ağa yayınlanır.
- Eğer bir cihaz o IP adresine sahipse, **ARP Reply (cevap)** göndererek kendi **MAC adresini** paylaşır.
- Cihaz, bu bilgiyi ARP önbelleğinde saklar ve **gelecekte daha hızlı iletişim kurar**.
## *2.4)DHCP(Dynamic Host Control Protocol)*
- **IP adresleri iki şekilde atanabilir:**
    
    1. **Manuel:** Elle cihazın ayarlarına girerek.
    2. **Otomatik:** **DHCP sunucusu** tarafından atanarak (en yaygın yöntem).
- **DHCP Süreci (4 Aşama)**
    
    1. **DHCP Discover:** Cihaz, ağa bağlandığında bir **IP adresi** almak için yaygın bir istek yollar.
    2. **DHCP Offer:** Ağdaki **DHCP sunucusu**, kullanılabilir bir **IP adresi** önerir.
    3. **DHCP Request:** Cihaz, kendisine teklif edilen **IP adresini** kullanmak istediğini bildirir.
    4. **DHCP ACK:** DHCP sunucusu, talebi onaylar ve cihaz artık **IP adresini** kullanmaya başlar.