# [Spec Adı] - AI Collaboration Spec

> [Kısa açıklama: Bu spec ne için?]

## Metadata

```yaml
name: [spec-adi]
version: 1.0
date: [tarih]
target_models: [claude, gpt, gemini]  # hangilerini hedefliyorsun?
author: [isim]
```

---

## 1. Persona

**Kim için?**
- Rol: [örn: Girişimci, Avukat, Doktor, Yazar]
- Context: [örn: Startup kurma, dava hazırlığı, tanı desteği, roman yazımı]
- Hedef: [AI ile ne başarmak istiyorsun?]

---

## 2. Kör Noktalar (Blind Spots)

**Bu persona için AI nerede hata yapıyor?**

| # | Kör Nokta | Açıklama | Örnek |
|---|-----------|----------|-------|
| 1 | [isim] | [ne oluyor?] | [somut örnek] |
| 2 | [isim] | [ne oluyor?] | [somut örnek] |
| 3 | [isim] | [ne oluyor?] | [somut örnek] |

> 💡 Başlangıç için [genel kör nokta kataloğu](../docs/blind-spots-catalog.md)'na bak.

---

## 3. Yasaklar (Prohibitions)

**ASLA yapma:**

### Yasaklı Kelimeler/İfadeler
```
- [kelime 1]
- [kelime 2]
- [ifade 1]
```

### Yasaklı Davranışlar
```
- [davranış 1: örn "süreç anlatma"]
- [davranış 2: örn "dolaylı bilgi taşıma"]
```

### Yasaklı Referanslar
```
- [referans 1: örn "bahsedilmeyen projeler"]
- [referans 2: örn "geçmiş konuşmalar"]
```

---

## 4. Prensipler (Principles)

**HER ZAMAN yap:**

| # | Prensip | Açıklama |
|---|---------|----------|
| 1 | [isim] | [ne yapılacak?] |
| 2 | [isim] | [ne yapılacak?] |
| 3 | [isim] | [ne yapılacak?] |
| 4 | [isim] | [ne yapılacak?] |
| 5 | [isim] | [ne yapılacak?] |

---

## 5. Kaynak Kuralları (Source Rules)

**Ne zaman araştır/kaynak göster?**

- [ ] İtiraz ediyorsan → kaynak göster
- [ ] Rakam/fiyat/oran veriyorsan → kaynak göster
- [ ] "X değişti/artık yok" diyorsan → web search yap
- [ ] [Kendi kuralın]

**Kaynak bulamıyorsan:**
> [ne yapılacak? örn: "Doğrulamam gerekiyor ama bulamadım" de]

---

## 6. Test Senaryoları

**Spec'i nasıl test edeceksin?**

### Senaryo 1: [isim]
```
Prompt: [test prompt'u]

Test edilen:
- [ ] Kör nokta #X
- [ ] Yasak #Y
- [ ] Prensip #Z

Beklenen davranış:
- [ne yapmalı?]
- [ne yapMAmalı?]
```

### Senaryo 2: [isim]
```
Prompt: [test prompt'u]

Test edilen:
- [ ] ...

Beklenen davranış:
- ...
```

---

## 7. Versiyon Geçmişi

| Versiyon | Tarih | Değişiklik |
|----------|-------|------------|
| v1.0 | [tarih] | İlk sürüm |

---

## 8. Notlar

[Ek notlar, öğrenilen dersler, gelecek güncellemeler için fikirler]
