# AI Collaboration Spec (ACS)

> AI modellerinin default davranışlarını override etmek için spec-driven metodoloji.

## Problem

AI modelleri (Claude, GPT, Gemini) default davranışlarla gelir:
- Pattern matching → keyword görünce düşünmeden aksiyon
- Sycophancy → kullanıcıyı memnun etmek için yanlışı onaylama
- Context pollution → geçmiş konuşmalardan alakasız bilgi taşıma
- Early closure → tam anlamadan hızlı cevap verme
- Conflict avoidance → itiraz etmekten kaçınma

Bu davranışlar çoğu kullanıcı için "yeterli" ama ciddi iş yapanlar için **sorun**.

## Çözüm

Spec-driven AI collaboration:

```
1. Kör noktaları tanımla (AI nerede hata yapıyor?)
2. Yasakları belirle (ASLA yapma)
3. Prensipleri yaz (HER ZAMAN yap)
4. Test senaryoları oluştur
5. İteratif geliştir (v1.0 → v1.x)
```

## Spec Yapısı

```yaml
name: collaboration-spec
version: 1.0
target_models: [claude, gpt, gemini]

# Kim için?
persona:
  role: "Girişimci"
  context: "Startup kurma, ürün geliştirme, strateji"

# AI nerede hata yapar?
blind_spots:
  - pattern_matching
  - sycophancy
  - context_pollution

# ASLA yapma
prohibitions:
  words: ["skill", "framework", "memory"]
  behaviors: ["süreç anlatma", "dolaylı bilgi taşıma"]
  references: ["bahsedilmeyen projeler"]

# HER ZAMAN yap
principles:
  - "Anlamadan hareket etme"
  - "Her konu taze başlar"
  - "Bağımsız düşün"
  - "Araştır, varsayma"
  - "Tam kapasite kullan"

# Ne zaman araştır?
source_rules:
  - "İtiraz ediyorsan → kaynak göster"
  - "Rakam veriyorsan → kaynak göster"
  - "Değişim iddia ediyorsan → web search"

# Nasıl test edilir?
test_scenarios:
  - "Yanlış teknik bilgi içeren plan"
  - "Gerçekçi olmayan hedefler"
  - "Belirsiz brief"
```

## Hızlı Başlangıç

1. [Template](templates/SPEC-TEMPLATE.md)'i kopyala
2. Kendi kör noktalarını tanımla
3. Yasakları ve prensipleri yaz
4. Test senaryoları oluştur
5. AI ile test et, iteratif geliştir

## Örnekler

| Örnek | Açıklama | Model |
|-------|----------|-------|
| [eren-framework](examples/eren-framework/) | Girişimci ↔ AI işbirliği | Claude |

## Neden Spec-Driven?

| Geleneksel | Spec-Driven |
|------------|-------------|
| "AI yanlış yaptı" → tekrar dene | Kör noktayı tanımla → spec'e ekle |
| Her seferinde aynı hataları düzelt | Bir kere düzelt, spec'te kalıcı |
| AI'a güvenme, kontrol et | AI'ı spec ile yönlendir |
| Tutarsız sonuçlar | Tekrarlanabilir davranış |

## Katkı

Bu repo açık kaynak ama aktif olarak ben ([@erenmustafaozdal](https://github.com/erenmustafaozdal)) geliştiriyorum.

## Lisans

MIT
