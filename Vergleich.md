# Entwurfsvergleich Vorschau-Seite Gastronomie (voller Ablauf)

Stand 2026-11-19. Alle Daten sind erfunden (Gasthaus Linde). Alle vier Entwürfe haben denselben Inhalt und dieselbe Abschnittsfolge nach Konzept § 3.1, keine Fotos (WS-31), eine Farbfamilie aus WS-35 und eine Schrift aus WS-34. Diese Fassung ersetzt den verkürzten Lauf vom 2026-11-18 (gesichert in `_Archiv\`).

**Ansehen:** Vorschau-Server „entwurfsvergleich“ starten (`.claude\launch.json`, Port 8765), dann `http://localhost:8765/A_hallmark/index.html`, entsprechend B, C, D. Die Seiten lesen die Uhrzeit des Aufrufs: „Jetzt geöffnet“ und der heutige Tag ändern sich mit ihr.

## Was gegenüber dem verkürzten Lauf anders ist
- **Echte Schriften:** Literata, Fraunces und Bricolage Grotesque liegen unter `fonts\` (variabel, mit OFL-Texten). Die Schriftwirkung ist jetzt beurteilbar.
- **Volle Abläufe:** Hallmark mit `sloplint --render`, Impeccable mit Richtungsvertrag, `detect`, Screenshots und Prüfer, Antialgorithm mit Seed, Zügen und Handarbeit an den Formen.
- **Eine Stilfamilie:** Auf deinen Wunsch sind alle vier traditionell. Weitere Stilfamilien (Asiatisch, gehoben, Imbiss) sind als offene Frage 5 in Konzept § 9 und in `_PROJEKT.md` eingetragen.
- **Vorschau statt Schema:** Alle Entwürfe wurden in Chrome gerendert und angesehen (390 und 1440 px).

## Die vier Entwürfe

| | A Hallmark | B Impeccable | C Antialgorithm | D Kombination |
|---|---|---|---|---|
| Idee | Aushang an der Tür | Speisekarte mit Doppelrahmen | Wirtshausschild mit Wendeschild | Abreißkalender, heutiges Blatt |
| Farbfamilie | ziegel | weinrot | oliv_nacht (dunkel, Gold) | ziegel |
| Schrift | Literata | Fraunces | Literata | Bricolage Grotesque |
| Jetzt-Zeile | Zeile im Aushang | Zeile zwischen zwei Linien | Wendeschild, dreht sich einmal beim Laden | Tageszahl, Jetzt-Zeile und Balken mit Strich für jetzt; gestriges Blatt fliegt einmal ab |
| Öffnungszeiten | Tabelle, heute hervorgehoben | Karte mit Punktlinie | Tafel, heute in Gold | Karte mit Punktlinie, heute hinterlegt |
| Muster (WS-31) | Ährenleiste | Blattleiste aus Lindenblättern | Wellen und Punkte | Abrisskante mit Lochung und Lindenblatt |
| Besonderes | geprüfter Stempel, Ausnahmen mit Grund | Blatt-Logo, Prüfer-Runde, DESIGN.md | Schild mit Kette, von Hand verfremdet | Bricolage wirkt am modernsten der vier |

## Messwerte (Chrome, heute gemessen)

| | A | B | C | D |
|---|---|---|---|---|
| Seitenlänge bei 390 px | 2806 | 2345 | 2555 | 2678 |
| Beide Hauptknöpfe enden bei (390 px, Bildschirm 780) | 444 | 502 | 647 | 713 |
| Waagerechtes Scrollen 390 / 1280 / 1920 | nein | nein | nein | nein |
| Kleinste Schrift | 15 px | 15 px | 15 px | 15 px |
| Knöpfe mindestens 48 px | ja | ja | ja | ja |

Die Links Impressum und Datenschutz im Fuß sind Textlinks von 18 bis 23 px Höhe, in allen vier gleich. Sie sind keine Knöpfe; ob die 48-px-Regel dort gelten soll, ist offen.

## Prüfergebnisse
- **sloplint (Hallmark):** A 0 FAIL, 2 Ausnahmen begründet. D 0 FAIL, 0 WARN, 16 Befunde begründet ausgenommen (reines Weiß aus der festen Familie, Desktop-Reflexe einer einspaltigen Vorschau). Das ist eine Entscheidung zu Gunsten von WS-35 und Konzept § 3.1, keine Ruhe im Reflex.
- **impeccable detect:** B, C und D ohne echte Gestaltungsbefunde. Die `design-system-*`-Befunde bei C und D vergleichen mit B, weil nur B ein DESIGN.md hat; sie sind Abweichungen vom anderen Entwurf, keine Fehler.
- **Prüfer:** B und D durch einen Prüfer im frischen Kontext. D: Urteil „fix“, umgesetzt wurden kürzere Verzögerung des Abreißeffekts (jetzt 0,1 s Verzug, 0,6 s Flug, damit die Jetzt-Zeile nicht lange verdeckt ist), Ausrichtung der Kartenzeilen an den Überschriften, gleiche Breite der Platzhalter. Offen bleiben die Platzhalterlinks (`maps.google.com/?cid=0`, `#`), die in allen Entwürfen Entwurfsstand sind.

## Stärken und Schwächen
- **A:** ruhig, sehr gut lesbar, kürzester Weg zu den Knöpfen (444 px). Wirkt am meisten wie ein ordentliches Dokument.
- **B:** wirkt am ehesten wie eine Gaststätten-Speisekarte, der Doppelrahmen und die Punktlinien tragen das Traditionelle gut. Etwas dekorativ; das Blatt ist selbstgezeichnet und muss je Betrieb zur Küche passen.
- **C:** das stärkste Bild (Schild), aber das größte Risiko: der Kopf ist ein Schild mit festem Namen „Linde“, und die Knöpfe rutschen auf 647 px. Der dunkle Grund passt zum Abend, eine tagsüber geöffnete Vorschau wirkt schwerer.
- **D:** die Tageszahl macht „heute“ zur Hauptsache und passt zur Idee „Kann ich jetzt kommen?“. Der Kopf trägt Name und Jetzt-Zeile in einem Element. Der Abreißeffekt ist nur einmalig und bei reduzierter Bewegung weg.

## Herleitung der Entwürfe

Nach der Regel in Konzept § 6.1; auch als Kommentar am Anfang jeder `index.html`.

| | Form | Muster | Farbe und Schrift |
|---|---|---|---|
| A | Aushang: Gasthaus hängt Zeiten an die Tür | Ähren: Gasthausküche, aus der Art des Hauses | ziegel wie Backstein, Literata wie Aushang |
| B | Speisekarte: Restaurant zeigt Karte | Lindenblätter: Name Linde | weinrot (Wein), Fraunces (gedruckte Karte) |
| C | Wirtshausschild: Name auf dem Schild, Wendeschild offen oder zu | Wellen und Punkte: nicht hergeleitet, Schmuckband (schwach) | oliv_nacht mit Gold: abends geöffnet, Schildgold; Literata |
| D | Abreißkalender: was heute gilt, Ruhetag Montag | Abrisskante mit Lochung und Lindenblatt: Kalender und Name | ziegel, Bricolage Grotesque (Plakat, Kalender) |

Alle Herleitungen stützen sich nur auf Name, Art des Hauses und Öffnungszeiten der erfundenen Daten. Bei C ist das Muster der schwache Punkt.

## Muster nachgebessert (Rückmeldung des Nutzers)
Die Muster in A (Linienraster) und D (Kalenderraster mit gefüllten Montagen) ergaben keinen Sinn. Sie sind jetzt Muster passend zum Haus: A eine Ährenleiste, D eine Abrisskante mit Lochung und einem Lindenblatt. Für die Vorlage gilt: Das Muster folgt dem Namen oder der Speisekarte des Betriebs, es ist kein beliebiges Ornament.

**Urteil des Nutzers:** B wirkt liebevoll und modern-traditionell und ist die Richtung für den Gasthaus-Ton. C ist der interessanteste Entwurf, passt aber eher in eine andere Stilfamilie (zum Beispiel mexikanisch oder lateinamerikanisch), nicht in die traditionelle.

## Offen und ehrlich benannt
- **Entscheidungsrunde Impeccable:** im Chat geklärt (Nutzer „beide gleich“, Erfolg „Ja-Mail“, Falsch „Agenturglanz, Baukasten“), nicht über das Werkzeug.
- **Prüfer und Dokumentierer:** liefen als allgemeine Unter-Agenten, weil der mitgelieferte Prüfer-Agent fehlt (Rolle aus `degraded\finish-reviewer.md`). Für B steht ein DESIGN.md im Projektstamm, für D keines.
- **Antialgorithm `check.py`:** lief nicht (kein cairosvg oder rsvg-convert, ohne Erlaubnis nichts installiert). Die Formen wurden in Chrome gerendert und von Hand angesehen.
- **Seeds:** bei C nur teilweise übernommen, bei D nicht (Drohnenfoto, Fluoreszenz, Schreibschrift passen nicht zur traditionellen Familie).
- **Schriften:** A und C beide Literata, damit ist der Unterschied dort Farbe und Form, nicht Schrift.
- **Einzelläufe:** jeder Entwurf ist ein einzelner Lauf.

## Empfehlung
1. Für die Branche Traditionell: B als Richtung (so auch vom Nutzer gewünscht). D bleibt die Alternative, wenn „offen jetzt?“ im Mittelpunkt stehen soll. C gehört als Beispiel in eine andere Stilfamilie.
2. In die Vorlage übernehmen: Bandknopf und alle Knöpfe mindestens 48 px, Zeiten mit „bis“, Jetzt-Zeile aus der Uhrzeit, die Seite schaltet Bewegung bei reduzierter Bewegung ab.
3. Vor mehr Branchen: Stilfamilien klären (Konzept § 9, Punkt 5).
