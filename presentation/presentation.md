---
theme: seriph
title: Slidev – Präsentationen für IT-Profis
titleTemplate: '%s | Slidev'
info: |
  ## Slidev für IT Lehrlinge 
  Eine Einführung für IT-Lehrpersonen in der Schweiz
author: IT-Lehrperson
keywords: slidev, präsentation, it, lehrlinge, ausbildung, schweiz
highlighter: shiki
lineNumbers: true
drawings:
  persist: false
transition: slide-left
mdc: true
---

# Slidev

### Präsentationen mit Code – für IT-Lehrlinge UPDATE

<div class="pt-12">
  <span class="px-2 py-1 rounded cursor-pointer" hover="bg-white bg-opacity-10">
    Präsentation für IT-Lehrpersonen · Schweiz · 2024
  </span>
</div>

<div class="abs-br m-6 flex gap-2">
  <a href="https://sli.dev" target="_blank" class="text-xl slidev-icon-btn opacity-50 !border-none !hover:text-white">
    sli.dev
  </a>
</div>

<!--
Herzlich willkommen! Heute zeige ich euch ein Werkzeug, das Präsentationen mit modernem Entwickler-Workflow verbindet: Slidev. Die Idee: Wer Markdown und Code kennt, kann damit professionelle Präsentationen erstellen – ideal für unsere IT-Lehrlinge.
-->


---
layout: default
---

# Agenda

<Toc minDepth="1" maxDepth="1" />

<!--
Wir haben etwa 10–15 Minuten. Ich zeige euch die wichtigsten Funktionen, wie man Slidev installiert und wie ihr es in der Ausbildung einsetzen könnt.
-->

---
layout: section
---

# Was ist Slidev?

---
layout: two-cols
---

# Was ist Slidev?

- **Markdown-basiertes** Präsentationstool für Entwickler
- Erstellt von [Anthony Fu](https://antfu.me) (Vue-Core-Team)
- Läuft als **lokale Web-App** (Node.js)
- Folien = einfache `.md`-Datei
- Vollständige **Vue.js**-Unterstützung
- Open Source (MIT) · [github.com/slidevjs/slidev](https://github.com/slidevjs/slidev)

::right::

```md
---
theme: seriph
---

# Meine erste Folie

- Punkt 1
- Punkt 2

---

# Zweite Folie

Hier kommt der Inhalt.
```

<!--
Slidev ist kein PowerPoint-Ersatz, sondern ein Tool für Leute, die schon mit Code und Markdown vertraut sind. Die gesamte Präsentation steckt in einer einzigen Markdown-Datei – das macht sie versionierbar, teilbar und wartbar.
-->

---

# Warum Slidev?
<v-clicks>

* Git-freundlich
* Code-Highlighting
* Codenahes arbeiten für IT-Lehrlinge
* Themes & Layouts über CSS
* Kostenlos

</v-clicks>

<!--
Für IT-Lehrlinge ist die Stärke klar: Sie arbeiten sowieso mit Markdown, Git und Code. Slidev passt in ihren Workflow. Das fördert auch technische Kompetenz – Präsentation als Code.
-->

---
layout: section
---

# Hauptfunktionen

---

# Markdown-basierte Folien

Folien werden durch `---` getrennt. Frontmatter konfiguriert das Verhalten:

````md
---
theme: seriph
transition: fade
lineNumbers: true
---

# Folientitel

Normaler **Markdown**-Inhalt mit `Code`, Listen und mehr.

---
layout: two-cols
---

# Links
Inhalt links

::right::

# Rechts
Inhalt rechts
````

<!--
Die gesamte Präsentation ist eine einzige .md-Datei. Das ist der Kern von Slidev: Text, den man versionieren, reviewen und per Pull Request bearbeiten kann.
-->

---
layout: two-cols
---

# Syntax-Highlighting

Slidev nutzt [Shiki](https://shiki.style) für Code-Highlighting:

````md
    ```python {none|1-3|4-6|all}
    def fibonacci(n: int) -> int:
        if n <= 1:
            return n
        a, b = 0, 1
        for _ in range(2, n + 1):
            a, b = b, a + b
        return b
    ```
````

::right::
Zeilen werden schrittweise hervorgehoben

```python {none|1-3|4-6|all}
def fibonacci(n: int) -> int:
    if n <= 1:
        return n
    a, b = 0, 1
    for _ in range(2, n + 1):
        a, b = b, a + b
    return b
```

<!--
Besonders nützlich für Lehrlinge, die Code erklären müssen: Man kann Zeilen schrittweise einblenden und so den Fokus lenken. Shiki unterstützt über 100 Sprachen und alle gängigen Themes.
-->

---

# Animationen & Klick-Übergänge

Mit `v-click` und `v-after` lassen sich Inhalte schrittweise einblenden:

```md
<v-click>

Dieser Text erscheint beim ersten Klick.

</v-click>

<v-click>

- Punkt A erscheint beim zweiten Klick
- Und dieser danach

</v-click>
```

<v-click>

✅ Erster Klick: dieser Text erscheint

</v-click>

<v-click>

✅ Zweiter Klick: und dieser hier

</v-click>

<!--
v-click ist simpel aber mächtig. Lehrlinge müssen kein CSS oder JS können – es reicht, den Tag zu kennen.
-->

---
layout: two-cols
---

# Layouts

Slidev liefert viele Layouts ab Werk:

- `default` – Standard
- `two-cols` – Zweispaltig (diese Folie!)
- `section` – Kapitelüberschrift
- `quote` – Zitat
- `image-right` / `image-left` – Bild + Text
- `center` – Zentriert
- `full` – Vollbild
- `intro` – Vorstellungsfolie

::right::

```md
---
layout: image-right
image: https://picsum.photos/720
---

# Folientitel

Text erscheint links,
Bild rechts.
```

<!--
Layouts geben schnell Struktur. Kein Design-Studium nötig. Lehrlinge können einfach das passende Layout wählen.
-->

---

# Themes

Themes werden im Frontmatter gesetzt – und können sofort gewechselt werden:

```md
---
theme: seriph
---
```

**Offizielle Themes:**

| Theme         | Stil                                       |
|---------------|--------------------------------------------|
| `default`     | Minimal, sauber                            |
| `seriph`      | Formal, Serif-Schrift (diese Präsentation) |
| `apple-basic` | Modern, Apple-Keynote-Stil                 |
| `bricks`      | Hell, geometrisch                          |

Community-Themes: [sli.dev/themes/gallery](https://sli.dev/themes/gallery.html)

<!--
Ein Theme zu wechseln dauert eine Sekunde. Das ist ideal für Lehrlinge, die verschiedene Präsentationsstile ausprobieren möchten, ohne das Design selbst zu bauen.
-->

---
layout: two-cols
---

# Presenter-Modus & Speaker Notes

Speaker Notes werden als HTML-Kommentare geschrieben:

```md
# Meine Folie

Inhalt hier.

<!--
Das sind die Speaker Notes.
Nur im Presenter-Modus sichtbar.
-->
```

**Presenter-Modus starten:**

```bash
slidev --open
```

Dann: Präsentations-Fenster + Notizen-Fenster gleichzeitig

::right::

<div class="flex flex-col items-center justify-center h-full gap-4">
  <div class="border rounded p-4 text-center w-full">
    <div class="text-sm opacity-60">Publikums-Fenster</div>
    <div class="text-2xl mt-2">📺 Folie</div>
  </div>
  <div class="border rounded p-4 text-center w-full bg-blue-900 bg-opacity-20">
    <div class="text-sm opacity-60">Presenter-Fenster</div>
    <div class="text-sm mt-2">📝 Notizen · Timer · Nächste Folie</div>
  </div>
</div>

<!--
Der Presenter-Modus ist professionell: Man sieht die eigenen Notizen, den Timer und die nächste Folie. Genau wie in Keynote oder PowerPoint – aber komplett im Browser. Yes
-->

---

# Export-Möglichkeiten

```bash
# Als PDF exportieren
slidev export

# Als PNG-Bilder
slidev export --format png

# Als interaktive Web-App (SPA)
slidev build
```

| Format | Einsatz                           |
|--------|-----------------------------------|
| PDF    | Abgabe, Druck, E-Mail             |
| PNG    | Vorschaubilder, Thumbnails        |
| SPA    | Hosting auf GitHub Pages, Netlify |

<!--
Lehrlinge können ihre Präsentation als PDF abgeben oder direkt auf GitHub Pages hosten – ohne Kosten, ohne fremde Cloud-Services.
-->

---
layout: section
---

# Versionskontrolle & Zusammenarbeit

---

# Slidev + Git = perfektes Match

Da die Präsentation eine einzige Textdatei ist:

```bash
git init
git add slides.md
git commit -m "Erste Version der Projektpräsentation"

# Änderung dokumentieren
git commit -m "Kapitel über Architektur ergänzt"

# Review via Pull Request
git checkout -b feedback/kapitel-2
```

**Vorteile:**

- 📜 Vollständige **Versionsgeschichte**
- 🔍 Diff-Ansicht zeigt genau was sich geändert hat
- 🤝 **Pull Requests** für Feedback möglich
- 🔄 Einfaches **Rollback** auf alte Version

<!--
Das ist der Moment, wo Lehrlinge merken: Das ist nicht nur Präsentation, das ist Software-Engineering. Genau dieselben Workflows wie im Betrieb.
-->

---

# Erste Schritte im Unterricht

**Voraussetzungen:**

- Node.js 18+ installiert
- Grundkenntnisse Markdown (1 Lektion reicht)
- Git (optional, aber empfohlen)

**Einstieg in 4 Befehlen**

```bash
# Neues Slidev-Projekt erstellen
npm create slidev@latest meine-praesentation

# In Ordner wechseln & starten
cd meine-praesentation
npm i
npm run dev
```

→ Browser öffnet sich automatisch auf `http://localhost:3030`

<!--
Das Schöne: In 5 Minuten haben Lehrlinge ihre erste laufende Präsentation. Danach lernen sie durch Ausprobieren. Das motiviert.
-->

---
layout: section
---

# Live-Demo

---

# Was wir gesehen haben

<v-click>

✅ **Markdown-Folien** — einfach, versionierbar, im Git

</v-click>
<v-click>

✅ **Code-Highlighting** — Shiki, 100+ Sprachen, Schritt-Animation

</v-click>
<v-click>

✅ **Layouts & Themes** — sofort einsatzbereit, kein Design nötig

</v-click>
<v-click>

✅ **Presenter-Modus** — professionell, mit Timer und Notizen

</v-click>
<v-click>

✅ **Export** — PDF, PNG, Web-Hosting

</v-click>
<v-click>

✅ **Git-Integration** — Review, Versionshistorie, Kollaboration

</v-click>
<v-click>

✅ **Einsatz in der Ausbildung** — Schule, Betrieb, IPA

</v-click>

<!--
Kurze Zusammenfassung bevor wir zur Diskussion kommen.
-->

---
layout: end
---

# Fragen & Diskussion

<div class="grid grid-cols-2 gap-8 mt-8">
<div>

**Weiterführendes**

- [sli.dev](https://sli.dev) — Offizielle Doku
- [sli.dev/themes/gallery](https://sli.dev/themes/gallery.html) — Themes
- [github.com/slidevjs/slidev](https://github.com/slidevjs/slidev) — GitHub

</div>
<div>

**Diese Präsentation**

- Erstellt mit Slidev + Theme `seriph`
- Liegt als `slides.md` im Repo
- Startbar via Docker Compose

</div>
</div>

<!--
Danke für eure Aufmerksamkeit! Habt ihr Fragen zu Slidev, zum Einsatz im Unterricht oder zu technischen Details?
-->


---
layout: TwoColsFooter
---

::left::

# Custom Layouts

## Template - Vue.js

```html {all|4,7,10,13,all}

<template>
    <div class="slidev-layout footer-layout">
        <div class="left">
            <slot name="left"/>
        </div>
        <div class="right">
            <slot name="right"/>
        </div>
        <div class="footer footer-left">
            <slot name="footer-left"/>
        </div>
        <div class="footer footer-right">
            <slot name="footer-right"/>
        </div>
    </div>
</template>
```

::right::

# <span style="opacity:0">Markdown</span>

## Markdown

```md {none|2,6,10,13|all}
# Custom Layouts

::left::

## Template - Vue.js

((SOME md here ;-) ))

::right::

## Markdown

((SOME md here ;-) ))

::footer-left::

#### Some Footer Content

::footer-right::

#### Speaker: Martin Käser
```

::footer-left::

#### Some Footer Content

::footer-right::

#### Speaker: Martin Käser
