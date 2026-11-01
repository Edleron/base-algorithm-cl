# base-algorithm-cl

## Günlük (devlog)

Gün sonunda Geliştirici Günlüğü `edleron/daily/YYYY-MM-DD.md` dosyasına yazılır: `devlog` skill'i (`.claude/skills/devlog/`).
Hafta sonu yapılan iş bir önceki cumanın tarihine yazılır. Bu klasörde sadece günlükler tarihle adlandırılır;
dosyalar Edleron'un hub-brain'ine (Habits) toplanır.

## Oturum

Bu oturumun adı: **narya** (base-algorithm-cl). Sadece kendi reposunda çalışır; başka bir repoya iş o reponun oturumuna mesajla verilir. Repolar arasında iş yapan tek oturum **tolkien**.
Tüm liste: hub-brain deposunda valar/99-mission/02-sessions.md (Windows: C:\Users\edler\Edleron\product\hub-brain, Mac: ~/Edleron/product/hub-brain).

## İki makine (Windows + Mac)

Bu repo hem Windows'ta hem Mac'te kullanılır. Aynı anda tek makinede çalışılır: makineden kalkmadan önce `git push`, diğerinde ilk iş `git pull`. Claude oturumları hub-sync ile taşınır. Dokümanlarda ve skill'lerde yollar repo köküne göre göreli yazılır; mutlak `C:\...` yolu yazılmaz, gerekirse iki biçim birlikte verilir (Windows / Mac). Satır sonları `.gitattributes` ile LF.

Makineye özel ihtiyaçlar:
- .NET SDK (8+) ve runtime'lar her iki makinede: `dotnet --list-sdks`, `dotnet --list-runtimes`.
- `DesingPatterns/Singleton` ve `DesingPatterns/State` `net7.0` hedefliyor; .NET 7 runtime yoksa `dotnet run` çalışmaz (diğerleri `net8.0`).
- Kabuk komutları iki tarafta da aynı (`dotnet new console`, `dotnet run`, `cd ..`).
