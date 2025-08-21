# MAGNA — IT Depo & Servis Takip

Bu proje, şirket içindeki cihazların takibini kolaylaştırmak amacıyla geliştirilmiş bir **web tabanlı envanter ve servis yönetim sistemi**dir.  
Ana modüller: **Depo Envanteri**, **Arızalı Cihazlar**, **Servis Geçmişi**, **Parametreler**, **Raporlar** ve **Kullanım Kılavuzu**.

## 🚀 Hızlı Başlangıç

```bash
# 1) Sanal ortam (opsiyonel ama önerilir)
python -m venv venv
# Windows
venv\Scripts\activate
# macOS/Linux
source venv/bin/activate

# 2) Kurulum
pip install -r requirements.txt

# 3) Geliştirme sunucusu
python app.py  # http://127.0.0.1:5000
```

> İlk çalıştırmada `app.db` SQLite veritabanı otomatik oluşur.

## 🔑 Özellikler

### 📦 Depo Envanteri (`/depo`)
- Cihaz ekleme, düzenleme, silme  
- Arızalı / Normal işaretleme  
- Miktar takibi  
- Arama kutusu ile marka, tip, seri kodu vb. alanlarda filtreleme  

### ⚠️ Arızalı Cihazlar (`/arizali`)
- Tüm arızalı cihazların listesi  
- **“Normal Yap”** butonu ile cihazı tekrar kullanılabilir hale getirme  

### 🛠 Servis Geçmişi (`/servis`)
- Cihazlar için servis kaydı ekleme, düzenleme, silme  
- **Aynı cihaz için birden fazla açık servis kaydı eklenemez**  
- **Durum “Tamir Edildi” veya “Teslim Edildi” seçilirse cihaz otomatik olarak arızalı listesinden çıkar**  

### ⚙️ Parametreler (`/parametreler`)
- Tip, Marka, Model, İşletim Sistemi gibi seçenekler buradan yönetilir  
- Yeni cihaz ekleme ve arıza ekleme ekranlarında bu parametreler **otomatik listelenir** (elle yazmaya gerek yok)  

### 📊 Raporlar (`/reports`)
- Envanter, arızalı cihazlar ve servis geçmişine dair **grafiksel raporlar**  
- Kategori bazlı sayılar ve trend grafikleri  

### 📘 Kullanım Kılavuzu (`/kullanim`)
- Sistemin kullanımına dair özet bilgiler  
- Kullanıcıların hızlıca öğrenebilmesi için sade bir dokümantasyon sayfası  

## 🎨 Tasarım
- Üst kısımda **navbar** bulunur, logoya tıklandığında envanter sayfasına yönlendirir  
- Aktif sayfa navbar’da **kırmızı alt çizgi** ile belirtilir  
- Sayfalar arası geçiş menü üzerinden yapılır  
- Modallar (ekleme/düzenleme pencereleri) **Bootstrap** ile yapılmıştır  
- Rapor sayfasında **chart.js** ile dinamik grafikler kullanılmıştır  
- CSS sade tutulmuş, isteğe göre özelleştirilebilir

## 🖼️ Ekran Görselleri
> Aşağıdaki ekran görüntülerini `screenshots/` klasörüne koyabilir ve buraya ekleyebilirsin:

- **Depo Envanteri**  
  ![Depo](screenshots/depo.png)

- **Arızalı Cihazlar**  
  ![Arızalı](screenshots/arizali.png)

- **Servis Geçmişi**  
  ![Servis](screenshots/servis.png)

- **Parametreler**  
  ![Parametreler](screenshots/parametreler.png)

- **Raporlar**  
  ![Raporlar](screenshots/raporlar.png)

- **Kullanım Kılavuzu**  
  ![Kullanım](screenshots/kullanim.png)

## 📝 Notlar
- Silme işlemlerinde **“Emin misin?”** onayı vardır  
- Kod **Flask + SQLite + SQLAlchemy** ile yazılmıştır  
- Gerektiğinde **MSSQL/PostgreSQL** gibi farklı veritabanlarına uyarlanabilir  
- Proje, **yerel kullanım** için tasarlanmıştır ancak kolayca sunucuya taşınabilir  
