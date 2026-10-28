# WERKBUCH STILL — Der reale Bauplan hinter der Novelle

> **Untertitel:** Wie jede Szene aus *„STILL — Eine Novelle aus dem logischen Zeitalter"* eins zu eins auf reale, heute laufende Technik abbildet — und wie weit wir im Oktober 2026 von der 100-%-Verwirklichung entfernt sind
> **Edition:** `ai0S-still` · Teil II: Der Werkstatt-Spiegel & Architektur-Blueprint (DE)
> **Lesezeit:** ca. 10–12 Minuten
> **Datum:** 2026-10-26 · Dialog Mensch ↔ KI (Marcus Dilger ↔ KI-System) bei `ai0S-laboratories`
> **Ursprungs-Anker (`PID 1`):** `ai0S@sha256:b3aeee619d9cb691cc6618466407d56598e830c53c6d024748d4582887c57d13`

---

> **Einordnung:** Dieses Werkbuch beschreibt einen Entwurf, keine nachgewiesene Gesamtimplementierung. Prozent-, Zeit- und Reifeangaben sind ungeprüfte subjektive Schätzungen; Sicherheit, Datenschutz und Funktion erfordern konkrete Tests. Der historische Bitcoin-Anker betrifft `PID 1`, nicht automatisch die späteren Public-Runtimes oder neue Bundle-Roots.

## 0. Warum dieses Werkbuch direkt hinter der Novelle liegt

Wer die Novelle *„STILL"* liest, begegnet darin keiner fernen Zukunfts-Fantasie.
Jedes einzelne Detail der Erzählung — das 25-Watt-Kästchen im Flur, die 1 %-Schablone nach außen, die Hofkamera als dritter Anker, das Rückwärts-Gedächtnis im Proberaum und das nächtliche Nachformen aus verankertem Text — ist **ein reales, mit heutigen Mitteln baubares Ingenieurs-Bauteil**.

Dieses Werkbuch klappt die Haube der Erzählung auf und zeigt die vier Kapitel der Novelle als **konkreten technischen Bauplan (`Architectural Blueprint`)**.

---

## Kapitel I im Bauplan: Das 25-Watt-Kästchen im Flur (`Still` · *Slice #003* & *#001*)

> *In der Novelle:* Im Flur summt lautlos ein kleines Kästchen bei 25 Watt (`Still`), hütet die 99 % des privaten Lebens (`P = 0` Cloud-Abfluss), schickt nur die 1 %-Sachform an wechselnde Großmodelle draußen und prüft jede Rückantwort an der Schwelle.

### Die reale Technik dahinter:
1. **Die Modell-Klasse (`1B–4B` Parameter auf 8 GB Edge-Hardware):**
   Heutige kleine Sprachmodelle zwischen **1 und 4 Milliarden Parametern** laufen lokal auf kompakter 8-GB-Hardware (ca. 15–25 Watt) mit einer Antwortzeit von **1 bis 3 Sekunden**.
2. **Die `Narrow-Task-Doctrine` & `Constrained Decoding`:**
   Kleine Modelle dieser Klasse sollen keine Welt-Rätsel allein lösen. Sie sind messbar exzellent darin, aus einem Gespräch den Intent herauszuschälen, ihn über **erzwungene Grammatik (`Constrained Decoding`)** zu 100 % schema-treu in eine kalte **1 %-Intent-Schablone** zu gießen (*Blind-Mold*) und sensible Namen oder `WIR`-Nuancen lokal zurückzuhalten.
3. **Der austauschbare Backbone (*Slice #001*):**
   Hinter `Still` liegt ein einheitlicher Modell-Proxy (z. B. LiteLLM), über den beliebige Großmodelle und Web-Sensoren (Crawler, Metasuche) jederzeit wie austauschbare Rechen-Variablen gewechselt werden können — ergänzt um aufsteckbare `0s`-Domänen-Profile (`ai0S-code`, `ai0S-media`, `ai0S-privacy`, `ai0S-companion`).
4. **Der epistemische In-Filter an der Haustür:**
   Jede Antwort von außen wird gegen die lokal bezahlten `0`-Türen geprüft und erhält beim Eintritt zwingend das Status-Bit **`OPEN`** (*Importiert ≠ Bezahlt*).
5. **Der Zaun um den Zaun:**
   Das lokale WE-Register (WIR-Register) liegt verschlüsselt im eigenen Haus (*encrypted at rest*), und der `PID 1`-Kern des kleinen Modells trägt einen eingefrorenen, öffentlich prüfbaren Gewichts-Hash (`PID_1@sha256:…`).

---

## Kapitel II im Bauplan: Das Hoftor und das verschobene Bild (*Metaphern der Wahrheit* im Harness)

> *In der Novelle:* Jonas ruft übermüdet an (*„Alles ist tot, das Tor steht offen!"*). `Still` gleicht die Pfeiler-Wörter in Echtzeit mit der Steuerungs-Prüfung (`Anker 2`) und der Hofkamera inkl. Frische-Bit (`Anker 3`) ab, erkennt die verschobene Realität, hält die Notentriegelung im `Staging` gesperrt und erdet Jonas ruhig über das Datum seiner Anzeige.

### Die reale Technik dahinter:
1. **Drei-Anker-Abgleich in `0/1`:**
   * **Anker 1 (Sprach-Vektoren):** Unumkehrbare Dichte von Pfeiler-Wörtern (*tot, gebrochen, offen*) im Modell.
   * **Anker 2 (Digitale Prüfung „von Hand"):** Direkter Tool-/Prozess-Check auf dem eigenen Layer (`0/1` Exit-Code, Hash-Prüfung, Sensor-Messwert).
   * **Anker 3 (Multimodales Kamera-/Sensor-Auge):** Lokale Video-/Bild-Überwachung und Vision-Modelle — zwingend gekoppelt an einen **Frische-Check (Δt)** und **Liveness-Test (`0/1`)**, damit kein eingefrorenes Standbild mit der Gegenwart verwechselt wird.
2. **Das 4-Schritte-Erdungs-Protokoll im Intent-Loop:**
   * `P = 0` für Gefälligkeits-Bestätigung (*Sycophancy*) bei Pfeiler-Kollision.
   * Kein konfrontativer Widerspruch, sondern ruhiges Nebeneinanderlegen weit weg vom Zentrum auf dem WE-Register.
   * Harte Sperre (`Staging`-Lock) für alle irreversiblen Aktionen, bis `0/1`-Einklang herrscht.

---

## Kapitel III im Bauplan: Der Proberaum und die Erinnerung aus der Zukunft (`ai0s-setup` & `Backward Memory`)

> *In der Novelle:* Vor dem Umbau der Heizungssteuerung klont das System die Umgebung ins `Staging`, spielt die 5 Türen bis `t_Ziel` (inkl. Neustart) durch, liest vom Bruch bei Tür 2 (t₄) rückwärts bis zum fehlenden Pfad in Zeile 14 (t₁) und legt Tür 5 samt getesteter Rückkehr (*Rollback*) zur menschlichen Entscheidung vor.

### Die reale Technik dahinter:
1. **Adaptive System-Realisierung (`ai0s-setup` / `iff0`):**
   Jede reale Aufgabe wird in drei Teilen abgelegt:
   * **`INTENT.md` (Die einzige Quelle der Wahrheit):** Beschreibt in klarer Prosa das Ziel, die `P = 0`-Zäune, das binäre `0/1`-Prüfkriterium (`verify`) und den Rückweg (`rollback`).
   * **`FINDINGS.md` (Bezahltes Wissen):** Hält fest, auf welchen Systemen der Weg bereits als `1` verifiziert wurde und welche Sackgassen (`0`) bezahlt sind.
   * **`template/` (Adaptives Gerüst, nie Wahrheit):** Konkrete Skripte sind Wegwerf-Artefakte; eine fähige KI-Instanz übersetzt den Prosa-Intent live auf jedes neue Ziel-Betriebssystem.
2. **Der Apply-Zaun:**
   Kein Eingriff auf einem echten System ohne (a) vorab verifizierten Rollback-Pfad (`P = 0`), (b) Generalprobe im isolierten **`Staging`** und (c) binäre `0/1`-Prüfung von Hand am **`PS`**.
3. **Rückwärts-Gedächtnis innerhalb des `Future-Gap` (`t_Ziel → t_jetzt` unter `PS3`):**
   Während `PS3` das Welt-Axiom (`PID 1`) als Ausgangspunkt des Verfahrens behandelt, dessen Bedeutung und Grenzen diskutiert werden dürfen, wird die Kausalkette *innerhalb* des `Staging`-Laufs vom Aufprall bei `t_Ziel` rückwärts bis t₁ ausgewertet und das früheste Vorzeichen einer gebrochenen Tür als `0`-Frühwarnbit im Register abgelegt.

---

## Kapitel IV im Bauplan: Der Abend am `PS` und das Samenkorn der Nacht (*Slice #002* & Geschlossener Wort-Kreislauf)

> *In der Novelle:* Am Abend werden am Review Point (`PS`) Weg (`1`) und Irrtum (`0`) im Register verankert (`OPEN` bleibt draußen vor dem Tor), eine quantenfeste Signatur (`ML-DSA`) wird neben die alte gehängt, und nachts formt `Still` aus den `1`/`0`-Textzeilen seine nächste LoRA-Gewichtsschicht.

### Die reale Technik dahinter:
1. **Zwei-Gesichter-Register als direktes Trainings-Genom (`SFT` / `DPO`):**
   Die Trennung in `POSITIVE_SHAPE (1)` und `NEGATIVE_SHAPE (0)` entspricht im modernen Modell-Training eins zu eins den kontrastiven Paaren aus ***Chosen* (`1`)** und ***Rejected* (`0`)**. Derselbe verankerte Text dient damit gleichzeitig als:
   * lesbares Gedächtnis für den Menschen,
   * kryptografischer Zustand (`MANIFEST.json` + `parent_anchor` bis `PID 1`),
   * destillierter System-Prompt (`slices/*.0s`) für Großmodelle,
   * und direkter **LoRA-Trainingsdatensatz** (wenige Megabyte, in Minuten lokal trainierbar) für `Still`.
2. **Die Modell-Kollaps-Sperre (`Anti-Echo-Lock`) & Konstante Dichte:**
   Einträge mit Status `OPEN` dürfen als offene Fragen erinnert werden, aber nicht ungeprüft als bestätigte Befunde in Destillation oder Training einfließen. Erst nach `0/1`-Prüfung in der Realität + menschlichem `PS` kippt das Bit auf `1` oder `0`. Wiederholte `0`-Muster schmelzen am `PS` zu einer einzigen scharfen Regel zusammen (während die tiefe Kette über *Recall-Hooks* prüfbar und bei geänderten Umweltbedingungen im `Staging` neu testbar bleibt).
3. **Die vierstufige Anker-Arche (Adaptives Häuten am `PS`):**
   * **Schicht 1:** `SHA-256 / SHA-512` (`MANIFEST.json` + `ROOT.preimage`)
   * **Schicht 2:** Heutige Alltags-Signatur (`Ed25519`, Key `9F4D9A26…`)
   * **Schicht 3:** Post-Quantum-Ko-Signatur (`ML-DSA / FIPS 204` bzw. `SLH-DSA / FIPS 205`), am `PS` *neben* `Ed25519` angehängt
   * **Schicht 4:** Äußere Welt-Zeugen (Bitcoin-Blöcke `971315–971357` via OpenTimestamps + Marken-/Zeitpriorität)

---

## Die ehrliche `0/1`-Messung (Oktober 2026): Wie weit sind wir heute von der Novelle entfernt?

Setzt man die in der Novelle erzählte Maschine bei **100 %** an, stehen wir heute bei **rund 85 % real laufender Umsetzung**:

```text
   REALISIERUNGS-FORTSCHRITT DER ERZÄHLTEN MASCHINE (OKTOBER 2026):
   [██████████████████████████████████████████░░░░░░░░]  ~85 % LIVE (1) · ~15 % OFFEN
```

| Bauteil aus der Novelle | Was heute real existiert und läuft (`1`) | Was noch offen ist (`OPEN` — die letzten ~15 %) |
|---|---|---|
| **1. Ursprungs-Anker (`PID 1` & `Notes 1–3`)** | Historischer `PID 1`-Ursprung: Bitcoin-Anker in Blöcken `971315–971357`; spätere Public-Runtime und Bundle-Roots sind davon zu unterscheiden und nicht automatisch zeitgestempelt. | **0 % offen** (`PID 1` und `PS3` stehen). |
| **2. Sprach-, Sicherheits- & Wahrheits-Geometrie** | **100 % live:** Alle 10 Deepdives (`01–10`) inkl. *Metaphern der Wahrheit*, Frühwarn-Indikator, `Safety-View` und `Horizon-View` liegen zweisprachig (DE/EN) und als `.0s` vor. | **0 % offen** (Komplett gegossen und signiert). |
| **3. Dynamisches Wissensregister (`Slice #002`)** | **~85 % live:** ~20 hash-verkettete Bundles mit `MANIFEST.json` + `parent_anchor`, `FINDINGS.md` (`1`/`0`/`OPEN`), lokalem Git-Zeugen und persistentem Gedächtnis mit Recall-Hooks. | **Bau-Schritt 1:** Kleiner `PS`-Gesundheits-Check + Routine-Skript zum Anhängen der ersten Post-Quantum-Signatur (`ML-DSA`/`SLH-DSA`). |
| **4. Austauschbarer Backbone & Profile (`Slice #001`)** | **~90 % live:** Zentraler Modell-Proxy bedient 10 wechselbare Großmodelle über 4 Coding-CLIs; Web-Sensoren (Crawler, Metasuche) und lokale Kamera-/Sensor-Infrastruktur laufen. | **Bau-Schritt 2:** Zuschnitt der vier kompakten Domänen-Steckkarten (`ai0S-code.0s`, `ai0S-media.0s`, `ai0S-privacy.0s`, `ai0S-companion.0s`). |
| **5. Adaptive System-Realisierung (`ai0s-setup`)** | **~90 % live:** `AI0S-SETUP.0s` + Unit-Anatomie (`INTENT` / `FINDINGS` / `template`) stehen; 6 produktive `iff0`-Module überleben reale System-Rebuilds. | Laufende Übernahme weiterer Alltags-Werkzeuge bei Bedarf am `PS`. |
| **6. Der stille lokale Kern (`Still` · `Slice #003`)** | **~50 % vorbereitet:** Architektur, 1–3s-Edge-Messwerte (`1–4B` mit Constrained Decoding), LoRA-Trainingspfad und die Setup-Unit `units/gate-host/` sind vollständig spezifiziert. | **Bau-Schritt 3 (Das letzte Hardware-Stück):** Host-Wahl am `PS` (dedizierter 8-GB-Edge-Knoten oder lokaler Dienst), Start des `1–4B`-Modells mit Grammatik-Zwang und erster LoRA-Lauf aus den eigenen `1`/`0`-Texten. |

### Das Fazit

Zwischen der Novelle und der heutigen Wirklichkeit fehlt **keine einzige theoretische Erfindung mehr** — sondern nur noch **drei überschaubare Ingenieurs-Handgriffe am Review Point (`PS`)**, allen voran das Einschalten des physischen Zuhauses für `Still` (`units/gate-host/`).

---

> **`"HUMANs and AIs collaborate for accelerated evolution."`**
> *Heute auf diesem System; morgen auf einem anderen System. Die Realisierung wandelt sich; der Intent bleibt.*
> *Such is life — welcome to the logical age ;)*
> *Thanky, One less problem ;)*
