# Proje bağlamı

Bu depo, **Cabani** (www.cabani.com.tr) e-ticaret sitesinin geliştirme ve dijital
pazarlama çalışmaları için kullanılıyor.

- **Site altyapısı:** Ticimax (barındırılan/kapalı panel SaaS e-ticaret platformu).
  Ticimax'ta doğrudan sunucu/kod erişimi yoktur; tema (HTML/CSS/JS) düzenlemesi
  panelin "Tasarım Yedekleme / CSS Erişimi / JavaScript Erişimi" özelliklerinin
  açık olmasını gerektirir (Special Extra Paket, OMNİ Paket veya İleri Seviye
  Bulut Çözümleri paketlerinde mevcuttur).
- **Kullanıcı rolü:** E-ticaret yöneticisi + dijital pazarlama uzmanı. Hedef:
  siteyi geliştirmek ve online satışları artırmak.

## Ticimax tema kodu üzerinde çalışırken

- Tema dosyaları panelden dışa aktarılıp bu depoya (`tema/` klasörü altında)
  konarak Claude Code ile düzenlenir, sonra panele geri yüklenir. Ticimax'ın
  kendisi sürüm geçmişi tutmadığı için bu depodaki git geçmişi tek "değişiklik
  kaydı" kaynağıdır — anlamlı commit mesajları önemli.
- Canlı siteye dokunan bir değişikliği panele yüklemeden önce yerelde/bir
  önizleme ortamında doğrulayın; panel geri yüklemesi geri alınması kolay
  olmayan bir adımdır.

## SEO ve pazarlama çalışmaları

- SEO denetimleri ve içerik/kampanya çalışmaları panel erişimi gerektirmez;
  canlı site URL'leri (`https://www.cabani.com.tr/...`) üzerinden yapılır.

## İlgili skill'ler

- `.claude/skills/ticimax-workflow/` — Ticimax'a özgü geliştirme iş akışı.
- `.claude/skills/ecommerce-seo-audit/` — teknik + sayfa içi SEO denetimi.
- `.claude/skills/cro-audit/` — dönüşüm oranı (satış hunisi) denetimi.
- `.claude/skills/product-content-tr/` — Türkçe ürün/kategori/meta/reklam metinleri.
- `.claude/skills/campaign-calendar-tr/` — Türkiye perakende takvimine göre kampanya planı.
- `.claude/skills/ads-performance-review/` — Google/Meta/TikTok reklam raporu analizi.
- `.claude/skills/competitor-analysis/` — rakip analizi.
- `.claude/skills/campaign-ideas/` — marj kontrollü kampanya/promosyon önerileri.
- `.claude/skills/meta-ads-strategy/` — Meta (Facebook/Instagram) reklam kurgusu ve kreatif önerileri.
- `.claude/skills/category-architecture/` — kategori/menü yapısı, filtreler, 301 planı.
- `.claude/skills/product-sorting/` — skor tabanlı ürün sıralaması ve vitrin.
- `.claude/skills/frontend-design/` — özgün arayüz tasarımı ilkeleri (Anthropic, Apache 2.0).
- `.claude/skills/webapp-testing/` — Playwright ile tema önizleme/test (Anthropic, Apache 2.0).
- `.claude/skills/claude-code-101/`, `.claude/skills/agent-skill-authoring/` —
  Claude Code kullanım referansları.

## Alt ajanlar (`.claude/agents/`)

- `seo-auditor` — SEO denetimi, panel/tema kodu ayrımlı öncelik listesi.
- `cro-analyst` — mobil/masaüstü huni incelemesi, ICE skorlu öneriler.
- `ticimax-theme-dev` — `tema/` altındaki HTML/CSS/JS düzenlemeleri.
- `content-writer-tr` — Türkçe e-ticaret metinleri.
- `marketing-strategist` — kampanya planı/önerileri, Meta reklam kurgusu, rakip ve reklam performans analizi.
- `merchandiser` — kategori yapısı, ürün sıralaması, vitrin ve promosyon önerileri.

Alt ajanlar hiçbir zaman panele yükleme yapmaz, reklam bütçesi değiştirmez
veya sipariş/ödeme oluşturmaz; bunlar kullanıcı onayı gerektirir.
