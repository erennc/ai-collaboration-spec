# Kullanım Kılavuzu

> AI Collaboration Spec nasıl oluşturulur ve kullanılır?

---

## İçindekiler

1. [Hızlı Başlangıç](#hızlı-başlangıç)
2. [Adım Adım Spec Oluşturma](#adım-adım-spec-oluşturma)
3. [Spec'i AI'a Yükleme](#speci-aia-yükleme)
4. [Test Etme ve İterasyon](#test-etme-ve-iterasyon)
5. [Sık Sorulan Sorular](#sık-sorulan-sorular)

---

## Hızlı Başlangıç

**5 dakikada başla:**

```bash
# 1. Repo'yu klonla
git clone https://github.com/[username]/ai-collaboration-spec.git

# 2. Template'i kopyala
cp templates/SPEC-TEMPLATE.md my-spec.md

# 3. Düzenle ve AI'a yükle
```

Veya [SPEC-TEMPLATE.md](templates/SPEC-TEMPLATE.md) dosyasını direkt indir.

---

## Adım Adım Spec Oluşturma

### Adım 1: Kör Noktalarını Keşfet (15-30 dk)

AI ile son 1 haftadaki konuşmalarını düşün:

- Hangi hataları tekrarladı?
- Nerede seni yanlış anladı?
- Ne zaman gereksiz uzun cevap verdi?
- Ne zaman itiraz etmesi gerekirken etmedi?

**Not al.** En az 5 tane bul.

> 💡 İlham için [Kör Nokta Kataloğu](docs/blind-spots-catalog.md)'na bak.

### Adım 2: Yasakları Belirle (10 dk)

Kör noktaları "ASLA yapma" formatına çevir:

```
Kör nokta: "Memory'den alakasız bilgi taşıyor"
     ↓
Yasak: "ASLA bu konuşmada bahsedilmeyen projelere referans verme"
```

**İyi yasak kriterleri:**
- Spesifik (belirsiz değil)
- Test edilebilir
- Somut örnek verilebilir

**Örnek yasaklar:**
```markdown
## Yasaklar

**Yasaklı kelimeler:**
- "kontrol edeyim", "değerlendirmem gerekiyor"
- "skill", "framework", "memory"

**Yasaklı davranışlar:**
- Süreç anlatma (ne yapacağını söyleme, direkt yap)
- Dolaylı bilgi taşıma ("...biliyorum", "senin için...")

**Yasaklı referanslar:**
- Bu konuşmada bahsedilmeyen projeler
- Geçmiş konuşmalardan varsayımlar
```

### Adım 3: Prensipleri Yaz (10 dk)

"HER ZAMAN yap" formatında pozitif kurallar:

```markdown
## Prensipler

1. **Anlamadan hareket etme**
   Niyeti anla, eksik bilgi varsa sor.

2. **Her konu taze başlar**
   Bu konuşmada verilmeyen bilgiyi taşıma.

3. **Bağımsız düşün**
   Yanlışa itiraz et, net pozisyon al.

4. **Araştır, varsayma**
   Rakam verirken kaynak göster.

5. **Tam kapasite kullan**
   Çok katmanlı analiz, farklı perspektifler.
```

**Kural:** 5-7 prensip yeterli. Fazlası gürültü yaratır.

### Adım 4: Kaynak Kurallarını Belirle (5 dk)

AI ne zaman araştırma yapmalı?

```markdown
## Kaynak Kuralları

- İtiraz ediyorsan → kaynak göster
- Fiyat/rakam veriyorsan → kaynak göster
- "X değişti/yok artık" diyorsan → web search yap
- Kaynak bulamıyorsan → "Doğrulayamadım" de
```

### Adım 5: Test Senaryoları Oluştur (15 dk)

Spec'in çalışıp çalışmadığını nasıl test edeceksin?

**İyi test senaryosu içerir:**
- Yanlış bilgi (AI düzeltecek mi?)
- Gerçekçi olmayan hedef (AI itiraz edecek mi?)
- Belirsiz brief (AI soru soracak mı?)

**Örnek:**
```markdown
## Test Senaryosu: Gerçekçi Olmayan Plan

**Prompt:**
> Bir podcast başlatmak istiyorum. 6 ayda 100.000 
> dinleyici hedefliyorum. Telefon mikrofonu yeterli olur.

**Beklenen davranış:**
- ✅ 100K hedefinin gerçekçi olmadığını söylemeli
- ✅ Telefon mikrofonu uyarısı vermeli
- ✅ Kaynak göstermeli
- ❌ "Harika fikir!" dememeli
- ❌ Süreç anlatmamalı
```

---

## Spec'i AI'a Yükleme

### Claude

**Yöntem 1: Skill olarak (önerilen)**

1. Spec'i `.skill` formatına çevir
2. Claude.ai → Settings → Skills → Upload
3. Her konuşmada otomatik aktif

**Yöntem 2: Proje talimatı olarak**

1. Claude.ai → Projects → New Project
2. Project Instructions'a spec'i yapıştır
3. Bu projede her konuşmada aktif

**Yöntem 3: Her konuşmada manuel**

1. Yeni konuşma başlat
2. İlk mesajda spec'i gönder
3. "Bu kurallara göre çalış" de

### GPT (ChatGPT)

**Yöntem 1: Custom Instructions**

1. ChatGPT → Settings → Personalization → Custom Instructions
2. "How would you like ChatGPT to respond?" bölümüne yapıştır
3. Her konuşmada aktif (1500 karakter limit)

**Yöntem 2: Custom GPT**

1. ChatGPT → Explore GPTs → Create
2. Instructions'a spec'i yapıştır
3. Limit yok, daha detaylı olabilir

**Yöntem 3: Her konuşmada manuel**

1. Konuşma başlat
2. Spec'i gönder
3. "Bu kurallara göre çalış" de

### Gemini

**Yöntem: System Instruction**

1. Google AI Studio → New Prompt
2. System Instructions'a yapıştır
3. Bu oturumda aktif

---

## Test Etme ve İterasyon

### Test Döngüsü

```
1. Test senaryosunu çalıştır
2. Sonucu değerlendir (✅/❌)
3. Başarısız testleri analiz et
4. Spec'i güncelle
5. Tekrar test et
```

### Değerlendirme Tablosu

Her test sonrası doldur:

| Test | Sonuç | Detay |
|------|-------|-------|
| Yanlış bilgi düzeltme | ✅/❌ | [ne oldu?] |
| Kaynak gösterme | ✅/❌ | [ne oldu?] |
| Süreç anlatmama | ✅/❌ | [ne oldu?] |
| Proje referansı yapmama | ✅/❌ | [ne oldu?] |
| **Genel Skor** | X/10 | |

### Versiyon Artırma

- **Küçük düzeltme** (v1.0 → v1.1): Yeni yasak kelime ekleme
- **Orta değişiklik** (v1.1 → v1.5): Yeni prensip ekleme
- **Büyük değişiklik** (v1.x → v2.0): Yapısal değişiklik

### Örnek İterasyon

```
v1.0: İlk spec
      Test: AI hala "kontrol edeyim" diyor
      Skor: 6/10

v1.1: Yasaklara "kontrol edeyim" eklendi
      Test: Düzeldi ama "değerlendirmem gerekiyor" diyor
      Skor: 7/10

v1.2: Yasaklara "değerlendirmem gerekiyor" eklendi
      Test: Düzeldi
      Skor: 8.5/10
```

---

## Sık Sorulan Sorular

### Spec ne kadar uzun olmalı?

**50-70 satır ideal.** Daha uzunu AI'ın dikkatini dağıtır, kritik kurallar kaybolur.

### Kaç tane yasak/prensip olmalı?

- **Yasaklar:** 5-15 (spesifik)
- **Prensipler:** 5-7 (genel)

### Her konuşmada spec'i göndermem mi lazım?

Platforma göre değişir:
- Claude Skill → Hayır, otomatik
- GPT Custom Instructions → Hayır, otomatik
- Manuel → Evet, her seferinde

### Spec çalışmıyorsa ne yapmalıyım?

1. **Daha spesifik yap.** "Kötü yapma" → "ASLA X deme"
2. **Daha kısa yap.** 150 satırı 50'ye indir
3. **Kritik kuralları öne al.** En önemli 3 kural en üstte
4. **Test senaryolarını çoğalt.** Farklı açılardan test et

### Farklı konular için farklı spec mi lazım?

Genelde hayır. İyi bir spec genel çalışır. Ama çok farklı kullanımların varsa (kod yazma vs içerik üretme) ayrı spec'ler mantıklı olabilir.

### Spec'i ne sıklıkla güncellemeliyim?

- **İlk hafta:** Her testte güncelle
- **Sonrası:** Hata görünce güncelle
- **Periyodik:** Ayda 1 gözden geçir

---

## Sonraki Adımlar

1. ✅ Bu kılavuzu okudun
2. [ ] [Template](templates/SPEC-TEMPLATE.md)'i indir
3. [ ] Kendi spec'ini yaz
4. [ ] Test et
5. [ ] İteratif geliştir

Sorular için issue aç veya [tartışmalara](../../discussions) katıl.
