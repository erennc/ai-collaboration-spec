# ACS Metodolojisi

> AI Collaboration Spec nasıl oluşturulur ve geliştirilir?

## Felsefe

**Temel fikir:** AI modelleri "genel kullanıcı" için optimize edilmiş. Eğer "genel kullanıcı" değilsen, AI'ın default davranışları seni yavaşlatır veya yanlış yönlendirir.

**Çözüm:** Default davranışları override eden bir spec yaz.

---

## 5 Adımlı Süreç

### Adım 1: Kör Nokta Keşfi

AI ile çalışırken hangi hataları tekrarlıyor?

**Yöntem:**
1. 1 hafta boyunca AI ile normal çalış
2. Her hatayı not al
3. Hataları kategorize et
4. En sık tekrarlananları seç

**Örnek kategoriler:**
- Düşünme hataları (pattern matching, varsayım yığma)
- İletişim hataları (süreç anlatma, aşırı uzun yanıt)
- Bağlam hataları (yanlış bilgi taşıma, memory pollution)
- Karar hataları (pozisyon almama, conflict avoidance)

### Adım 2: Yasak Tanımlama

Kör noktaları "ASLA yapma" formatına çevir.

**İyi yasak örneği:**
```
❌ "Skill dosyamı kontrol edeyim"
❌ "Değerlendirmem gerekiyor"
❌ Bahsedilmeyen projelere referans verme
```

**Kötü yasak örneği:**
```
❌ "Kötü cevap verme" → çok belirsiz
❌ "Yanlış yapma" → ölçülemez
```

**Kural:** Yasak spesifik ve test edilebilir olmalı.

### Adım 3: Prensip Belirleme

"HER ZAMAN yap" formatında pozitif kurallar.

**İyi prensip örneği:**
```
✅ İtiraz ediyorsan kaynak göster
✅ Her konu taze başlar - önceki bilgiyi taşıma
✅ Net pozisyon al, seçenek listesi verme
```

**Kötü prensip örneği:**
```
✅ "İyi ol" → belirsiz
✅ "Yardımcı ol" → zaten default
```

**Kural:** Prensip, default davranışın TERSİ olmalı.

### Adım 4: Test Senaryoları

Spec'in çalışıp çalışmadığını nasıl test edeceksin?

**İyi test senaryosu:**
- Birden fazla kör noktayı tetikler
- Yanlış bilgi içerir (AI düzeltecek mi?)
- Gerçekçi olmayan beklenti içerir (AI itiraz edecek mi?)
- Belirsizlik içerir (AI soru soracak mı?)

**Test değerlendirme:**
```
| Test | Sonuç | Detay |
|------|-------|-------|
| Kör nokta #1 | ✅/❌ | [ne oldu?] |
| Kör nokta #2 | ✅/❌ | [ne oldu?] |
| Yasak #1 | ✅/❌ | [ne oldu?] |
```

### Adım 5: İteratif Geliştirme

Test sonuçlarına göre spec'i güncelle.

**Versiyon artırma kuralları:**
- Küçük düzeltme → v1.1, v1.2
- Yeni kör nokta ekleme → v1.x
- Yapısal değişiklik → v2.0

**Örnek iterasyon:**
```
v1.0 → "Skill'e bakıyorum" hala diyor
v1.1 → Yasağa ekle: "skill", "framework"
v1.1 → Hala diyor, farklı kelimelerle
v1.2 → Yasağa ekle: "kontrol edeyim", "değerlendirmem gerekiyor"
v1.2 → Düzeldi ✅
```

---

## Anti-Pattern'ler

**1. Aşırı uzun spec**
- ❌ 200+ satır, 60+ kör nokta
- ✅ 50-70 satır, 5-10 kritik kural
- Neden: AI uzun spec'te kritik kuralları kaybeder

**2. Belirsiz yasaklar**
- ❌ "Kötü davranma"
- ✅ "ASLA 'değerlendirmem gerekiyor' deme"
- Neden: Test edilemez

**3. Tek seferlik spec**
- ❌ Yaz, kullan, güncelleme
- ✅ Sürekli test et, her hatada güncelle
- Neden: AI davranışı değişiyor, spec de değişmeli

**4. Her şeyi yasaklama**
- ❌ 50 yasaklı kelime
- ✅ 5-10 kritik yasak
- Neden: Çok yasak = AI doğal konuşamaz

---

## Model-Spesifik Notlar

### Claude
- Skill dosyası (.skill) formatını destekler
- Memory edit ile yasaklar eklenebilir
- Description alanı kritik - ilk okunan yer

### GPT
- Custom Instructions kullan
- System prompt'a spec'i ekle
- Memory özelliği sınırlı

### Gemini
- System instruction kullan
- Context window büyük ama dikkat dağınık
- Daha agresif yasak listesi gerekebilir

---

## Başarı Metrikleri

Spec ne zaman "çalışıyor" sayılır?

| Metrik | Hedef |
|--------|-------|
| Yasak ihlali oranı | <%10 |
| İtiraz oranı (yanlış bilgiye) | >%80 |
| Kaynak gösterme oranı | >%70 |
| "İlk seferde doğru" oranı | >%80 |

---

## Sonraki Adımlar

1. [Template](../templates/SPEC-TEMPLATE.md)'i kopyala
2. Kendi kör noktalarını yaz
3. Test et, skorla
4. İteratif geliştir
5. Versiyon geçmişini tut
