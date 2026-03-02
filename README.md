# MedVice - AI-Powered Health Consultation System

MedVice, tahlil sonuçlarını analiz eden ve sağlık danışmanlığı sağlayan gelişmiş bir AI sistemi.

## Özellikler

### 🧪 Tahlil Analizi
- **PDF Yükleme**: Tahlil raporlarını PDF, JPG, PNG formatında yükleme
- **Manuel Giriş**: Tahlil değerlerini manuel olarak girme
- **AI Analizi**: GPT-4 ile kapsamlı tahlil analizi
- **3 Aşamalı Değerlendirme**: İlk analiz → Ek sorular → Final değerlendirme

### 🔒 Güvenlik ve Gizlilik
- **Veri Güvenliği**: Tüm veriler şifrelenerek işlenir
- **Gizlilik Onayı**: GDPR uyumlu gizlilik politikası
- **Rate Limiting**: API çağrıları için hız sınırlaması
- **İçerik Filtreleme**: Güvenlik açısından zararlı içerik kontrolü
- **Veri Saklama**: 30 gün sonra otomatik veri silme

### 🏥 Tıbbi Güvenlik
- **Acil Durum Tespiti**: Kritik değerler için otomatik uyarı
- **Tanı Koymama**: Sadece bilgilendirme amaçlı analiz
- **Doktor Yönlendirme**: Uzman hekim başvurusu önerisi
- **Etik Kurallar**: Tıbbi etik standartlara uygunluk

## Kurulum

### Gereksinimler
- Node.js 18+
- npm veya yarn
- OpenAI API anahtarı

### Adımlar

1. **Projeyi klonlayın**
```bash
git clone https://github.com/enestsc/medvice-deploy.git
cd medvice
```

2. **Bağımlılıkları yükleyin**
```bash
npm install
```

3. **Environment variables ayarlayın**
```bash
# .env dosyası oluşturun
cp .env.example .env

# OpenAI API anahtarınızı ekleyin
echo "VITE_OPENAI_API_KEY=your_api_key_here" >> .env
```

4. **Geliştirme sunucusunu başlatın**
```bash
npm run dev
```

5. **Tarayıcıda açın**
```
http://localhost:8080
```

## Environment Variables

```env
# OpenAI API Configuration
VITE_OPENAI_API_KEY=your_openai_api_key_here

# Application Security Settings
VITE_MAX_FILE_SIZE=10485760  # 10MB in bytes
VITE_ALLOWED_FILE_TYPES=application/pdf,image/jpeg,image/jpg,image/png

# GPT Model Configuration
VITE_GPT_MODEL=gpt-4
VITE_GPT_MAX_TOKENS=2000
VITE_GPT_TEMPERATURE=0.3

# Security Headers
VITE_ENABLE_RATE_LIMITING=true
VITE_RATE_LIMIT_REQUESTS=10
VITE_RATE_LIMIT_WINDOW=60000  # 1 minute in milliseconds

# Privacy Settings
VITE_DATA_RETENTION_DAYS=30
VITE_ENABLE_ANALYTICS=false
VITE_LOG_USER_INTERACTIONS=false
```

## Kullanım

### 1. Hasta Bilgileri
- Yaş ve cinsiyet bilgilerini girin
- Gizlilik onayını verin

### 2. Tahlil Verileri
**Manuel Giriş:**
- Test adını girin (örn: Hemoglobin)
- Değeri ve birimini belirtin
- Normal aralığı tanımlayın

**Dosya Yükleme:**
- PDF, JPG, PNG formatında tahlil raporu yükleyin
- Sistem otomatik olarak metni çıkaracak

### 3. AI Analizi
- "AI Analizi Başlat" butonuna tıklayın
- Sistem 3 aşamada analiz yapacak:
  1. **Tahlil Analizi**: Değerlerin normal aralıklarla karşılaştırılması
  2. **Ek Sorular**: Daha detaylı bilgi için sorular
  3. **Final Değerlendirme**: Kapsamlı sağlık değerlendirmesi

## Teknik Detaylar

### Mimari
- **Frontend**: React 18 + TypeScript + Vite
- **UI Framework**: ShadCN/UI + Tailwind CSS
- **AI Integration**: OpenAI GPT-4 API
- **State Management**: React Hooks
- **Routing**: React Router v6

### Güvenlik Katmanları
1. **Input Validation**: Dosya türü ve boyut kontrolü
2. **Content Sanitization**: Zararlı içerik temizleme
3. **Rate Limiting**: API çağrı sınırlaması
4. **Data Encryption**: Hassas veri şifreleme
5. **Privacy Compliance**: GDPR uyumluluğu

### API Endpoints
- `POST /api/analyze` - Tahlil analizi başlatma
- `POST /api/follow-up` - Ek sorular sorma
- `POST /api/final-assessment` - Final değerlendirme

## Güvenlik Uyarıları

⚠️ **ÖNEMLİ**: Bu sistem tanı koymaz ve doktor muayenesinin yerini tutmaz.

- Acil durumlarda 112'yi arayın
- Kritik değerler için derhal doktora başvurun
- Tüm analizler bilgilendirme amaçlıdır
- Kesin tanı ve tedavi için uzman hekim gereklidir

## Katkıda Bulunma

1. Fork yapın
2. Feature branch oluşturun (`git checkout -b feature/amazing-feature`)
3. Commit yapın (`git commit -m 'Add amazing feature'`)
4. Push yapın (`git push origin feature/amazing-feature`)
5. Pull Request oluşturun

---

**MedVice** - Sağlığınız için AI destekli çözümler
