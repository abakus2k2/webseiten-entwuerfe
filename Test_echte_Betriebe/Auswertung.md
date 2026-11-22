# Auswertung: Entwurf D an fünf echten Betrieben ohne eigene Webseite

Stand 2026-11-20. Grundlage: `Arbeitsdaten\Maps_Beispiele\betriebe.json` (Daten aus Google Maps, 2026-11-19), Herleitungsregel Konzept § 6.1, Farbfamilien WS-35, Schriften WS-34. Jede Seite hat ihre Herleitung als Kommentar in den Zeilen 1 und 2 der `index.html`. Alle Seiten sind Entwürfe mit erfundenem Angebotsblock (99 €, Löschdatum 18. Dezember 2026), keine Fotos (WS-31).

## Die fünf Seiten

| Betrieb | Familie | Schrift | Muster | Kopf | Herleitung |
|---|---|---|---|---|---|
| Asia Lotus | ziegel | Bricolage Grotesque | Kegelhüte | Akzentfläche | Küche (asiatisch); der Name Nguyen gibt nichts her |
| EISCAFÉ FONTANA | tinte | Fraunces | Brunnen | Grund | Name (Fontana = Brunnen), Wasser, Eis |
| Karim Imbiss | ziegel | Bricolage Grotesque | Fladenbrote mit Sesam | Akzentfläche | Döner als meistgenanntes Gericht |
| Restaurant Sofram | oliv_nacht (dunkel) | Literata | Karotuch und Teeglas | Grund | türkische Küche, Tischtuch, Tee |
| CASA FIORENTINA | weinrot | Fraunces | Lilienfliesen | Grund | Name (Florenz, Lilie), italienische Küche, Wein |

Ansicht: `http://localhost:8765/Test_echte_Betriebe/<ordner>/index.html` über die Konfiguration `entwurfsvergleich` in `.claude\launch.json`.

## Eigene Prüfung (Claude)

- Alle fünf Seiten laufen bei 375 px Breite ohne waagrechtes Scrollen.
- Sloplint: nur der Stempel meldet FAIL (gewollt) und der Weiß-Reflex (#fff) ist durch WS-35 abgedeckt.
- Ruhetag-Logik, Zeitleiste und „Jetzt geöffnet bis …" funktionieren mit den echten Zeiten, auch bei Casa (Freitag bis Sonntag zu).

## Befunde

1. **Starke Herleitungen tragen.** Fontana, Sofram, Casa und Karim ergeben schnell ein erkennbares Motiv. Das stützt die Herleitungsregel.
2. **Schwache Herleitung bei Asia Lotus.** Der Kegelhut ist ein Allerweltsmotiv, der Name liefert nichts. Bei solchen Betrieben bleibt die Seite „nett, aber austauschbar". Mögliche Antwort: bei fehlender Herleitung ein ruhiges, rein typografisches Muster statt eines erzwungenen Motivs.
3. **Kopfform bleibt bei zwei Varianten.** Die abgeleiteten Ideen für Kopfformen (Brunnenschale, Bogenfenster) widersprechen dem Konzept, das nur „Name auf Grund" und „Name auf Akzentfläche" zulässt. Beibehalten.
4. **Wasser gehört zur Familie tinte**, nicht salbei (Regelergänzung, Fontana).
5. **Dunkle Familie funktioniert** mit demselben CSS über die Tokens. Das spricht dafür, die dunkle Vorlage aufzunehmen (Entscheidung steht noch aus).
6. **Daten:** Für Asia Lotus und Karim fehlt die PLZ in `betriebe.json`. Das Sammelscript muss die PLZ immer mitnehmen.
7. **Lilien lesen sich wie Weingläser.** Passt zu einem Weinrot-Haus, war aber nicht beabsichtigt.
8. **Gerichte-Zeile** („Gäste nennen in Google Maps oft: …") nur bei Karim und Sofram (Themen mit mindestens 20 Nennungen). Offene Entscheidung gegenüber Leitlinie 3: Es ist belegt, aber es sind Stimmen Dritter. Vorschlag: nur mit Freigabe des Betriebs.
9. **Ruhetage** brauchen eigene Logik (Casa, Ingerwirt nur sonntags). Eingebaut.
10. **Zeitleiste** muss ihren Maßstab je Betrieb anpassen (Eiscafé saisonal und kurz, Gasthaus lang). Eingebaut (`--span`, `base`).

## Offen

- Zweitmeinung Codex: siehe Abschnitt unten.
- Entscheidungen für Andreas und Michael: dunkle Vorlage ja/nein, Gerichte-Zeile ja/nein, Verhalten bei schwacher Herleitung.
- Weitere Betriebe sammeln (Kissing, Dasing, Königsbrunn, Landkreis Musterstadt, Schlosserwirt).

## Zweitmeinung Codex

Bericht nach Delegation_Codex: Aufgabe: nur lesende Prüfung der fünf Seiten (Anforderungen, Zeitlogik, Muster, Herleitungen). Modell: `gpt-6.1-sol` im zweiten Versuch; der erste Versuch mit `gpt-6-astra` endete nach 20 Minuten ohne Ergebnis (Modell ausgelastet). Dauer zweiter Lauf: etwa 4 Minuten. Nachbesserungsrunden: keine. Token: unbekannt. Prüfung: Claude hat das Ergebnis gelesen und die Kernpunkte gegen Quelltext und Daten abgeglichen. Codex hatte keine Maps-Daten und hat nichts verändert.

**Von Claude bestätigt oder übernommen:**
1. Zeitlogik fehlerhaft: Status wird nach dem Laden nicht aktualisiert, nutzt die Zeitzone des Geräts statt Berlin, „gestern" rechnet mit 24 Stunden und ist bei Zeitumstellung falsch (25.10. und 30.03.).
2. Zeitleisten bei Asia Lotus und Karim: Die Beschriftungen in der Mitte (14 bzw. 16 Uhr) stehen nicht an der richtigen Stelle.
3. Kegelhüte bei Asia Lotus sind als Hüte kaum erkennbar (rund statt spitz). Deckt sich mit meinem Befund.
4. Alle Farb- und Textkontraste bestehen 4,5:1; nur der Jetzt-Strich auf dem Balken ist schwächer (Dekoration, Status steht zusätzlich im Text).
5. Platzhalter vor Versand: Kontakt-Adresse, Impressum und Datenschutz zeigen noch ins Leere.

**Mit Vorbehalt:** Die Aussagen „Gäste nennen …" und „92 Nennungen" kann Codex ohne Maps-Daten nicht prüfen; sie stammen aus `betriebe.json` und sind dort belegt, sollen aber nach der offenen Entscheidung zur Gerichte-Zeile behandelt werden. „Brunnenplatz mit Brunnen" (Fontana) stammt nicht aus den Maps-Daten, sondern aus eigener Ortskenntnis und steht nur im Herleitungskommentar. Die Zugangssperre „nur mit Ihrem Code" ist in der Vorschau nicht umgesetzt (Aufgabe der späteren Auslieferung).

**Umgesetzt am 2026-11-20:** Zeitlogik in der Vorlage korrigiert und die fünf Seiten neu erzeugt (alter Stand in `Arbeitsdaten\Entwurfsvergleich\_Archiv\Test_echte_Betriebe_20261120_1\`, SHA256 geprüft):
- Wochentag, Datum und Uhrzeit gelten immer für Berlin (`Intl.DateTimeFormat`, Zeitzone `Europe/Berlin`), egal wo das Gerät steht.
- Die Anzeige rechnet alle 30 Sekunden und beim Zurückkehren in den Tab neu (Status, Datum, Tageszeile, Zeitstrich).
- „Gestern" ist der Kalendertag davor, nicht 24 Stunden zurück.
- Die Skala der Zeitleiste steht zeitgenau über dem Balken (mittlere Beschriftung an ihrer echten Stelle).

Geprüft mit simuliertem Datum und Zeitzone (11 Fälle): Karim 11:30 Berlin aus New York „Jetzt geöffnet", Karim 21:29 und 21:31, Sofram 22:59 und 23:00, Casa Montag und Donnerstag „wieder offen am Freitag", „gestern" am 25.10. (24) und 30.03. (29). Alle richtig. Im Browser bei 375 px: Skala bei Karim stimmt mit dem Balken überein, kein waagrechtes Scrollen. Nicht geprüft: Feiertage und Sonderöffnungszeiten (dafür fehlen Daten).
