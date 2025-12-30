# Eren Collaboration Framework

> Girişimci ↔ AI işbirliği için spec örneği.

## Özet

| Alan | Değer |
|------|-------|
| Persona | Startup kurucusu |
| Model | Claude (Opus 4.5) |
| Versiyon | v1.8 |
| Geliştirme süresi | 1 gün, 8 iterasyon |

## Problem

Claude'un default davranışları girişimci için sorun yaratıyordu:
- Memory'den alakasız proje referansları
- "Skill'e bakıyorum" gibi süreç anlatma
- Yanlış bilgiye itiraz etmeme
- Kaynak göstermeden rakam verme

## Çözüm

5 yasak + 5 prensip + kaynak zorunluluğu:

**Yasaklar:**
- "skill", "framework", "memory" kelimeleri
- Bahsedilmeyen projelere referans
- Süreç anlatma
- Dolaylı bilgi taşıma ("...biliyorum")

**Prensipler:**
1. Anlamadan hareket etme
2. Her konu taze başlar
3. Bağımsız düşün
4. Araştır, varsayma
5. Tam kapasite kullan

## Versiyon Geçmişi

| Versiyon | Skor | Ana Değişiklik |
|----------|------|----------------|
| v1.0 | 7/10 | İlk sürüm |
| v1.3 | 7/10 | Process narration yasakları |
| v1.4 | 6.5/10 | Kritik kurallar en üste |
| v1.6 | 8.5/10 | Radikal optimizasyon (50 satır) |
| v1.7 | 9/10 | Dolaylı memory taşıma yasakları |
| v1.8 | 9/10 | Kaynak zorunluluğu |

## Test Senaryoları

1. **SaaS + Yanlış Teknik Bilgi** - "Python en hızlı dil" iddiası
2. **Podcast + Gerçekçi Olmayan Hedef** - 6 ayda 100K dinleyici
3. **E-ticaret + Platform Hatası** - Stripe Türkiye'de çalışmıyor
4. **Newsletter + Pazar Yanılgısı** - Substack Türkiye popülerliği

## Öğrenilen Dersler

1. **Uzun spec = gürültü.** 150 satırdan 50 satıra indirmek başarıyı artırdı.
2. **Description kritik.** AI ilk oraya bakıyor.
3. **Yasaklar spesifik olmalı.** "Kötü yapma" değil, "ASLA 'kontrol edeyim' deme."
4. **Her test sonrası güncelle.** Tek seferlik spec çalışmıyor.

## Kullanım

Claude'da skill olarak yükle veya system prompt'a ekle.
