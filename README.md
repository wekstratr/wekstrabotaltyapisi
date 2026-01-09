# 🛡️ Gelişmiş Moderasyon & Rapor Botu

Bu proje, Python ve `discord.py` kütüphanesi kullanılarak geliştirilmiş, **modüler (Cogs)** yapıya sahip, **SQLite** veritabanı destekli bir Discord moderasyon botu altyapısıdır.

## ✨ Özellikler

* **Modüler Yapı:** Komutlar kategorize edilmiştir (Cogs), bu sayede kod yönetimi kolaydır.
* **Slash Komutları:** Modern Discord API'sine uygun `/` komut sistemi.
* **Veritabanı Kaydı:** Tüm raporlar ve moderasyon işlemleri `database.db` dosyasına kalıcı olarak kaydedilir.
* **Küfür Engel Sistemi:** Belirlenen kelimeler anında silinir ve kullanıcı uyarılır.
* **DM Bilgilendirme:** Yasaklanan veya susturulan kullanıcılara bot tarafından otomatik bilgi mesajı gönderilir.

## 🛠️ Kurulum

1. **Gereksinimleri Yükleyin:**
```bash
pip install discord.py

```


2. **Bot Tokenini Ayarlayın:**
`main.py` dosyasındaki `TOKEN_BURAYA` kısmına [Discord Developer Portal](https://www.google.com/search?q=https://discord.com/developers/applications)'dan aldığınız bot tokenini yapıştırın.
3. **İzinleri Kontrol Edin:**
Discord Developer Portal üzerinden **Privileged Gateway Intents** (Server Members ve Message Content) izinlerini aktif ettiğinizden emin olun.
4. **Botu Çalıştırın:**
```bash
python main.py

```



## 📜 Komutlar

### 🛡️ Moderatör Komutları

| Komut | Açıklama |
| --- | --- |
| `/yasakla [@kullanıcı] [neden]` | Kullanıcıyı sunucudan yasaklar ve kaydeder. |
| `/yasakkaldir [ID] [neden]` | Yasak kaldırır ve kullanıcıya davet linkiyle DM atar. |
| `/sustur [@kullanıcı] [dk] [neden]` | Kullanıcıyı belirlenen süre boyunca susturur. |
| `/susturkaldir [@kullanıcı]` | Kullanıcının susturmasını erkenden kaldırır. |
| `/duyuru [mesaj]` | Sunucudaki tüm üyelere DM yoluyla duyuru gönderir. |
| `/kullanicibilgisi [@kullanıcı]` | Kullanıcın giriş tarihi ve rollerini gösterir. |

### 👥 Kullanıcı Komutları

| Komut | Açıklama |
| --- | --- |
| `/raporla [@kullanıcı] [neden]` | Bir kullanıcıyı moderatörlere şikayet eder. |
| `/raporlar [@kullanıcı]` | Belirtilen kullanıcının rapor geçmişini veritabanından çeker. |

## 📁 Klasör Yapısı

```text
├── main.py              # Ana çalıştırıcı
├── database.db          # SQLite Veritabanı (Otomatik oluşur)
├── utils/
│   └── db_handler.py    # Veritabanı fonksiyonları
└── cogs/
    ├── moderation.py    # Mod komutları
    ├── reporting.py     # Rapor sistemi
    └── filters.py       # Küfür filtresi

```

---

**Not:** Bu proje eğitim ve sunucu yönetimi amaçlı geliştirilmiştir. Geliştirmeye açıktır!
