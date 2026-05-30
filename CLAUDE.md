# CLAUDE.md

Kontext für KI-Assistenten, die an diesem Projekt arbeiten.

## Was ist dieses Projekt?

Ein Team-Rätsel, das Toki Pona (eine Plansprache mit ~120 Wörtern) als Pseudocode-Sprache verwendet. Ziel ist es, den Code zu lesen und zu verstehen – ohne KI-Hilfe.

Das Projekt besteht aus:
- Dem Rätsel selbst (Pseudocode-Schnipsel)
- Einem druckbaren Gewinner-Zertifikat in sitelen pona (dem Schriftsystem von Toki Pona)

## Sprache & Konzepte

### Toki Pona-Grundlagen

Toki Pona hat ~120 Wörter. Relevante Wörter für dieses Projekt:

| Wort | Bedeutung |
|---|---|
| `open` | Anfang, öffnen, starten |
| `pini` | Ende, fertig, stoppen |
| `pali` | Arbeit, Prozess, Programm |
| `toki` | sprechen, Sprache, ausgeben |
| `pi` | Zugehörigkeit (Genitivpartikel, gruppiert Modifikatoren) |
| `e` | direktes Objekt (Akkusativmarker) |
| `li` | Prädikatmarker |
| `jan` | Person, Mensch |
| `sona` | Wissen, verstehen |
| `ilo` | Werkzeug, Gerät |
| `nasa` | seltsam, verrückt, ungewöhnlich |
| `ma` | Land, Ort, Welt |
| `ali` | alles, alle |
| `sina` | du, ihr |
| `kepeken` | benutzen, mit |
| `wile` | wollen, brauchen, müssen |
| `ni` | dies, das |
| `tan` | weil, von, Grund |
| `ona` | er/sie/es/sie (pl.) |
| `lukin` | sehen, schauen, Auge |
| `sitelen` | Zeichen, Bild, schreiben/zeichnen |
| `kama` | kommen, werden, ankommen |
| `tenpo` | Zeit, Moment |
| `lawa` | Kopf, Kontrolle, führen |
| `kulupu` | Gruppe, Gemeinschaft, Team |

### Grammatik (kurz)

```
[Subjekt] li [Prädikat] (e [Objekt])
jan li toki e nimi  →  Die Person spricht ein Wort

[Subjekt] li [Prädikat] tan ni: [Begründung]
ona li kama jan sona tan ni: ona li sona e toki nasa
→  Sie wurde Wissende, weil sie die seltsame Sprache verstand
```

### Der Pseudocode im Detail

```
open pi pali          # Beginn des Programms
    toki e "..."      # Ausgabe (print) des Strings
pini pi pali          # Ende des Programms
```

Der ausgegebene String:
```
toki ma ali! sina kepeken sona pi ilo sona nasa tan ni: sina wile sona e toki ni.
```
Bedeutung: *„Hallo Welt! Du benutzt Wissen über seltsame Computer-Werkzeuge, weil du diese Sprache verstehen wolltest."*

## Das Zertifikat (`jan-sona-certificate.html`)

### Technischer Aufbau

- Reines HTML/CSS, keine externen Abhängigkeiten
- Glyphen als inline SVG-Pfade (kein Font nötig)
- Druckbar via `window.print()` / Browser-Druckdialog → PDF

### Warum SVG statt Font?

sitelen pona Fonts (z.B. `nasin-nanpa`, `linja-pona`) sind nicht über öffentliche CDNs zuverlässig ladbar. Die SVG-Lösung ist robuster und funktioniert offline.

### Zertifikatstext (Toki Pona → Deutsch)

| sitelen pona | Toki Pona | Deutsch |
|---|---|---|
| Titel | lipu sona | Urkunde des Wissens |
| Zeile 1 | jan ni li kama jan sona tan ni: | Diese Person wurde zur Wissenden, weil: |
| Zeile 2 | ona li sona e toki nasa pi ilo sona | sie die seltsame Sprache der Computer versteht |
| Zeile 3 | ona li lukin e sitelen nasa li sona e ona | sie die seltsamen Zeichen sah und sie verstand |
| Siegel | toki pona | Toki Pona |
| Links | jan lawa / pali kulupu | Teamleitung / Gruppenarbeit |
| Rechts | tenpo ni | Datum |

### Änderungen am Zertifikat

Wenn du Glyphen anpassen willst: Jede Glyphe ist ein `<div class="glyph">` mit einem `<svg viewBox="0 0 40 40">` und einem `<span class="word">`. SVG-Koordinatensystem ist 40×40px.

Größenklassen: `.xl` (52px), `.lg` (42px), `.md` (34px), `.sm` (26px)

## Designentscheidungen

- **Pergament-Optik** (`#fdf6e3`) mit Goldtönen (`#8b6914`) – bewusst urkundenartig
- **Doppelrahmen** – klassisches Zertifikat-Motiv
- **Kursive Labels** unter den Glyphen – lesbar für Nicht-Toki-Pona-Sprecher, dezent in Goldton
- **Doppelpunkt-Glyphe** (zwei gefüllte Kreise) – grammatikalisch korrekte Interpunktion in sitelen pona

## Bekannte Einschränkungen

- Die SVG-Glyphen sind vereinfachte Interpretationen der offiziellen sitelen pona Designs, keine 1:1-Reproduktionen
- Der Name des Gewinners wird in lateinischer Schrift eingegeben (Eigennamen werden in sitelen pona in einem Cartouche geschrieben, was hier der Einfachheit halber weggelassen wurde)
