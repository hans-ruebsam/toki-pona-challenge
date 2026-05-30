# Esoterische Implementierungen

> Weil eine obskure Plansprache offensichtlich nicht genug ist.

Der Toki-Pona-String aus dem Rätsel:

```
toki ma ali! sina kepeken sona pi ilo sona nasa tan ni: sina wile sona e toki ni.
```

...existiert auch in zwei weiteren Sprachen, die niemand braucht aber alle lieben.

---

## Brainfuck (`hello-world.bf`)

Erschaffen 1993 von Urban Müller. Ziel: eine Turing-vollständige Sprache mit minimalem Compiler.

**Die 8 Befehle:**

| Befehl | Bedeutung |
|---|---|
| `>` | Zeiger nach rechts |
| `<` | Zeiger nach links |
| `+` | Zelle incrementieren |
| `-` | Zelle decrementieren |
| `.` | Zelle als ASCII ausgeben |
| `,` | ASCII-Zeichen einlesen |
| `[` | Sprung nach `]` wenn Zelle = 0 |
| `]` | Sprung nach `[` wenn Zelle ≠ 0 |

**Implementierungsdetails:**

Jedes Zeichen wird als ASCII-Wert aufgebaut. Statt naiv 116× `+` für `t` (ASCII 116) zu schreiben, werden Multiplikations-Schleifen eingesetzt wo sie kürzer sind:

```brainfuck
>++++++++[<++++++++++++++>-]<
```

Das baut `8 × 14 = 112`, dann `++++` für 116 – statt 116 einzelner `+`.

**Länge:** 1526 Zeichen für 81 Ausgabe-Zeichen. Effizienz: fragwürdig. Eleganz: keine.

---

## Shakespeare Programming Language (`hello-world.spl`)

Erschaffen 2001 von Karl Hasselström und Jon Åslund. Ziel: Programme wie elisabethanische Theaterstücke aussehen lassen.

**Konzepte:**

- **Charaktere** sind Variablen (müssen historische/shakespearsche Namen haben)
- **Akte und Szenen** strukturieren den Code
- **Werte** werden durch poetische Aussagen gesetzt:
  - Substantive: positiv (`a lord`, `a flower`) = +1, negativ (`a pig`, `a toad`) = -1
  - Adjektive **verdoppeln** den Wert: `a good lord` = 2, `a good good lord` = 4
  - Additionen: `the sum of X and Y`
- **`Speak your mind!`** gibt den Wert des angesprochenen Charakters als ASCII-Zeichen aus

**Beispiel – Kodierung von `t` (ASCII 116 = 64+32+16+4):**

```
Ophelia:
You are the sum of the sum of the sum of
  the product of good good a lord and
  the product of good good good good a lord and
  the product of good good good good good a lord and
  the product of good good good good good good a lord.
Speak your mind!
```

**Struktur des Stücks:**

- Zwei Charaktere: **Hamlet** (Empfänger/Sprecher) und **Ophelia** (Encoderin)
- 11 Szenen, je ~8 Zeichen
- 398 Zeilen für 81 Ausgabe-Zeichen

**Länge:** 398 Zeilen. Jede Zeile Poesie. Kein einziges sinnvolles Wort.

---

## Warum?

```
open pi pali
    toki e "..."
pini pi pali
```

Weil `open pi pali` auf Toki Pona „Beginn des Programms" heißt –
und Brainfuck sowie SPL beweisen, dass man denselben Gedanken
in jeder noch so absurden Form ausdrücken kann.

*ona li nasa. taso ona li pona.* 🙂
*(Es ist verrückt. Aber es ist gut.)*
