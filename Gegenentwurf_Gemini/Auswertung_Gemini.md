# Gegenentwurf mit Gemini: Drei Design- & Grafik-Varianten je Geschäft

Stand: 2026-11-22 · Erstellt mit Gemini 4 Argon (High) und dem Subagenten `image-generator`.
Grundlage: Echte Betriebsdaten aus `Arbeitsdaten\Maps_Beispiele\betriebe.json`, Schriften aus WS-34, Leitlinien WS-43.

## Interaktive Vergleichs-Bühne im Browser

Die Vergleichsseite `Arbeitsdaten\Entwurfsvergleich\Gegenentwurf_Gemini\index.html` bietet vier Umschalter in der Kopfleiste:
1. **Geschäft wählen:** `Casa Fiorentina`, `Eiscafé Fontana`, `Karim Imbiss`.
2. **Vergleichsmodus:**
   - **Alle 3 Gemini-Varianten nebeneinander:** zeigt `Variante 1 (Buchdruck + Sekundärfarbe)`, `Variante 2 (Aquarell & Pastell)` und `Variante 3 (Retro-Siebdruck & Mid-Century-Pastell)` direkt nebeneinander.
   - **Claude (Entwurf D) vs. Gemini:** zeigt links Claudes bisherigen Entwurf D und rechts den neuen Gemini-Entwurf (auch im Kopf jeder Einzelseite zwischen Variante 1, 2 und 3 umschaltbar).
3. **Zeit-Test (Live-Simulator für den Öffnungszeiten-Zeitstrahl):**
   - `Jetzt (Live)` · `Geöffnet (Fr 14:30)` · `Feierabend (So 20:15)` · `Vor Öffnung (Fr 08:30)` · `Ruhetag (Mo 12:00)`.
4. **Bildschirmbreite:** `Handy (390 px)` oder `Computer (1280 px)`.

## Die drei Varianten je Geschäft

| Variante       | Grafik-Stil (`image-generator`)                                    | Farbkonzept (Hauptfarbe + Sekundärfarbe + Pastell-Flächen)                                                           | Charakter                                                     |
| -------------- | ------------------------------------------------------------------ | -------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------- |
| **Variante 1** | **Buchdruck / Linolschnitt** (`illustration.webp`)                 | Hauptfarbe aus WS-35 + harmonische Sekundärfarbe (Toskana-Salbei, Waffel-Terrakotta, Kräuter-Oliv), kantiger Rahmen   | Klassisch, handwerklich, wie eine gedruckte Speisekarte       |
| **Variante 2** | **Aquarell & feine Tuschezeichnung** (`illustration_v2.webp`)      | Weiche Pastell-Aquarellfarben auf warmem Naturpapier, abgerundete Karten (`10–12 px`), sanfte Pastell-Sekundärflächen | Freundlich, luftig, einladend, moderne Magazin-Illustration   |
| **Variante 3** | **Retro-Siebdruck / Mid-Century-Pastell** (`illustration_v3.webp`) | Dreifarbige Risographie-/Plakat-Ästhetik (z. B. Weinrot + Salbei + Toskana-Ocker; Tinte + Koralle + Pistazie)         | Kreativ, plakativer Blickfang, hoher Wiedererkennungswert     |

## Neue Marketing-Formulierungen für die Spezialitäten-Plaketten

Statt des technischen Satzes „Von Gästen in Google Maps genannt:“ nutzen die Varianten einladende, verkaufsstarke Überschriften:
- **Variante 1:** *„Die Casa Fiorentina wird besonders geschätzt für:“* / *„Das Eiscafé Fontana wird geschätzt für:“* / *„Karim Imbiss wird besonders geschätzt für:“*
- **Variante 2:** *„Bei unseren Gästen besonders beliebt:“* / *„Am Musterstädter Brunnenplatz beliebt für:“*
- **Variante 3:** *„Wofür Gäste die Casa Fiorentina schätzen:“* / *„Genuss am Brunnenplatz:“* / *„Hier kommen Gäste gerne für:“*

## Überarbeiteter, selbsterklärender Öffnungszeiten-Zeitstrahl

1. **Sofortige Angabe der nächsten Öffnung bei geschlossenem Laden:**
   - **Bei Ruhetag:** Badge `HEUTE RUHETAG` + *„Heute geschlossen · Öffnet wieder am Freitag um 09:00 Uhr (bis 19:00 Uhr).“* (Bei Ruhetag wird der Tages-Balken ausgeblendet, damit kein leerer Balken verwirrt.)
   - **Nach Ladenschluss (Feierabend):** Badge `FEIERABEND` + *„Heute bereits geschlossen (war bis 18:00 Uhr offen) · Öffnet wieder am Freitag um 09:00 Uhr.“* bzw. *„Öffnet wieder morgen (Montag) um 11:00 Uhr.“*
   - **Morgens vor Öffnung:** Badge `ÖFFNET HEUTE` + *„Gerade noch geschlossen · Öffnet heute um 09:00 Uhr (geöffnet bis 19:00 Uhr).“*
   - **Während der Öffnungszeit:** Grüner Sekundär-Badge `JETZT GEÖFFNET` + *„Heute noch bis 19:00 Uhr für Sie geöffnet“*.
2. **Eindeutiger Tages-Zeitstrahl (08:00 bis 22:00/24:00 Uhr) mit Beschriftung und Legende:**
   - Der geöffnete Zeitraum sitzt als farbiges Band auf der grauen geschlossenen Tagesleiste und trägt die Uhrzeit (`09:00 bis 19:00`) direkt im Farbbalken.
   - Darunter erklärt eine dreiteilige Mini-Legende jede Farbe: `[Grün/Blau] Geöffnete Zeit` · `[Grau] Geschlossen` · `[Roter Strich] Jetzt (Uhrzeit)`.
