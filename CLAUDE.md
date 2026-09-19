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
- `.claude/skills/claude-code-101/`, `.claude/skills/agent-skill-authoring/` —
  Claude Code kullanım referansları.
