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
- `.claude/skills/find-skills/` — Açık skill ekosisteminden (`npx skills`,
  https://skills.sh) yeni skill bulma/yükleme (kaynak: `vercel-labs/skills`).

## Dışarıdan skill yükleme kuralı

- `npx skills find` / `find-skills` ile bulunan bir skill **yalnızca kaynak
  GitHub deposu en az 30.000 yıldıza sahipse** yüklenir. Yüklemeden önce
  deponun yıldız sayısını doğrulayın; eşiğin altındakileri yüklemeyin, sadece
  kullanıcıya bilgi olarak sunun (yıldız sayısıyla birlikte).
- Skill'ler proje düzeyinde yüklenir (`-g` kullanmadan), böylece
  `.claude/skills/` altına ve `skills-lock.json`'a yazılıp git'e commit edilir.
  Bulut oturumları geçici olduğundan global (`-g`) kurulum kalıcı olmaz.
- Yüklenen skill'in `SKILL.md` dosyasını commit etmeden önce okuyun; skill'ler
  tam ajan yetkileriyle çalışır.
