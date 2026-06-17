# ⚽ PFOSTENKRACHER

**Pixel-Elfmeterschießen im 16-Bit-Look – für zwei Spieler oder gegen eine KI.**

Ein komplettes Elfmeterschießen in einer einzigen HTML-Datei. Kein Server, keine
Installation, keine Abhängigkeiten – einfach `pfostenkracher.html` öffnen und
loslegen. Optimiert fürs Handy (Hochformat), spielbar mit Touch oder Maus.

![Plattform](https://img.shields.io/badge/Plattform-Browser-3fcf6a) ![Modus](https://img.shields.io/badge/Modus-2%20Spieler%20%C2%B7%20vs%20KI-4b9bff) ![Stil](https://img.shields.io/badge/Stil-Pixel%2F16--Bit-ffd23f)

---

## 🎮 So wird gespielt

Standardmäßig teilen sich **zwei Spieler ein Gerät** und reichen es abwechselnd
weiter („Pass-and-Play"). In jeder Runde schießt einer, der andere hält – danach
wird getauscht. Im **Einzelspieler-Modus** übernimmt eine KI den zweiten Spieler.

1. **Startbildschirm** → `SPIELEN` antippen.
2. **Länderauswahl:** Per Losentscheid bestimmt das Spiel, **wer zuerst** sein Land
   wählen darf. Beide Spieler suchen sich nacheinander eine Nationalmannschaft aus.
3. **Gerät weitergeben:** Vor jedem Schuss/jeder Parade sagt das Spiel klar an, wer
   das Gerät bekommt und ob er **Schütze** oder **Torwart** ist – so sieht der
   Torwart nicht, wohin der Schütze zielt. (Gegen die KI entfällt das Weitergeben.)
4. **Schütze:** Tippe eine von **15 Zonen** im Tor an, in die du schießen willst.
5. **Torwart:** Tippe die Zone an, in die du springst (in der Mitte reicht ein Schritt).
6. **Die Szene läuft flüssig ab:** Anlauf → Schuss → der Ball fliegt mit hohem Tempo
   ins Tor und das Netz beult sich aus – oder der Torwart fängt ihn ab.
   Per **Wiederholung** lässt sich der Schuss noch einmal ansehen.
7. Nach **5 Runden** (je Spieler 5 Schüsse) gewinnt, wer mehr Tore erzielt hat.
   Steht es uneinholbar, endet das Spiel sofort. Bei Gleichstand geht es ins
   **Sudden Death** (Verlängerung), bis eine Entscheidung fällt.

## 🥅 Trefferzonen & Wahrscheinlichkeiten

Das Tor ist in ein **5×3-Raster (15 Zonen)** unterteilt – für Schütze **und**
Torwart, mit einer **echten Mittelspalte**, um direkt auf den Torwart zu schießen
bzw. dort zu halten. Es zählt nicht nur die exakt richtige Zone: die Haltechance
fällt mit der Distanz zwischen Schuss und Sprung.

Daraus ergibt sich ein **Risiko/Ertrag**-Prinzip (Werte bei zufällig ratendem Keeper):

| Ziel | Tor | gehalten | verfehlt |
| --- | --- | --- | --- |
| **Mitte** | ~40 % | ~54 % | ~4 % |
| halb-außen | ~56 % | ~31 % | ~12 % |
| **ganz außen** | ~60 % | ~14 % | ~24 % |

- **Mitte:** leicht zu treffen, der Torwart deckt sie aber mit dem Körper – wird also
  eher gehalten.
- **Außen:** schwer zu halten, dafür deutlich höhere Gefahr, das Tor ganz zu verfehlen.

Dazu kommen Zufallsmomente für mehr Spannung: **Pfosten**, **Drüber**, **Daneben**,
**Ausrutscher** des Schützen, **Patzer** des Torwarts und gelegentliche **Abpraller**,
die doch noch reingehen.

## 👦 Spieler & Einstellungen

Standardmäßig treten an:

- **Fiete** – der blonde, kleinere Spieler,
- **Jonte** – der größere mit den langen braunen Haaren.

Über `EINSTELLUNGEN` auf dem Startbildschirm lassen sich

- **beide Namen ändern** und
- der **Spielmodus** umschalten (2 Spieler ↔ 1 Spieler · KI).

Namen und Modus werden lokal im Browser gespeichert (`localStorage`).

## 🌍 Mannschaften

15 Nationalteams mit eigenen Trikots und Flaggen:

Deutschland · Brasilien · Argentinien · Frankreich · Italien · Spanien ·
England · Niederlande · Portugal · Japan · Mexiko · Kroatien · Belgien ·
Uruguay · Kolumbien

## ✨ Features

- **16-Bit-Pixeloptik:** schattierte Spieler-Sprites, Stadion mit wogendem Publikum
  in den Farben der beiden Teams, Flutlicht, perspektivischer Rasen mit Strafraum
  und Strafraumbogen, **dreidimensionales Tor mit durchsichtigem weißen Netz**.
- **Realistische Schussszene:** flüssiger Ablauf aus Anlauf, Schuss und Aktion;
  der Schütze dreht sich zum Tor und zeigt beim Anlauf den Rücken; der Torwart
  hechtet menschlich in die Ecken oder macht in der Mitte nur einen Schritt; der
  Ball fliegt mit hohem Tempo, **das Netz verzieht sich am Einschlag** und der Ball
  fällt zu Boden ins Tor. Mit dezenter Zeitlupe und Wiederholungs-Funktion.
- **Einzelspieler gegen KI** oder **2 Spieler lokal** (Pass-and-Play).
- **Hochformat fürs Handy:** füllt den Bildschirm groß aus.
- **Lesbare Pixelschrift** (eigener 5×7-Zeichensatz inkl. Umlauten).
- **Soundeffekte** komplett per Web Audio API erzeugt (Schiedsrichter-Trillerpfeife,
  Schuss, Jubel, Parade, Pfosten, Publikum) – kein einziges Audio-File nötig.
- **Komplett offline & ohne Build:** eine `.html`-Datei, fertig.

## 🕹️ Steuerung

| Aktion | Eingabe |
| --- | --- |
| Auswählen / Bestätigen | Antippen (Touch) oder Klicken |
| Zielen / Springen | Zone im Tor antippen |
| Schuss noch einmal ansehen | `WIEDERHOLUNG` im Spielstand |
| Namen & Modus ändern | `EINSTELLUNGEN` auf dem Startbildschirm |

> Tipp: Beim ersten Antippen aktiviert sich der Ton (Browser-Vorgabe für Audio).

## 🛠️ Technik

- Reines **HTML5 Canvas** + JavaScript, keine Frameworks, keine Build-Tools.
- Internes Render-Format **224 × 398 px** (Hochformat ≈ 9:16), pixelgenau auf die
  Bildschirmgröße hochskaliert.
- Grafik, Schrift, Flaggen und Sound werden **vollständig im Code generiert**.
- Eine Datei: `pfostenkracher.html`.

---

Viel Spaß – und nicht den Pfosten krachen lassen! 🥅💥
