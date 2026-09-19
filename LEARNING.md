# Anthropic Academy (Skilljar) — En Faydalı Kurslar ve Kurulan Skill'ler

Kaynak: https://anthropic.skilljar.com/ (not: bu ortamın ağ politikası bu alan adına
doğrudan erişimi engellediği için sayfalar canlı olarak çekilemedi; aşağıdaki özet,
Anthropic Academy'nin herkese açık kurs kataloğu ve duyurularına dayanır).

## Sizin için en faydalı 4 kurs

1. **Claude Code 101** (`anthropic.skilljar.com/claude-code-101`)
   Claude Code'u günlük geliştirme akışında etkin kullanma: görev tanımlama, plan
   modu, izin/permission modelleri, `CLAUDE.md` ile proje bağlamı verme.
   → Karşılığı: `.claude/skills/claude-code-101/SKILL.md`

2. **Introduction to Agent Skills** ("Skills in Claude Code")
   (`anthropic.skilljar.com/introduction-to-agent-skills`)
   Yeniden kullanılabilir "skill" yazma, yapılandırma, ekip içinde paylaşma ve
   sorun giderme. Bu depoya skill eklemenin tam olarak nasıl yapılacağını anlatır.
   → Karşılığı: `.claude/skills/agent-skill-authoring/SKILL.md`

3. **Building with the Claude API**
   (`anthropic.skilljar.com/claude-with-the-anthropic-api`)
   Model seçimi, sistem promptları, yapılandırılmış (JSON) çıktı alma, streaming,
   prompt caching gibi API entegrasyon pratikleri.
   → Karşılığı: `.claude/skills/claude-api-building/SKILL.md`

4. **Introduction to Model Context Protocol (MCP)**
   (`anthropic.skilljar.com/introduction-to-mcp` civarı)
   MCP'nin üç temel primitifi (tools, resources, prompts) ile Claude'u dış
   servislere bağlayan sunucu/istemci yazma.
   → Karşılığı: `.claude/skills/mcp-fundamentals/SKILL.md`

## Diğer kurslar (daha az öncelikli, genel/rol bazlı)

- Claude 101 / Claude Platform 101 — genel platform tanıtımı (yeni başlayanlar için)
- Introduction to Claude Cowork — Cowork görev döngüsü, plugin/skill kullanımı
- Claude on Google Cloud (Vertex) — sadece GCP/Vertex üzerinden Claude kullananlar için
- AI Fluency for educators — eğitimciler için

## Neden bu 4 tanesi seçildi

Bu depo bir yazılım geliştirme ortamı ve siz Claude Code üzerinden çalışıyorsunuz;
bu yüzden doğrudan iş akışınıza değer katacak (Claude Code kullanımı, skill yazımı,
API entegrasyonu, MCP) kursları önceliklendirdim; rol bazlı (eğitimci, GCP-özel)
kursları listeye almadım.

## Kurulan skill'ler

Aşağıdaki 4 skill `.claude/skills/` altına eklendi. Bunlar bu depodaki (ve bu
depoyu kullanan) Claude Code oturumlarında otomatik olarak devreye girer; ilgili
konu geçtiğinde Claude bu talimatları okuyup uygular.
