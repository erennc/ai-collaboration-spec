# ACS Roadmap

> AI Collaboration Spec geliştirme yol haritası

---

## Mevcut Durum: v0.1 (Alpha)

**Var olan:**
- [x] README + temel açıklama
- [x] SPEC-TEMPLATE.md (boş şablon)
- [x] Metodoloji dökümanı
- [x] Kör nokta kataloğu (32 genel)
- [x] 1 örnek (eren-framework)
- [x] MIT lisans

---

## Faz 1: Foundation (v0.2)

**Hedef:** Temel yapıyı sağlamlaştır, daha fazla örnek ekle.

| Task | Öncelik | Durum |
|------|---------|-------|
| 2-3 farklı persona örneği ekle | Yüksek | ⬜ |
| GPT için adaptasyon notu | Yüksek | ⬜ |
| Gemini için adaptasyon notu | Yüksek | ⬜ |
| Test senaryosu kütüphanesi | Orta | ⬜ |
| Kör nokta kataloğunu genişlet (50+) | Orta | ⬜ |
| Contributing guide | Düşük | ⬜ |

**Örnek persona fikirleri:**
- Freelance yazılımcı
- İçerik üreticisi / YouTuber
- Araştırmacı / Akademisyen
- Küçük işletme sahibi

**Tahmini süre:** 2-3 hafta

---

## Faz 2: Tooling (v0.3)

**Hedef:** Spec yazmayı ve test etmeyi kolaylaştır.

| Task | Öncelik | Durum |
|------|---------|-------|
| Spec validator (format kontrolü) | Yüksek | ⬜ |
| Spec generator (interaktif CLI) | Yüksek | ⬜ |
| Test runner (senaryo otomasyonu) | Orta | ⬜ |
| Scoring system (otomatik değerlendirme) | Orta | ⬜ |

**Spec validator örneği:**
```bash
acs validate my-spec.md

✅ Metadata: OK
✅ Prohibitions: 5 found
❌ Principles: Missing (required)
⚠️  Test scenarios: Only 1 (recommend 3+)
```

**Spec generator örneği:**
```bash
acs init

? Persona rolün nedir? > Girişimci
? Hangi model? > Claude
? En sık yaşadığın 3 AI hatası?
  > Memory'den yanlış bilgi taşıma
  > Kaynak göstermeme
  > Süreç anlatma

✅ my-spec.md oluşturuldu
```

**Tahmini süre:** 1-2 ay

---

## Faz 3: Ecosystem (v0.5)

**Hedef:** Farklı platformlara entegrasyon.

| Task | Öncelik | Durum |
|------|---------|-------|
| Claude skill formatter | Yüksek | ⬜ |
| GPT Custom Instructions formatter | Yüksek | ⬜ |
| Gemini system instruction formatter | Orta | ⬜ |
| VS Code extension | Düşük | ⬜ |
| Obsidian plugin | Düşük | ⬜ |

**Çıktı formatları:**
```bash
acs export my-spec.md --format claude-skill
acs export my-spec.md --format gpt-instructions
acs export my-spec.md --format gemini-system
```

**Tahmini süre:** 2-3 ay

---

## Faz 4: Community (v1.0)

**Hedef:** Açık kaynak ekosistem.

| Task | Öncelik | Durum |
|------|---------|-------|
| Spec registry (npm gibi) | Orta | ⬜ |
| Web UI (spec builder) | Orta | ⬜ |
| Topluluk spec'leri | Düşük | ⬜ |
| Benchmark sistemi | Düşük | ⬜ |

**Spec registry örneği:**
```bash
acs search entrepreneur
acs install @erenmustafaozdal/entrepreneur-spec
```

**Tahmini süre:** 6+ ay

---

## Versiyon Takvimi (Tahmini)

| Versiyon | Tarih | Milestone |
|----------|-------|-----------|
| v0.1 | Aralık 2024 | ✅ İlk release |
| v0.2 | Ocak 2025 | Daha fazla örnek + model notları |
| v0.3 | Mart 2025 | CLI tools |
| v0.5 | Haziran 2025 | Platform entegrasyonları |
| v1.0 | 2025 Q4 | Tam ekosistem |

---

## Başarı Metrikleri

| Metrik | v0.2 | v0.5 | v1.0 |
|--------|------|------|------|
| GitHub stars | 50 | 200 | 1000 |
| Örnek spec sayısı | 5 | 15 | 50+ |
| Kör nokta kataloğu | 50 | 80 | 100+ |
| Desteklenen model | 3 | 3 | 5+ |

---

## İlk Adımlar (Bu Hafta)

1. [ ] GitHub repo oluştur
2. [ ] v0.1 tag'le
3. [ ] İlk tweet/post at
4. [ ] 1 yeni persona örneği ekle
5. [ ] GPT adaptasyon notu yaz

---

## Notlar

- Öncelik: Tooling'den önce daha fazla örnek. İnsanlar önce "bu bana uyar mı?" görmek istiyor.
- CLI Node.js veya Python olabilir - hangisi daha hızlı geliştirilebilirse.
- v1.0 öncesi topluluk katkısı almak riskli - kalite kontrolü zor.
