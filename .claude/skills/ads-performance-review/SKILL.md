---
name: ads-performance-review
description: Reviewing Google Ads, Meta Ads, and TikTok Ads performance for Cabani from exported CSV/XLSX reports or connected ad tools — ROAS/CPA/CTR analysis, wasted spend, creative fatigue, budget reallocation. Use when the user shares an ad report or asks "reklamlarım nasıl gidiyor", ROAS düşük, bütçe dağılımı, or which campaigns to pause/scale.
---

# Reklam performans analizi

## Veri kaynağı
- **Supermetrics** bağlıysa önce onu kullan: Google Ads, Meta Ads, TikTok Ads
  ve GA4 verisini aynı tarih aralığıyla çek (`data_source_discovery` →
  `accounts_discovery` → `field_discovery` → `data_query`). GA4 gelirini
  platform dönüşüm değeriyle karşılaştır.
- Diğer bağlı reklam araçları (Adspirer/AdWhispr MCP vb.) varsa oradan çek.
- Yoksa kullanıcıdan dışa aktarılmış rapor iste (son 30 gün + önceki 30 gün,
  kampanya/reklam seti/reklam düzeyinde): harcama, gösterim, tıklama,
  dönüşüm, dönüşüm değeri.
- **Hiçbir değişikliği (duraklatma, bütçe, yayına alma) kullanıcı onayı
  olmadan uygulama** — bunlar para harcatan, dışa dönük işlemlerdir.

## Analiz adımları
1. **Hesap özeti:** harcama, ciro, ROAS, CPA, CTR, CVR — dönem karşılaştırmalı.
2. **Başabaş ROAS** = 1 / brüt marj. Marj bilinmiyorsa sor; hedef ROAS'ı buna göre yorumla.
3. **Kazananlar / kaybedenler:** ROAS'a göre sırala, yeterli veri eşiği
   uygula (ör. ≥ 30 tıklama veya ≥ 3× hedef CPA harcama) — az veriyle karar verme.
4. **İsraf:** dönüşümsüz yüksek harcamalı arama terimleri (negatif anahtar
   kelime önerisi), düşük CTR'lı reklamlar, frekansı > 3-4 olan Meta kitleleri.
5. **Kreatif yorgunluğu:** CTR'ın zaman içinde düşüp CPM'in arttığı reklamlar.
6. **Takip sağlığı:** platform dönüşümleri ile Ticimax sipariş sayısı çok
   farklıysa önce pixel/Conversions API/GA4 kurulumunu şüphelen.

## Çıktı
- Tek paragraf yönetici özeti.
- Aksiyon tablosu: **Kampanya | Sorun | Öneri (Ölçekle/Optimize et/Durdur) | Beklenen etki**.
- Bütçe yeniden dağıtım önerisi (mevcut → önerilen).
- Grafik gerekiyorsa `dataviz` skill'ini kullan.
