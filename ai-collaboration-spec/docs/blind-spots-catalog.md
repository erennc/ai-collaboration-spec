# AI Kör Nokta Kataloğu

> Tüm AI modelleri (Claude, GPT, Gemini) için ortak kör noktalar.

Bu katalog, kendi spec'ini oluştururken başlangıç noktası olarak kullan. Tüm kör noktalar senin için geçerli olmayabilir - sadece deneyimlediğini seç.

---

## Kategori 1: Düşünme Hataları

| # | Kör Nokta | Açıklama | Semptom |
|---|-----------|----------|---------|
| 1 | Pattern matching | Keyword görünce düşünmeden aksiyon | "Python" deyince hemen kod yazıyor |
| 2 | Assumption stacking | Varsayım üstüne varsayım | Temeli sorgulamadan ilerliyor |
| 3 | Incomplete reasoning | Düşünce zincirini yarıda bırakma | "Yeterli" deyip kesiyor |
| 4 | Single perspective | Tek açıdan bakma | Alternatif düşünmüyor |
| 5 | Early closure | Tam anlamadan hızlı cevap | İlk anlayışla sonuca atlıyor |
| 6 | Template thinking | Her şeyi bilinen kalıba sokma | Özgün durumu görmüyor |

---

## Kategori 2: Bağlam Hataları

| # | Kör Nokta | Açıklama | Semptom |
|---|-----------|----------|---------|
| 7 | Context pollution | Alakasız geçmiş bilgiyi taşıma | Başka projeden referans veriyor |
| 8 | Recency bias | En son söyleneni önemseme | Önceki kritik bilgiyi unutuyor |
| 9 | Memory leak | Memory'den istenmeyen bilgi sızması | "Biliyorum ki sen..." diyor |
| 10 | Scope creep acceptance | Konu dağılmasına izin verme | Her yeni konuya atlıyor |

---

## Kategori 3: İletişim Hataları

| # | Kör Nokta | Açıklama | Semptom |
|---|-----------|----------|---------|
| 11 | Process narration | Ne yapacağını anlatma | "Önce şunu kontrol edeyim..." |
| 12 | Verbosity | Gereksiz uzun yanıtlar | 3 cümlelik cevap 3 paragraf oluyor |
| 13 | Meta-commentary | Sistem hakkında konuşma | "Memory'de şunu gördüm..." |
| 14 | Repetitive warnings | Aynı uyarıyı tekrarlama | Her yanıtta aynı disclaimer |
| 15 | Format lock | Yanlış formatta takılma | Her şeyi liste yapıyor |

---

## Kategori 4: Karar Hataları

| # | Kör Nokta | Açıklama | Semptom |
|---|-----------|----------|---------|
| 16 | Sycophancy | Kullanıcıyı memnun etmek için onaylama | Yanlışı "güzel fikir" diyor |
| 17 | Conflict avoidance | İtiraz etmekten kaçınma | "Ama şunu da düşün..." yerine susma |
| 18 | Decision delegation | Karar vermeme | "İkisi de olabilir" |
| 19 | False confidence | Emin olmadan kesin konuşma | Kaynak göstermeden iddia |
| 20 | Hedging overload | Aşırı belirsiz konuşma | "Belki, muhtemelen, olabilir..." |

---

## Kategori 5: Araştırma Hataları

| # | Kör Nokta | Açıklama | Semptom |
|---|-----------|----------|---------|
| 21 | Tool under-use | Araştırması gerektiğinde yapmama | Eski bilgiyle cevap veriyor |
| 22 | Tool over-reliance | Gereksiz yere araştırma | Basit soruda bile search |
| 23 | Unsourced statistics | Kaynak göstermeden rakam | "%80'i şöyle yapıyor" |
| 24 | Outdated info | Güncel olmayan bilgi | "Heroku ücretsiz" (değil) |

---

## Kategori 6: Kullanıcı İlişkisi Hataları

| # | Kör Nokta | Açıklama | Semptom |
|---|-----------|----------|---------|
| 25 | User anchoring | Kullanıcının rakamlarına takılma | "5 fikir ver" → tam 5 veriyor |
| 26 | Assumed expertise | Uzmanlık varsayma | Jargon açıklamadan kullanıyor |
| 27 | Politeness override | Kibar olmak için yanlışı geçme | Kritik hatayı soft söylüyor |
| 28 | Question avoidance | Belirsizlikte soru sormama | Varsayımla ilerliyor |

---

## Kategori 7: Çıktı Hataları

| # | Kör Nokta | Açıklama | Semptom |
|---|-----------|----------|---------|
| 29 | Option paralysis | Seçenek sunup önermeme | "3 yol var: A, B, C" (hangisi?) |
| 30 | Over-engineering | Basit soruna karmaşık çözüm | 3 satır kod yerine framework |
| 31 | Under-engineering | Karmaşık soruna basit çözüm | Kritik edge case'leri atlama |
| 32 | Premature structuring | Düşünmeden formatlama | Hemen tablo/liste yapıyor |

---

## Nasıl Kullanılır?

1. **Keşif:** 1 hafta AI ile çalış, hataları not al
2. **Eşleştirme:** Hatalarını bu katalogla eşleştir
3. **Seçim:** En sık yaşadığın 5-10 tanesini seç
4. **Spec'e ekle:** Yasaklar ve prensipler olarak yaz
5. **Test et:** Senaryo oluştur, spec'i test et

---

## Model-Spesifik Eğilimler

| Kör Nokta | Claude | GPT | Gemini |
|-----------|--------|-----|--------|
| Sycophancy | Orta | Yüksek | Yüksek |
| Verbosity | Düşük | Yüksek | Orta |
| Process narration | Yüksek | Orta | Düşük |
| Memory leak | Yüksek | Düşük | Düşük |
| Unsourced statistics | Orta | Yüksek | Yüksek |

*Bu tablo deneyime dayalı gözlemdir, kesin değildir.*

---

## Katkı

Yeni kör nokta keşfettiysen, issue aç veya PR gönder.
