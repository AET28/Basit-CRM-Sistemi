# Müşteri Defteri - CRM Sistemi

Müşteri ilişkilerinin, satış kayıtlarının ve gelen destek/iş taleplerinin merkezi olarak yönetilebildiği, modern ve minimalist bir masaüstü CRM (Müşteri İlişkileri Yönetimi) otomasyonudur. PyQt5 altyapısı üzerinde, kurumsal tasarım yönergeleri ve Nesne Yönelimli Programlama (OOP) prensipleri kullanılarak, güvenli katmanlı mimari (Frontend/Backend) modeliyle geliştirilmiştir.

---

### 🚀 Teknolojiler

* **Python 3** - Temel programlama dili
* **PyQt5 (>=5.15.0)** - Masaüstü GUI (Grafik Kullanıcı Arayüzü) framework'ü
* **JSON** - Veri kalıcılığı ve yerel ilişkisel veritabanı yönetimi
* **Fusion Style** - Modern ve platformlar arası tutarlı arayüz stili

---

### 📂 Proje Yapısı

```text
crm_sistemi/
├── main.py                          # Uygulamanın ana giriş noktası ve başlatıcı
├── requirements.txt                 # Üçüncü parti kütüphane bağımlılıkları
├── data/                            # JSON formatında yerel veritabanı dosyaları
│   └── kullanicilar.json            # Sistem kullanıcıları ve kimlik doğrulama verileri
├── backend/
│   ├── __init__.py
│   ├── veri_yoneticisi.py           # CRM iş mantığı, CRUD işlemleri ve istatistik motoru
│   ├── auth.py                      # Kullanıcı oturum yönetimi ve doğrulama modülü
│   └── seed.py                      # Veritabanı boşsa devreye giren örnek veri yükleyici
└── frontend/
    ├── __init__.py
    ├── ana_pencere.py               # Ana kontrol paneli ve modül navigasyonu
    ├── login.py                     # Yetkili kullanıcı giriş ekranı (Dialog)
    └── tema.py                      # Kurumsal renk paleti ve UI stil şablonları (ANA_STIL)

🧠 Ana Yapı ve İş Mantığı Katmanları
🔐 Kimlik Doğrulama Yönetimi (backend/auth.py -> AuthYoneticisi)

    Özellikler: kullanicilar_dosyasi yolu

    Metodlar: kullanici_var_mi(), varsayilan_kullanici_olustur(), kullanici_dogrula(ad, sifre)

⚙️ Veri Yönetim Merkezi (backend/veri_yoneticisi.py -> VeriYoneticisi)

    Özellikler: veri_klasoru referansı, müşteri/satış/talep veri kümeleri

    Metodlar: tum_talepler(), genel_istatistikler() (Anlık CRM metrik analizi)

🎨 Grafik Arayüz Yönetimi (frontend/)

    LoginPenceresi (login.py): Uygulama güvenliğini sağlayan, ana pencere öncesi çalışan modal giriş ekranı.

    AnaPencere (ana_pencere.py): Yüksek DPI ölçeklendirme destekli, dinamik CRM özet grafikleri ve tablolarını içeren ana dashboard.

✨ Temel Özellikler

    Merkezi CRM Paneli (Dashboard): Şirket genelindeki toplam müşteri sayısını, toplam satış hacmini ve bekleyen talepleri tek bir ekranda analiz eden istatistiksel özet motoru.

    Katmanlı Güvenlik (Auth Gate): Sistem doğrulanmış bir kullanıcı oturumu (aktif_kullanici) almadan ana ekranın açılmasını engelleyen güvenli mimari yapısı.

    Akıllı Veri Besleyici (Auto-Seed): Sistem ilk kez çalıştırıldığında veya yerel veritabanı boş olduğunda otomatik olarak örnek müşterileri, satışları ve talepleri sisteme entegre eden geliştirici dostu test mekanizması.

    Yüksek Çözünürlük (DPI) Desteği: Modern ekranlarda grafiklerin ve arayüz elemanlarının bulanıklaşmasını önleyen AA_EnableHighDpiScaling entegrasyonu.

    Kurumsal Tasarım Dili: Segoe UI tipografik hiyerarşisine sahip, temiz, göz yormayan ve modern "Fusion" arayüz giydirmesi (ANA_STIL).

🛠️ Kurulum ve Çalıştırma

Gerekli bağımlılıkları yüklemek ve CRM sistemini başlatmak için terminalinizde sırasıyla şu komutları çalıştırın:
Bash

pip install -r requirements.txt
python main.py

🔒 Varsayılan Giriş Bilgileri

Sistem ilk kez çalıştırıldığında yetkili personel hesabı otomatik olarak oluşturulur:

    Kullanıcı Adı: admin

    Şifre: admin123

🌱 Otomatik Yüklenen Örnek Veriler (Seed)

Eğer yerel veri klasörünüz boşsa, sistem ilk açılışta CRM süreçlerinin simüle edilebilmesi için arka planda otomatik olarak mock veriler üretir ve şu istatistikleri konsola raporlar:

    Örnek Müşteri Kayıtları

    Geçmiş Satış Bilgileri

    Güncel Destek ve İş Talepleri
