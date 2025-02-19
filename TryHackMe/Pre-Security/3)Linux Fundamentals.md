## **📌 1.1-Terminal ve Temel Linux Komutları**

Linux’un **hafif yapısı**, çoğu zaman **grafik arayüz (GUI) olmadan** çalışmasını gerektirir. Bu nedenle, **Terminal** kullanımı büyük önem taşır.

📌 **Terminal, sadece metin tabanlı komutlarla çalışır ve başta zorlayıcı görünebilir, ancak temel komutlarla hızla öğrenilebilir.**

---

### **📌 İlk Temel Komutlar**

|**Komut**|**Açıklama**|**Örnek Kullanım**|
|---|---|---|
|**echo**|Belirtilen metni ekrana yazdırır.|`echo "Merhaba Dünya!"`|
|**whoami**|Hangi kullanıcı ile giriş yapıldığını gösterir.|`whoami`|

📌 **Örnek Kullanım:**

```bash
tryhackme@linux1:~$ echo "Hello Friend!"
tryhackme@linux1:~$ whoami
```

🚀 **Özet:** **Linux’ta terminal kullanımı esastır. `echo` metin yazdırır, `whoami` ise giriş yapılan kullanıcıyı gösterir.**
## **📌 1.2-Linux Dosya Sistemi ile Çalışma**

Linux’ta **grafik arayüz (GUI) olmadan dosya sisteminde gezinmek için temel komutları bilmek gerekir**.

---

### **📌 Temel Dosya Yönetimi Komutları**

|**Komut**|**Açıklama**|**Örnek Kullanım**|
|---|---|---|
|**ls**|Bulunduğunuz dizindeki dosyaları ve klasörleri listeler.|`ls`|
|**cd**|Belirtilen dizine geçiş yapar.|`cd Pictures`|
|**cat**|Bir dosyanın içeriğini görüntüler.|`cat todo.txt`|
|**pwd**|Mevcut dizinin tam yolunu gösterir.|`pwd`|

---

### **📌 Kullanım Örnekleri**

🔹 **Bulunduğunuz dizindeki dosyaları listeleme:**

```bash
ls
```

📌 **"Documents", "Pictures" gibi klasörleri gösterir.**

🔹 **Dizin değiştirme (Örn: Pictures klasörüne gitme):**

```bash
cd Pictures
ls
```

📌 **Yeni dizindeki dosyaları listeler.**

🔹 **Bir dosyanın içeriğini görüntüleme:**

```bash
cat Documents/todo.txt
```

📌 **Belirtilen dosyanın içeriğini ekrana yazdırır.**

🔹 **Tam dosya yolunu öğrenme:**

```bash
pwd
```

📌 **Örn: `/home/ubuntu/Documents` sonucu döner.**

🚀 **Özet:** **`ls` içerikleri listeler, `cd` ile dizin değiştiririz, `cat` dosya içeriğini gösterir, `pwd` bulunduğumuz konumu belirtir.**
## **📌 1.3-Linux’ta Dosya ve İçerik Arama**

Linux, **dosya ve içerik aramak için güçlü komutlar sunar**. **`find` ve `grep`**, dosya isimlerini ve içeriklerini hızlıca bulmamıza yardımcı olur.

---

### **📌 `find` ile Dosya Arama**

|**Komut**|**Açıklama**|**Örnek Kullanım**|
|---|---|---|
|**find -name dosyaadı**|Belirtilen ada sahip dosyayı bulur.|`find -name passwords.txt`|
|*_find -name _.txt__|Belirtilen uzantıya sahip tüm dosyaları listeler.|`find -name *.txt`|

📌 **Örnek Çıktı:**

```bash
tryhackme@linux1:~$ find -name *.txt
./folder1/passwords.txt
./Documents/todo.txt
```

🚀 **Tüm `.txt` dosyalarını bulduk!**

---

### **📌 `grep` ile Dosya İçeriği Arama**

|**Komut**|**Açıklama**|**Örnek Kullanım**|
|---|---|---|
|**grep "aranan_kelime" dosya**|Dosyada geçen belirli bir kelimeyi arar.|`grep "81.143.211.90" access.log`|

📌 **Örnek Çıktı:**

```bash
81.143.211.90 - - [25/Mar/2021:11:17 +0000] "GET / HTTP/1.1" 200 417 "-" "Mozilla/5.0"
```

🚀 **Belirli bir IP’nin web sunucu loglarındaki hareketlerini bulduk!**

**Özet:**

- **`find` → Dosya ve uzantı arama**
- **`grep` → Dosya içeriğinde belirli kelimeleri bulma**
## **📌 1.4-Linux Operatörleri**

Linux operatörleri, **komutları daha verimli kullanmamızı sağlar**. İşte en yaygın 4 operatör:

|**Operatör**|**Açıklama**|**Örnek Kullanım**|
|---|---|---|
|**&**|Komutu **arka planda çalıştırır**.|`cp büyük_dosya &`|
|**&&**|**Komutları zincirleme çalıştırır** (ilk komut başarılı olursa ikinci çalışır).|`mkdir test && cd test`|
|**>**|**Çıktıyı dosyaya yönlendirir** (içeriği değiştirir).|`echo "Merhaba" > dosya.txt`|
|**>>**|**Çıktıyı dosyanın sonuna ekler** (içeriği korur).|`echo "Nasılsın?" >> dosya.txt`|

---

### **📌 Kullanım Örnekleri**

🔹 **Arka planda komut çalıştırma:**

```bash
cp büyük_dosya hedef_klasör &
```

📌 **Dosya kopyalama işlemi arka planda devam eder.**

🔹 **Zincirleme komut çalıştırma:**

```bash
mkdir yeni_klasör && cd yeni_klasör
```

📌 **Klasör oluştur ve içine gir (başarılı olursa).**

🔹 **Çıktıyı dosyaya yönlendirme:**

```bash
echo "Merhaba" > mesaj.txt
```

📌 **`mesaj.txt` içeriği "Merhaba" olarak değişir.**

🔹 **Çıktıyı dosyanın sonuna ekleme:**

```bash
echo "Nasılsın?" >> mesaj.txt
```

📌 **Dosyanın içeriği korunur ve sonuna "Nasılsın?" eklenir.**

🚀 **Özet:** **`&` arka planda çalıştırır, `&&` zincirleme komut çalıştırır, `>` çıktı yönlendirir, `>>` dosyanın sonuna ekler.**

## **📌 2.1-SSH (Secure Shell) ile Uzaktan Bağlantı**

SSH, **uzaktaki bir Linux makinesine güvenli bir şekilde bağlanmamızı sağlayan şifreli bir protokoldür**.

🔹 **SSH'nin Temel İşlevleri:**

- **Uzak makinede komut çalıştırma**
- **Trafiği şifreleyerek güvenli iletişim sağlama**

---

### **📌 SSH ile Bağlantı Kurma**

🔹 **Gerekli Bilgiler:**  
1️⃣ **Uzak makinenin IP adresi**  
2️⃣ **Geçerli kullanıcı adı ve şifre**

📌 **Örnek SSH Komutu:**

```bash
ssh tryhackme@10.10.70.3
```

1️⃣ **`tryhackme` kullanıcı adıyla bağlanıyoruz.**  
2️⃣ **Şifre sorulduğunda `tryhackme` giriyoruz.**  
3️⃣ **Bağlantı başarıyla kurulduğunda artık uzak makinede çalışıyoruz!**

🚀 **Özet:** **SSH, uzaktaki Linux makinelerine güvenli bağlantı sağlar. `ssh kullanıcı@IP` komutuyla giriş yapılır.**
## **📌 2.2-Linux Komutlarında Argümanlar ve Man Sayfaları**

📌 **Linux komutları, genellikle belirli davranışlarını değiştirmek veya genişletmek için argümanlar (flags veya switches) kullanır.**

---

### **📌 Linux Komutlarında Argümanlar (Flags / Switches)**

🔹 **Komutlar, varsayılan olarak belirli bir işlem yapar.**  
🔹 **Ancak, eklenen argümanlar komutların çıktısını değiştirebilir.**  
🔹 **Argümanlar genellikle `-` veya `--` ile başlar.**

---

### **📌 Örnek: `ls` Komutu**

✅ **Varsayılan kullanım:**

```bash
ls
```

👉 Çalıştırıldığında, geçerli dizindeki dosyaları listeler. Ancak, gizli dosyaları göstermez.

✅ **Gizli dosyaları görmek için:**

```bash
ls -a
```

👉 `-a` argümanı (`--all`), gizli dosyaları (`.` ile başlayanlar) da görüntüler.

✅ **Komutun tüm seçeneklerini görmek için:**

```bash
ls --help
```

👉 `--help`, komutun tüm kullanılabilir argümanlarını listeler.

---

### **📌 Man Sayfaları (Manual Pages)**

🔹 **Linux komutlarının detaylı belgelerine erişmek için `man` komutu kullanılır.**  
🔹 **Bu sayfalarda komutun açıklaması, seçenekleri ve örnek kullanımları bulunur.**

✅ **Örnek:** `ls` komutunun man sayfasını açmak için:

```bash
man ls
```

👉 **Man sayfasında gezinmek için:**

- **`Enter`** → Bir satır aşağı git
- **`Space`** → Bir sayfa aşağı git
- **`q`** → Çıkış yap

---

### **📌 Özet**

🚀 **Linux komutları, belirli işlevleri yerine getirirken, argümanlarla daha esnek hale gelir.**  
🚀 **Komutların desteklediği seçenekleri öğrenmek için `--help` veya `man` komutları kullanılabilir.**  
🚀 **Man sayfaları, komutlar hakkında en detaylı bilgiyi sağlar!**
## **📌 2.3-Linux Dosya ve Dizin İşlemleri**

📌 **Linux'ta dosya ve dizinlerle çalışırken, onları oluşturma, taşıma, kopyalama ve silme gibi işlemler yapmak için çeşitli komutlar kullanılır.**

---

### **📌 Temel Dosya ve Dizin Komutları**

|**Komut**|**Açılımı**|**Amacı**|
|---|---|---|
|`touch`|touch|Yeni bir dosya oluşturur|
|`mkdir`|make directory|Yeni bir klasör (dizin) oluşturur|
|`cp`|copy|Dosya veya klasörü kopyalar|
|`mv`|move|Dosya veya klasörü taşır veya adını değiştirir|
|`rm`|remove|Dosya veya klasörü siler|
|`file`|file|Bir dosyanın türünü belirler|

---

### **📂 Dosya ve Klasör Oluşturma (`touch`, `mkdir`)**

✅ **Boş bir dosya oluşturmak için:**

```bash
touch dosya.txt
```

📌 **Not:** `touch`, içeriği olmayan boş bir dosya oluşturur. İçerik eklemek için `echo` veya bir metin editörü (`nano`, `vim`, `cat >`) kullanılır.

✅ **Klasör (dizin) oluşturmak için:**

```bash
mkdir yeniklasor
```

👉 **Birden fazla klasör oluşturmak için:**

```bash
mkdir klasor1 klasor2 klasor3
```

✅ **İç içe dizinler oluşturmak için (`-p` flag'i ile):**

```bash
mkdir -p ana_klasor/alt_klasor
```

---

### **🗑 Dosya ve Klasör Silme (`rm`)**

✅ **Dosya silmek için:**

```bash
rm dosya.txt
```

✅ **Dizin silmek için (`-r` argümanı ile):**

```bash
rm -r klasor
```

✅ **Zorla (onay istemeden) silmek için (`-f` flag'i ile):**

```bash
rm -rf klasor
```

📌 **UYARI:** `rm -rf /` komutu, sistemdeki tüm dosyaları silebilir. Dikkatli olun!

---

### **📄 Dosya ve Klasör Kopyalama (`cp`)**

✅ **Dosya kopyalamak için:**

```bash
cp dosya1.txt dosya2.txt
```

👉 `dosya1.txt` içeriği, `dosya2.txt` içine kopyalanır.

✅ **Klasör kopyalamak için (`-r` argümanı ile):**

```bash
cp -r klasor1 klasor2
```

📌 `-r` (recursive) flag'i olmadan, klasör kopyalanamaz!

✅ **Birden fazla dosya veya dizini kopyalamak için:**

```bash
cp dosya1.txt dosya2.txt klasor/
```

---

### **📂 Dosya ve Klasör Taşıma veya Yeniden Adlandırma (`mv`)**

✅ **Dosyayı başka bir konuma taşımak için:**

```bash
mv dosya.txt yeni_klasor/
```

✅ **Dosya adını değiştirmek için:**

```bash
mv eski_ad.txt yeni_ad.txt
```

👉 `mv`, hem taşımak hem de ad değiştirmek için kullanılır.

✅ **Klasörü taşımak için:**

```bash
mv klasor1 yeni_klasor/
```

---

### **📌 Dosya Türünü Belirleme (`file`)**

✅ **Bir dosyanın türünü öğrenmek için:**

```bash
file dosya.txt
```

📌 **Örnek çıktı:**

```bash
dosya.txt: ASCII text
```

✅ **Bilinmeyen bir dosyanın içeriğini anlamak için:**

```bash
file gizli_dosya
```

📌 **Çıktı örneği:**

```bash
gizli_dosya: PNG image data, 800 x 600, 8-bit/color RGBA
```

---

### **📌 Özet**

🚀 **Dosya ve klasör işlemleri için temel komutlar:**

- `touch` → **Dosya oluşturur**
- `mkdir` → **Klasör oluşturur**
- `rm` → **Dosya veya klasör siler**
- `cp` → **Dosya veya klasör kopyalar**
- `mv` → **Dosya veya klasör taşır/adını değiştirir**
- `file` → **Dosyanın türünü belirler**

⚠ **Silme işlemlerinde dikkatli olun, özellikle `rm -rf` kullanırken!**
## **📌 2.4-Linux'ta Kullanıcılar, Gruplar ve Yetkiler**

Linux sistemlerinde **kullanıcılar** (users) ve **gruplar** (groups), dosya ve dizinlere belirli **izinler** (permissions) ile erişebilir. Bu yetkilendirme mekanizması, sistem güvenliğini sağlamak için oldukça önemlidir.

---

### **📂 Dosya ve Dizin İzinlerini Görüntüleme (`ls -l`)**

Bir dizindeki dosya ve klasörlerin sahiplerini ve izinlerini görmek için `ls -l` komutunu kullanabiliriz:

```bash
ls -lh
```

Örnek çıktı:

```bash
-rw-r--r-- 1 cmnatic cmnatic 0 Feb 19 10:37 file1
-rw-r--r-- 8 cmnatic cmnatic 0 Feb 19 10:37 file2
```

Bu çıktıda en önemli sütunlar:

1. **İzinler (Permissions)** → `-rw-r--r--`
2. **Sahip Kullanıcı (Owner User)** → `cmnatic`
3. **Sahip Grup (Owner Group)** → `cmnatic`

---

### **🔑 Linux İzinleri: `r`, `w`, `x` Ne Anlama Gelir?**

Linux'ta her dosya/dizin için **üç tür izin** vardır:

|Harf|Anlamı|Dosya İçin|Dizin İçin|
|---|---|---|---|
|`r`|**Read (Okuma)**|Dosya içeriğini okuyabilir|Klasördeki dosyaları listeleyebilir|
|`w`|**Write (Yazma)**|Dosya içeriğini değiştirebilir|Klasöre yeni dosya ekleyebilir/silebilir|
|`x`|**Execute (Çalıştırma)**|Dosyayı çalıştırabilir (örn: betik)|Klasöre erişebilir|

---

### **📋 Linux'ta Kullanıcılar ve Gruplar**

- **Sistem kullanıcıları**, belirli dosya ve dizinlere erişmek için yetkilendirilmiştir.
- **Gruplar**, birden fazla kullanıcıya ortak erişim sağlamak için oluşturulmuştur.

Örneğin, bir dosyanın sahibi bir kullanıcı olabilir ama belirli bir grup da erişim hakkına sahip olabilir.

**Örnek:**

```bash
-rwxr-xr-- 1 alice developers 1024 Feb 20 10:00 script.sh
```

- **alice** → Dosyanın sahibi
- **developers** → Dosyanın grubu
- **İzinler** → `rwxr-xr--`
    - **Sahip (alice)** → `rwx` → Okuma, yazma ve çalıştırma yetkisi var.
    - **Grup (developers)** → `r-x` → Sadece okuma ve çalıştırma yetkisi var.
    - **Diğerleri (other)** → `r--` → Sadece okuma yetkisi var.

---

### **🔄 Kullanıcı Değiştirme (`su` ve `sudo`)**

Linux'ta bir kullanıcıdan diğerine geçmek için `su` ve `sudo` komutları kullanılır.

#### **👤 `su` ile Kullanıcı Değiştirme**

`su` komutu ile başka bir kullanıcıya geçiş yapabilirsiniz.

📌 **Örnek:**

```bash
su user2
```

📌 **Eğer `-l` (login) parametresi eklenirse:**

```bash
su -l user2
```

Bu durumda, `user2` kullanıcısının **varsayılan kabuğuna ve home dizinine** giriş yapmış olursunuz.

#### **🔧 `sudo` ile Yetkili İşlem Yapma**

Bazı komutlar için **root yetkisi** gereklidir. Bunun için `sudo` kullanılır.

📌 **Örnek:**

```bash
sudo apt update
```

📌 Eğer root kullanıcı olarak oturum açmak isterseniz:

```bash
sudo su
```

---

### **🎯 Özet:**

- **Dosya izinlerini görmek için:** `ls -lh`
- **İzin türleri:** `r` (okuma), `w` (yazma), `x` (çalıştırma)
- **Kullanıcı değiştirme:** `su username`
- **Yetkili işlemler için:** `sudo komut`

Bu komutlar, Linux'ta dosya izinlerini yönetmek ve kullanıcı hesapları arasında geçiş yapmak için gereklidir. 🚀
## **📌 2.5-Linux'taki Önemli Dizimler ve Kullanımları**

Linux'ta, sistemin düzgün çalışmasını sağlayan **root dizinleri** vardır. Bu dizinler, belirli türdeki verileri saklamak için özel olarak tasarlanmıştır. İşte en yaygın kullanılan dizinlerden bazıları:

---

### **📂 `/etc` - Sistem Yapılandırma Dosyaları**

- **Açılımı:** "etcetera"
- **Görevi:** Çeşitli **sistem yapılandırma** dosyalarını saklar.
- **Önemli Dosyalar:**
    - **`sudoers`** → Hangi kullanıcıların `sudo` komutunu çalıştırabileceğini belirler.
    - **`passwd`** → Kullanıcı hesap bilgilerini içerir.
    - **`shadow`** → Kullanıcı şifrelerinin şifrelenmiş biçimde saklandığı dosya.

📌 **Örnek:**

```bash
ls /etc
cat /etc/passwd
cat /etc/shadow
```

---

### **📂 `/var` - Değişken Veri Depolama**

- **Açılımı:** "variable" (değişken)
- **Görevi:** **Sürekli değişen** verileri saklar (loglar, önbellekler, vs.).
- **Önemli Alt Dizinler:**
    - **`/var/log/`** → Sistem ve servis loglarını tutar.
    - **`/var/tmp/`** → Kalıcı geçici dosyalar.
    - **`/var/backups/`** → Yedekleme dosyaları.
    - **`/var/opt/`** → Harici programlar için değişken veriler.

📌 **Örnek:**

```bash
ls /var
ls /var/log
cat /var/log/syslog
```

---

### **📂 `/root` - Root Kullanıcısının Ev Dizini**

- **Görevi:** **Root (yönetici) kullanıcısının** özel dizinidir.
- **Not:** Normal kullanıcılar buraya erişemez.

📌 **Örnek:**

```bash
sudo ls /root
```

---

### **📂 `/tmp` - Geçici Dosyalar**

- **Açılımı:** "temporary"
- **Görevi:** **Geçici dosyaları** saklar.
- **Özellikleri:**
    - **Tüm kullanıcılar yazabilir.**
    - **Sistem yeniden başlatıldığında içeriği silinir.**

📌 **Örnek:**

```bash
ls /tmp
echo "Deneme dosyası" > /tmp/test.txt
cat /tmp/test.txt
```

---

### **🎯 Özet**

|**Dizin**|**Görevi**|
|---|---|
|**`/etc`**|Sistem yapılandırma dosyalarını saklar.|
|**`/var`**|Sürekli değişen verileri ve logları saklar.|
|**`/root`**|Root kullanıcısının özel ev dizini.|
|**`/tmp`**|Geçici dosyalar için kullanılır, sistem yeniden başlatıldığında temizlenir.|

Bu bilgiler, Linux sistemlerini daha iyi anlamanızı ve yönetmenizi sağlayacaktır. 🚀
## **📌 3.1-Linux Terminal Metin Editörleri: Nano ve VIM**

Linux'ta metin dosyalarıyla çalışırken terminal tabanlı metin editörleri oldukça kullanışlıdır. Daha önce **`echo`** ve yönlendirme operatörleri (`>`, `>>`) ile dosyalara metin yazmayı öğrendik. Ancak, bu yöntem büyük ve çok satırlı dosyalarla çalışırken verimsizdir.

Bu yüzden **Nano ve VIM** gibi terminal metin editörlerini kullanmayı öğrenmek önemlidir.

---

### **📝 Nano: Basit ve Kullanıcı Dostu Metin Editörü**

Nano, Linux'ta kullanımı kolay bir metin editörüdür ve yeni başlayanlar için mükemmeldir.

### **📌 Nano ile Dosya Oluşturma veya Düzenleme**

Aşağıdaki komut ile bir dosya açabilir veya yeni bir dosya oluşturabilirsiniz:

```bash
nano myfile
```

📌 **Nano açıldığında ekran şöyle görünür:**

```
GNU nano 4.8                                         myfile        

Hello TryHackMe
I can write things into "myfile"

^G Get Help  ^O Write Out  ^W Where Is  ^K Cut Text  ^J Justify  ^C Cur Pos
^X Exit      ^R Read File  ^\ Replace   ^U Paste     ^T To Spell ^_ Go To Line
```

### **📌 Nano’da Kullanışlı Kısayollar**

| **Kısayol**            | **Açıklama**            |
| ---------------------- | ----------------------- |
| **`CTRL + X`**         | Çıkış                   |
| **`CTRL + O + ENTER`** | Dosyayı kaydet (yazdır) |
| **`CTRL + W`**         | Metin içinde arama yap  |
| **`CTRL + K`**         | Satır kes               |
| **`CTRL + U`**         | Yapıştır                |
| **`CTRL + T`**         | Yazım denetimi          |
| **`CTRL + _`**         | Satıra git              |

---

### **🔥 VIM: Güçlü ve Esnek Metin Editörü**

Nano basit ve kullanışlı olsa da, **VIM (Vi IMproved)** çok daha gelişmiş bir editördür. Yazılım geliştiriciler ve ileri düzey Linux kullanıcıları arasında popülerdir.

### **📌 VIM’in Avantajları**

✅ **Özelleştirilebilir**: Kendi kısayollarınızı ve eklentilerinizi ekleyebilirsiniz.  
✅ **Syntax Highlighting**: Kod yazarken sözdizimini renklendirir.  
✅ **Tüm terminallerde çalışır**: Nano her zaman yüklü olmayabilir ama VIM genellikle bulunur.

### **📌 VIM Kullanımı**

**VIM'i başlatmak için:**

```bash
vim myfile
```

VIM’de **3 ana mod** vardır:

1. **Normal Mod**: Varsayılan başlangıç modu. Burada komutlar çalıştırabilirsiniz.
2. **Insert Mod**: Metin yazmak için **`i`**, **`a`**, veya **`o`** tuşlarına basarak geçebilirsiniz.
3. **Command Mod**: **`:w`** ile kaydetme, **`:q`** ile çıkma gibi komutlar girilir.

### **📌 VIM’de Kullanışlı Kısayollar**

|**Komut**|**Açıklama**|
|---|---|
|**`:w`**|Dosyayı kaydet|
|**`:q`**|Çıkış|
|**`:wq`**|Kaydedip çıkış yap|
|**`:q!`**|Kaydetmeden çıkış yap|
|**`i`**|Yazma moduna geç|
|**`ESC`**|Normal moda dön|
|**`/kelime`**|Metin içinde arama yap|
|**`dd`**|Satırı sil|
|**`yy`**|Satırı kopyala|
|**`p`**|Yapıştır|

---

### **📌 Sonuç**

|**Editör**|**Avantajlar**|**Dezavantajlar**|
|---|---|---|
|**Nano**|Kolay ve kullanıcı dostu|Gelişmiş özellikler sınırlı|
|**VIM**|Güçlü, özelleştirilebilir, her terminalde çalışır|Öğrenmesi zaman alır|

📌 **Başlangıç için Nano önerilir**, ancak Linux’u daha iyi öğrenmek ve geliştirmek için VIM öğrenmek faydalıdır! 🚀
## **📌 3.2-Faydalı Linux Araçları: Dosya Transferi ve Sunucu Çalıştırma**

Linux'ta dosya transferi ve paylaşımı oldukça yaygın bir işlemdir. Bu yazıda **wget**, **scp**, ve **Python HTTP Server** gibi yöntemlerle dosya indirmenin, aktarmanın ve paylaşmanın nasıl yapılacağını öğreneceğiz.

---

### **📥 Wget ile Dosya İndirme**

Linux’ta internetten dosya indirmek için **wget** kullanabiliriz.

📌 **Örnek Kullanım:**  
Bir dosyayı indirmek için aşağıdaki komutu kullanabilirsiniz:

```bash
wget https://assets.tryhackme.com/additional/linux-fundamentals/part3/myfile.txt
```

Bu komut, belirtilen URL’den **myfile.txt** dosyasını bulunduğunuz dizine indirir.

📌 **Wget'in Faydaları:**  
✅ Basit ve hızlıdır.  
✅ HTTP, HTTPS ve FTP protokollerini destekler.  
✅ Büyük dosyalar indirirken kaldığı yerden devam edebilir (**-c** seçeneği).

📌 **Faydalı Wget Seçenekleri:**

|**Seçenek**|**Açıklama**|
|---|---|
|**`-c`**|İndirme kesilirse kaldığı yerden devam eder.|
|**`-b`**|Arka planda indirme yapar.|
|**`-q`**|Sessiz modda çalışır (çıktı vermez).|
|**`-O filename`**|Dosya ismini değiştirerek indirir.|

Örnek:

```bash
wget -c -O yeni_ad.txt https://example.com/file.txt
```

---

### **🔁 SCP ile Güvenli Dosya Transferi**

**SCP (Secure Copy Protocol)**, **SSH** kullanarak dosya ve dizinleri güvenli bir şekilde uzaktaki sistemlere kopyalamak için kullanılır.

#### **📌 Yerelden Uzak Sunucuya Dosya Gönderme**

📌 **Örnek Senaryo:**

|**Bilgi**|**Değer**|
|---|---|
|**Hedef IP**|192.168.1.30|
|**Uzak kullanıcı**|ubuntu|
|**Yerel dosya**|important.txt|
|**Hedef dosya adı**|transferred.txt|

📌 **Komut:**

```bash
scp important.txt ubuntu@192.168.1.30:/home/ubuntu/transferred.txt
```

Bu komut, **important.txt** dosyasını, **ubuntu** kullanıcısı ile **192.168.1.30** IP adresindeki uzak sisteme gönderir.

#### **📌 Uzak Sunucudan Yerel Bilgisayara Dosya Çekme**

📌 **Örnek Senaryo:**

|**Bilgi**|**Değer**|
|---|---|
|**Hedef IP**|192.168.1.30|
|**Uzak kullanıcı**|ubuntu|
|**Uzak dosya**|documents.txt|
|**Yerel dosya adı**|notes.txt|

📌 **Komut:**

```bash
scp ubuntu@192.168.1.30:/home/ubuntu/documents.txt notes.txt
```

Bu komut, **documents.txt** dosyasını uzaktaki sistemden çekip **notes.txt** olarak kaydeder.

#### **📌 SCP ile Dizin Kopyalama**

Tüm bir klasörü taşımak için **`-r`** parametresi kullanılır:

```bash
scp -r myfolder ubuntu@192.168.1.30:/home/ubuntu/
```

Bu komut, **myfolder** dizinini uzaktaki sunucuya kopyalar.

📌 **SCP Avantajları:**  
✅ Güvenlidir (SSH ile şifrelenmiş bağlantı kullanır).  
✅ Hızlıdır ve kullanıcı adı + parola veya SSH anahtarları ile çalışır.  
✅ Basit bir şekilde dosya ve dizin transferine imkan tanır.

---

### **🌍 Python HTTP Server ile Dosya Paylaşımı**

Eğer bir dosyayı hızlıca paylaşmak istiyorsanız, **Python HTTP Server** kullanabilirsiniz. Bu yöntem, basit bir web sunucusu başlatarak dosyalarınızı internet veya yerel ağ üzerinden paylaşmanıza olanak tanır.

#### **📌 Python HTTP Server Başlatma**

Bulunduğunuz dizini sunucu olarak çalıştırmak için:

```bash
python3 -m http.server
```

📌 Varsayılan olarak **port 8000** üzerinden çalışır. Çıktı şu şekilde olur:

```
Serving HTTP on 0.0.0.0 port 8000 (http://0.0.0.0:8000/)
```

#### **📌 Belirli Bir Port Kullanma**

Varsayılan **8000** yerine başka bir portta çalıştırmak için:

```bash
python3 -m http.server 8080
```

📌 Eğer bir dizindeki dosyaları paylaşmak istiyorsanız, ilgili dizine geçip komutu çalıştırabilirsiniz:

```bash
cd /home/user/shared
python3 -m http.server
```

Bu, **/home/user/shared** klasörünü web sunucusu haline getirir.

#### **📌 Wget ile Paylaşılan Dosyayı İndirme**

Başka bir cihazdan dosya indirmek için **wget** kullanabilirsiniz:

```bash
wget http://10.10.30.65:8000/myfile
```

📌 **Önemli Not:** Python HTTP Server açık olduğu sürece çalışır. Sunucuyu kapatmak için **CTRL + C** tuşlarına basabilirsiniz.

📌 **Python HTTP Server’ın Avantajları:**  
✅ Kurulum gerektirmez, Python ile hazır gelir.  
✅ Hızlı ve basittir.  
✅ Dosya paylaşımı için ideal bir çözümdür.

📌 **Python HTTP Server Dezavantajları:**  
❌ Dosya dizinleri için indeksleme yapmaz, dosya adlarını tam bilmeniz gerekir.  
❌ Gelişmiş özellikler sunmaz, sadece basit dosya paylaşımı yapabilir.

📌 Alternatif olarak **Updog** gibi daha gelişmiş bir araç kullanılabilir.

---

### **🚀 Sonuç: Hangi Yöntemi Kullanmalısınız?**

|**Yöntem**|**Ne İşe Yarar?**|**Ne Zaman Kullanmalısınız?**|
|---|---|---|
|**wget**|İnternetten dosya indirir|Webden bir dosya çekmek istediğinizde|
|**scp**|SSH üzerinden güvenli dosya aktarımı yapar|İki bilgisayar arasında güvenli kopyalama yapmak istediğinizde|
|**Python HTTP Server**|Basit bir web sunucu başlatır|Dosyalarınızı başka bir cihazla paylaşmak istediğinizde|

---

Bu yöntemleri kullanarak dosya transferi konusunda yetkin hale gelebilirsiniz! 🚀