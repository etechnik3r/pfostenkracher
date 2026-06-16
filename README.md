# ⚽ PFOSTENKRACHER

**Pixel-Elfmeterschießen für zwei Spieler – ein Browser-Spiel im 16-Bit-Look.**

Ein komplettes Elfmeterschießen in einer einzigen HTML-Datei. Kein Server, keine
Installation, keine Abhängigkeiten – einfach `pfostenkracher.html` öffnen und
loslegen. Optimiert fürs Handy (Hochformat), spielbar mit Touch oder Maus.

![Spielprinzip](https://img.shields.io/badge/Plattform-Browser-3fcf6a) ![Spieler](https://img.shields.io/badge/Spieler-2%20lokal-4b9bff) ![Stil](https://img.shields.io/badge/Stil-Pixel%2F16--Bit-ffd23f)

---

## 🎮 So wird gespielt

Zwei Spieler teilen sich **ein Gerät** und reichen es abwechselnd weiter
(„Pass-and-Play"). In jeder Runde schießt einer, der andere hält – danach wird
getauscht.

1. **Startbildschirm** → `SPIELEN` antippen.
2. **Länderauswahl:** Per Zufall entscheidet das Spiel, **wer zuerst** sein Land
   wählen darf. Beide Spieler suchen sich nacheinander eine Nationalmannschaft aus.
3. **Handy weitergeben:** Vor jedem Schuss/jeder Parade sagt das Spiel an, wer das
   Gerät bekommt – so sieht der Torwart nicht, wohin der Schütze zielt.
4. **Schütze:** Tippe eine von **12 Zonen** im Tor an, in die du schießen willst.
5. **Torwart:** Tippe die Zone an, in die du hechtest.
6. **Die Szene läuft ab:** Aufbau → kurze Ruhe → Anlauf → Schuss → Parade.
   Tor oder gehalten?
7. Nach **5 Runden** (je Spieler 5 Schüsse) gewinnt, wer mehr Tore erzielt hat.
   Bei Gleichstand geht es ins **Sudden Death** (Verlängerung), bis eine
   Entscheidung fällt.

## 🥅 Trefferzonen & Wahrscheinlichkeiten

Das Tor ist in ein **4×3-Raster (12 Zonen)** unterteilt – für Schütze **und**
Torwart. Es zählt nicht nur die exakt richtige Zone:

- **Gleiche Zone** wie der Schuss → Torwart hält fast immer (~88 %).
- **Benachbarte Zone** → der Keeper hat trotzdem eine reelle Chance
  (~40 % Parade) – ein „knapp daneben" kann also noch gehalten werden.
- **Weit daneben gehechtet** → der Ball zappelt meist im Netz.

Dazu kommen Zufallsmomente für mehr Spannung und Realismus:

- **Pfosten** und **Drüber** bei riskanten Schüssen in die Ecken / nach oben,
- **Ausrutscher** des Schützen,
- **Patzer** des Torwarts,
- gelegentliche **Abpraller**, die doch noch reingehen.

Schüsse in die Ecken sind schwerer zu halten – aber auch riskanter (Pfosten/drüber).

## 👦 Spieler & Einstellungen

Standardmäßig treten an:

- **Fiete** – der blonde, kleinere Spieler,
- **Jonte** – der größere mit den langen braunen Haaren.

Über `EINSTELLUNGEN` auf dem Startbildschirm lassen sich **beide Namen ändern**.
Die Namen werden lokal im Browser gespeichert (`localStorage`) und bei jedem
Handoff, im Spielstand und auf dem Siegerbildschirm angezeigt.

## 🌍 Mannschaften

15 Nationalteams mit eigenen Trikots und Flaggen:

Deutschland · Brasilien · Argentinien · Frankreich · Italien · Spanien ·
England · Niederlande · Portugal · Japan · Mexiko · Kroatien · Belgien ·
Uruguay · Kolumbien

## ✨ Features

- **16-Bit-Pixeloptik:** schattierte Sprites, Stadion mit Publikum und Flutlicht,
  perspektivischer Rasen mit Strafraum, Tornetz, Konfetti.
- **Hochformat fürs Handy:** füllt den Bildschirm groß aus (deutlich größer als ein
  klassisches Mini-Spielfenster).
- **Lesbare Pixelschrift** (eigener 5×7-Zeichensatz inkl. Umlauten).
- **Entschleunigte Animation:** die Schussszene baut sich ruhig auf – erst Aufbau,
  dann Anlauf, dann Schuss – statt Hektik.
- **Soundeffekte** komplett per Web Audio API erzeugt (Pfiff, Schuss, Jubel,
  Parade, Publikum) – kein einziges Audio-File nötig.
- **Komplett offline & ohne Build:** eine `.html`-Datei, fertig.

## 🚀 Starten

Variante A – einfach öffnen:

```
pfostenkracher.html im Browser öffnen (Doppelklick)
```

Variante B – lokal servieren (z. B. fürs Handy im selben WLAN):

```bash
python3 -m http.server 8000
# dann im Browser: http://<deine-ip>:8000/pfostenkracher.html
```

> Tipp: Beim ersten Antippen aktiviert sich der Ton (Browser-Vorgabe für Audio).

## 🕹️ Steuerung

| Aktion | Eingabe |
| --- | --- |
| Auswählen / Bestätigen | Antippen (Touch) oder Klicken |
| Zielen / Hechten | Zone im Tor antippen |
| Namen ändern | `EINSTELLUNGEN` auf dem Startbildschirm |

## 🛠️ Technik

- Reines **HTML5 Canvas** + JavaScript, keine Frameworks, keine Build-Tools.
- Internes Render-Format **224 × 398 px** (Hochformat ≈ 9:16), pixelgenau auf die
  Bildschirmgröße hochskaliert.
- Grafik, Schrift, Flaggen und Sound werden **vollständig im Code generiert**.
- Eine Datei: `pfostenkracher.html`.

---

Viel Spaß – und nicht den Pfosten krachen lassen! 🥅💥
