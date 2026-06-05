# Claude-Code-Prompt: Reise-Website umbauen

> Kopiere alles unterhalb der Trennlinie in Claude Code (im Repo der Seite `reise-plan.vercel.app`).

---

## Aufgabe

Diese Website ist aktuell ein **Revolut-Plan-Vergleich**. Baue sie komplett zu einem **persönlichen Reiseplaner** für unsere Thailand-Reise um. **Alle Revolut-Inhalte fliegen raus.**

Zuerst: Inspiziere die Repo-Struktur (Framework, Komponenten, Styling, wo Texte/Daten liegen). Behalte den **Tech-Stack, das Design-System und die Optik bei** (heller Apple-Look, Sektions-Navigation, sanfte Cards, Countdown-Hero, deutsche Sprache). Nur Inhalt und Struktur ändern sich.

### Entfernen (vollständig)
- Alle Revolut-Plan-Komponenten: Plan-Karten (Standard/Premium/Metal), Vergleichstabelle, Live-Konfigurator, Revolut-spezifischer Aktionsplan und Revolut-Hinweise (FX-Gebühren, ATM-Limits, Einlagensicherung, Gemeinschaftskonto-Streit etc.).
- Alle Texte, Meta-Tags, Titel und Assets, die Revolut/Versicherungs-Plan-Vergleich erwähnen.
- Navigation-Anker, die auf gelöschte Sektionen zeigen.

### Beibehalten / Wiederverwenden
- **Countdown-Hero**: „Frankfurt → Bangkok", Abflug **5. August 2026, 12:10 Uhr**. Layout & Animation behalten.
- **Interaktive Checkliste mit localStorage-Persistenz** (Fortschritt bleibt nach Schließen erhalten) → für die neue Pack- & Admin-Checkliste wiederverwenden.
- Sektions-Navigation oben → neue Anker.

### Meta / SEO aktualisieren
- Title: `Thailand 2026 · Unser Reiseplan`
- Description: Reiseplan Thailand August 2026 – Route, Kosten, Anbieter, Checkliste.
- `apple-mobile-web-app-title`: `Reiseplan`

---

## Neue Seitenstruktur (Sektionen in dieser Reihenfolge)

### 1. Hero + Countdown (behalten, Texte anpassen)
Titel z.B. „Unsere Thailand-Reise." · Untertitel: Route, Kosten und alles Wichtige an einem Ort. · Countdown bleibt (Abflug 5.8.2026, 12:10).

### 2. Reiseroute / Ziele
Vier Etappen als Cards mit Nächten, ca.-Datum und 1 Satz Beschreibung. Optional kleine Timeline/Verbindung dazwischen.

| Etappe | Zeitraum (ca.) | Nächte | Kurzbeschreibung |
|---|---|---|---|
| **Bangkok** (Riverside) | 06.–09.08 | 3 | Tempel (Wat Arun, Wat Pho, Grand Palace), Märkte, Stadtleben. Mietwagen vor Ort. |
| **Ko Pha Ngan** (Salad Beach) | ca. 09.–15.08 | 6 | Ruhige Strände, Schnorcheln, Roller, Inselgefühl. |
| **Krabi / Ao Nang** | ca. 15.–22.08 | 7 | Inselhopping, Railay, Kalksteinfelsen, Strände. |
| **Phuket** | ca. 22.–25.08 | 3 | Strandtage, letzte Stopps, Abreise ab Phuket. |

Rückflug ab Phuket nach Frankfurt.

### 3. Detaillierte Kostentabelle
Saubere Tabelle (zu zweit, ~20 Tage). Summen hervorheben. Optional kleine Donut-/Balken-Visualisierung der Anteile.

| Posten | Details | Kosten |
|---|---|---|
| Unterkunft gesamt | Bangkok 130 € (3 N) + Ko Pha Ngan + Krabi + Phuket | 1.000 € |
| Mietwagen Bangkok | | 66 € |
| Flug Suvarnabhumi → Surat Thani | | 100 € |
| Surat Thani → Ko Pha Ngan | Bus + Fähre | 50 € |
| Ko Pha Ngan → Krabi/Ao Nang | Bus + Fähre, ~8 h | 45 € |
| Krabi → Phuket | Minivan, ~3–4 h | 25 € |
| Transfers + Grab/Taxi | Phuket-Flughafen, lokale Fahrten | 60 € |
| Essen & Trinken | ~27,5 € × 2 × ~20 Tage | 1.100 € |
| Roller | ~200 THB/Tag + Sprit | 80 € |
| Bootstouren / Inselhopping | 2–3 Touren | 200 € |
| Tauchen / Schnorcheln | Schnuppertag | 200 € |
| Tempel / Sightseeing | Grand Palace, Wat Pho, Wat Arun | 50 € |
| eSIM, Puffer, Kleinkram | | 180 € |
| **Zwischensumme** | | **~3.156 €** |
| **+ Puffer (~10 %)** | | **~316 €** |
| **= Noch offen** | | **~3.470 €** |

**Bereits bezahlt** (separat ausweisen, nicht in „noch offen" einrechnen):
- Flüge FRA → Bangkok + Phuket → FRA: **800 €/Person** 
- Auslandskrankenversicherung EUROPA ERK: 24 €
- Bangkok: **Royal Princess Larn Luang - SHA Extra Plus**, city-view — buchen über [Booking.com](https://www.booking.com)

### 4. Anbieter-Liste (Transport, Unterkunft, Touren) mit Links
Gruppiert in Cards. Links als Buttons, in neuem Tab öffnen.

**Unterkunft**
- Ko Pha Ngan: **Bougain Villas Salad Beach** (⭐4.9) — direkt per WhatsApp buchen (6-Nächte-Rabatt anfragen)
- Krabi/Ao Nang & Phuket: flexibel, kurzfristig über [Agoda](https://www.agoda.com)

**Transport**
- Flug Suvarnabhumi → Surat Thani: AirAsia / Nok Air / Thai Lion Air (vergleichen)
- Bus + Fähre (Surat Thani↔Ko Pha Ngan, Ko Pha Ngan↔Krabi, Krabi↔Phuket): [12Go](https://12go.asia) oder lokale Agenturen
- Mietwagen Bangkok: vor Ort / online buchen: [skyscanner](https://skyscanner.de/carhire/)
- Lokal: Grab-App (Taxi/Ride-Hailing)

**Touren & Aktivitäten**
- Krabi 4-Inseln-Tour, Phi-Phi-Tagestour: lokale Agenturen in Ao Nang oder [Viator](https://www.viator.com) / [GetYourGuide](https://www.getyourguide.com)
- Roller-Verleih: vor Ort (~200 THB/Tag)
- Tauchen/Schnorcheln: lokale Dive-Center auf Ko Pha Ngan / Ao Nang

**SIM / Internet**
- eSIM vorab: [Airalo](https://www.airalo.com)

### 5. Pack- & Admin-Checkliste (interaktiv, localStorage)
Wie die alte Checkliste: abhakbar, Fortschritt gespeichert, Fortschrittsanzeige „X von Y erledigt". Zwei Gruppen:

**Admin / Vor der Reise**
- [ ] TDAC digitale Einreisekarte ausfüllen — innerhalb **72 h vor Ankunft** (tdac.immigration.go.th)
- [ ] EUROPA Notfall-Hotline-Nummer speichern — **vor jeder Behandlung anrufen** (Repatriierung vorab freigeben)
- [ ] EUROPA-Police kündigen — innerhalb der 1-Monats-Frist (nur für diese Reise)
- [ ] Revolut Geld umtauschen in Thai Baht und vor Ort umtauschen
- [ ] Internationalen Führerschein dabei (Mietwagen + Roller)
- [ ] Reisepass: min. 6 Monate gültig + Kopien
- [ ] Bargeld 600–1.000 € (max. 2.000 €); THB-Abhebungen werktags über Krungsri/AEON, immer **THB** wählen (kein DCC), auf beide Karten splitten
- [ ] eSIM organisieren

**Packen** (August = feucht-heiß, Regenschauer möglich)
- [ ] Leichte Kleidung + Regenjacke/Poncho
- [ ] Badesachen, Flip-Flops + feste Sandalen
- [ ] Schulterbedeckende Kleidung für Tempel
- [ ] Sonnencreme + After-Sun + Mückenspray (DEET)
- [ ] Reiseapotheke (Durchfallmittel, Elektrolyte, Pflaster)
- [ ] Universaladapter + Powerbank
- [ ] Wasserdichte Handytasche / Dry Bag
- [ ] Kopien wichtiger Dokumente + Versicherungsunterlagen

---

## Technische Hinweise
- Bestehenden Stack & Styling weiterverwenden, nur Inhalt/Komponenten austauschen.
- Responsive (Mobile-First) und Dark/Light wie bisher.
- localStorage für die Checkliste behalten/wiederverwenden.
- Tote Imports, ungenutzte Revolut-Komponenten und -Assets entfernen.
- Navigation-Anker an neue Sektionen anpassen.
- Footer-Disclaimer anpassen: kein Revolut/Versicherungs-Hinweis mehr, stattdessen kurzer Hinweis „Alle Preise & Zeiten sind Schätzungen, Stand der Planung".
- Am Ende: Build prüfen, dann committen.
