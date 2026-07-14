<div dir="rtl">

<p align="center">
  <a href="https://opencode.ai">
    <picture>
      <source srcset="packages/console/app/src/asset/logo-ornate-dark.svg" media="(prefers-color-scheme: dark)">
      <source srcset="packages/console/app/src/asset/logo-ornate-light.svg" media="(prefers-color-scheme: light)">
      <img src="packages/console/app/src/asset/logo-ornate-light.svg" alt="OpenCode logo">
    </picture>
  </a>
</p>
<p align="center">סוכן ה-AI לפיתוח קוד בקוד פתוח.</p>
<p align="center">
  <a href="https://opencode.ai/discord"><img alt="Discord" src="https://img.shields.io/discord/1391832426048651334?style=flat-square&label=discord" /></a>
  <a href="https://www.npmjs.com/package/opencode-ai"><img alt="npm" src="https://img.shields.io/npm/v/opencode-ai?style=flat-square" /></a>
  <a href="https://github.com/anomalyco/opencode/actions/workflows/publish.yml"><img alt="Build status" src="https://img.shields.io/github/actions/workflow/status/anomalyco/opencode/publish.yml?style=flat-square&branch=dev" /></a>
</p>

<p align="center">
  <a href="README.he.md">עברית</a> |
  <a href="README.md">English</a> |
  <a href="README.zh.md">简体中文</a> |
  <a href="README.zht.md">繁體中文</a> |
  <a href="README.ko.md">한국어</a> |
  <a href="README.de.md">Deutsch</a> |
  <a href="README.es.md">Español</a> |
  <a href="README.fr.md">Français</a> |
  <a href="README.it.md">Italiano</a> |
  <a href="README.da.md">Dansk</a> |
  <a href="README.ja.md">日本語</a> |
  <a href="README.pl.md">Polski</a> |
  <a href="README.ru.md">Русский</a> |
  <a href="README.bs.md">Bosanski</a> |
  <a href="README.ar.md">العربية</a> |
  <a href="README.no.md">Norsk</a> |
  <a href="README.br.md">Português (Brasil)</a> |
  <a href="README.th.md">ไทย</a> |
  <a href="README.tr.md">Türkçe</a> |
  <a href="README.uk.md">Українська</a> |
  <a href="README.bn.md">বাংলা</a> |
  <a href="README.gr.md">Ελληνικά</a> |
  <a href="README.vi.md">Tiếng Việt</a>
</p>

[![OpenCode Terminal UI](packages/web/src/assets/lander/screenshot.png)](https://opencode.ai)

---

### התקנה

<div dir="ltr">

```bash
# YOLO
curl -fsSL [https://opencode.ai/install](https://opencode.ai/install) | bash

# מנהלי חבילות (Package managers)
npm i -g opencode-ai@latest         # or bun/pnpm/yarn
scoop install opencode             # Windows
choco install opencode             # Windows
brew install anomalyco/tap/opencode # macOS and Linux (מומלץ, תמיד מעודכן)
brew install opencode              # macOS and Linux (הנוסחה הרשמית של brew, מתעדכנת פחות)
sudo pacman -S opencode            # Arch Linux (Stable)
paru -S opencode-bin               # Arch Linux (הכי מעודכן מ-AUR)
mise use -g opencode               # לכל מערכות ההפעלה
nix run nixpkgs#opencode           # or github:anomalyco/opencode לענף הפיתוח האחרון (dev)

```

<div dir="rtl">
  > [!TIP]
> יש להסיר גרסאות ישנות יותר מ-0.1.x לפני ההתקנה.
</div>

### אפליקציית דסקטופ (BETA)

OpenCode זמין גם כאפליקציית שולחן עבודה (Desktop). ניתן להוריד אותה ישירות מ[עמוד הגרסאות (Releases)](https://github.com/anomalyco/opencode/releases) או מהקישור [opencode.ai/download](https://opencode.ai/download).

| Platform | Download |
| --- | --- |
| macOS (Apple Silicon) | `opencode-desktop-mac-arm64.dmg` |
| macOS (Intel) | `opencode-desktop-mac-x64.dmg` |
| Windows | `opencode-desktop-windows-x64.exe` |
| Linux | `.deb`, `.rpm`, or `.AppImage` |

```bash
# macOS (Homebrew)
brew install --cask opencode-desktop
# Windows (Scoop)
scoop bucket add extras; scoop install extras/opencode-desktop

```

#### תיקיית התקנה

סקריפט ההתקנה מתחשב בסדר העדיפויות הבא עבור נתיב ההתקנה:

1. `$OPENCODE_INSTALL_DIR` - תיקיית התקנה מותאמת אישית
2. `$XDG_BIN_DIR` - נתיב התואם למפרט התיקיות של XDG Base
3. `$HOME/bin` - תיקיית קבצי הרצה סטנדרטית של המשתמש (אם היא קיימת או שניתן ליצור אותה)
4. `$HOME/.opencode/bin` - נתיב ברירת המחדל לגיבוי (Fallback)

```bash
# דוגמאות
OPENCODE_INSTALL_DIR=/usr/local/bin curl -fsSL [https://opencode.ai/install](https://opencode.ai/install) | bash
XDG_BIN_DIR=$HOME/.local/bin curl -fsSL [https://opencode.ai/install](https://opencode.ai/install) | bash

```

### סוכנים (Agents)

OpenCode כולל שני סוכנים מובנים שניתן לעבור ביניהם באמצעות מקש ה-`Tab`.

* **build** - סוכן ברירת המחדל, בעל גישה מלאה לעבודת פיתוח וכתיבה.
* **plan** - סוכן לקריאה בלבד (Read-only) לצורך ניתוח וחקר קוד.
* חוסם עריכת קבצים כברירת מחדל.
* מבקש אישור מפורש לפני הרצת פקודות bash.
* אידיאלי לחקירת בסיסי קוד לא מוכרים או לתכנון שינויים.



בנוסף, כלול גם סוכן משנה **general** לחיפושים מורכבים ומשימות מרובות שלבים.
סוכן זה משמש את המערכת באופן פנימי וניתן להפעיל אותו ידנית באמצעות `@general` בתוך ההודעות.

למידע נוסף על [סוכנים](https://opencode.ai/docs/agents).

### תיעוד (Documentation)

למידע נוסף על אופן הגדרת התצורה של OpenCode, **[עבור אל מדריכי התיעוד שלנו](https://opencode.ai/docs)**.

### תרומה לפרויקט (Contributing)

אם אתה מעוניין לתרום ל-OpenCode, אנא קרא את [הנחיות התרומה שלנו](https://www.google.com/search?q=./CONTRIBUTING.md) לפני הגשת Pull Request.

### פיתוח על בסיס OpenCode

אם אתה עובד על פרויקט שקשור ל-OpenCode ומשתמש במילה "opencode" כחלק משמו, לדוגמה "opencode-dashboard" או "opencode-mobile", אנא הוסף הערה ברורה לקובץ ה-README שלך המבהירה כי הפרויקט לא נבנה על ידי צוות OpenCode ואינו קשור אלינו בשום צורה.

---

**הצטרף לקהילה שלנו** [Discord](https://discord.gg/opencode) | [X.com](https://x.com/opencode)
