# Outline v2: Finanzielle Risiken durch Vendor Lock-in bei DevOps-SaaS-Plattformen

## Metainformationen

**Forschungsfrage:** „Welche finanziellen Risiken entstehen durch Vendor Lock-in bei DevOps-SaaS-Plattformen und wie lassen sich diese für Investitionsentscheidungen quantifizieren?"

**Format:** Transfer-Dokument-Report (TDR), 5 Seiten à 210 Wörter = 1.050 Wörter

**Untersuchungsobjekte:** GitHub Team, GitLab Premium (reduziert von ursprünglich drei Plattformen)

**Betrachtungszeitraum:** 5 Jahre (als Annahme für mittelfristige Bindungsdauer gekennzeichnet)

---

## Kapitel 1: Einleitung (200 Wörter)

### Problemstellung und Forschungsfrage

**Argumentationskette:**

1. DevOps-Plattformen als zentrale Infrastruktur etabliert
   - Forsgren/Humble/Kim (2018): Accelerate, S. 3-15
     - Korrelation zwischen DevOps-Adoption und Unternehmensperformance
   - CNCF (2023): Annual Survey
     - Verbreitung von Container/CI-CD in Produktion
     - **QUELLENSTATUS:** Survey-Daten, als Industriestandard akzeptabel für Marktdaten

1. Plattformwahl bindet langfristig durch technische und organisatorische Abhängigkeiten; "Switching costs are the norm in information industries" (Shapiro/Varian 1999, S. 133)
   - Repository-Historie, CI/CD-Konfigurationen, Team-Know-how


3. Forschungslücke: Fehlende Quantifizierungsmodelle für finanzielle Lock-in-Risiken bei DevOps-SaaS
   - Bestehende Literatur fokussiert auf Cloud-IaaS (451 Research 2021) oder qualitative Dimensionen
   - **NEU IDENTIFIZIERTE SCHWACHSTELLE:** Behauptung der Forschungslücke müsste durch systematische Literaturrecherche belegt werden; im TDR-Format nicht leistbar → als Arbeitshypothese kennzeichnen

4. Forschungsfrage (ergebnisoffen formuliert)

5. Zielsetzung: Entwicklung einer Bewertungsmethode durch Kombination von Exit-Kosten und Preisvolatilität

6. Abgrenzung:
   - Fokus: Finanzielle Risikokomponenten (einmalige Wechselkosten + kumulative Preisrisiken)
   - Einbezogen: Alle einmaligen Kosten der Transition (Quell- und Zielplattform), inkl. Parallelbetriebs-, Setup- und Unterstützungskosten
   - Ausschluss:
     - Technische Migrationsdetails (Implementierungsanleitungen, Code-Beispiele)
     - Change-Management (organisatorische Widerstände, Kommunikation)
     - Projektmanagement- und Entscheidungskosten
     - Self-Hosted-Varianten
     - Laufende Kosten und Nutzen nach Abschluss der Migration (Produktivitätsgewinne, Feature-Unterschiede, reguläre Lizenzkosten der neuen Plattform)
   - Scope: SaaS-Varianten, Betrachtungszeitraum 5 Jahre
     - **TRANSPARENZ:** 5-Jahres-Zeitraum als Annahme für mittelfristige Plattformbindung, nicht empirisch belegt
   - **HINWEIS:** Die Terminologie "Exit-Kosten" wird im Folgenden synonym mit "einmalige Wechselkosten" verwendet, umfasst aber auch Entry-Kosten der Zielplattform während der Transition

---

## Kapitel 2: Theoretische Grundlagen (250 Wörter)

### 2.1 Vendor Lock-in und Wechselkosten (150 Wörter)

**Argumentationskette:**

1. Definition Vendor Lock-in aus Konsumentenperspektive
   - Shapiro/Varian (1998): Information Rules, Kap. 5, S. 116-129
     - Lock-in entsteht durch Wechselkosten, die Anbieterwechsel ökonomisch unattraktiv machen
     - Allgemeine Typologie der Wechselkostenquellen nach Shapiro/Varian:
       1. Vertragsbindung
       2. Marken-/Systemspezifisches Training → Ausbildungskosten
       3. Informations- und Datenbankformate → Migrationskosten
       4. Suchkosten → Kosten aus Prüfung und Auswahl neuer Anbieter
       5. Verlorene Loyalitätsprogramme → Kosten aus weggefallenen Ermäßigungen
     - **QUELLENSTATUS:** Standardwerk (1998, vor SaaS-Ära), Übertragbarkeit auf moderne Kontexte zu argumentieren

2. Übertragung auf DevOps-SaaS-Kontext (analytische Eigenleistung)
   - **Relevante Kategorien:**
     - Ausbildungskosten → Team-Requalifizierung auf neue Plattform (Einarbeitung in neue CI/CD-Syntax, neue UI, neue Workflows)
     - Migrationskosten → Repository-Migration, Pipeline-Konvertierung, Datenexport/-import
   - **Ausgeschlossene Kategorien mit Begründung:**
     - Vertragsbindung → Nicht DevOps-SaaS-spezifisch; kundenspezifisch
     - Loyalitätsprogramme → Enterprise-Rabatte sind Verhandlungssache und vertraglich geregelt
     - Suchkosten → Nicht plattformspezifisch quantifizierbar, inkludieren nach Shapiro/Varian (1999) außerdem psychologische Kosten durch Änderung von Gewohnheiten -Quantifizierbarkeit nicht gegeben, besonders nicht im Unfang dieser Arbeit-, Zeit und Aufwand zur Identifizierung eines neuen Anbieters und das mit der Auswahl eines unbekannten Anbieters verbundene Risiko - Quantifizierbarkeit auch hier nicht gegeben -; Zeit und Aufwand zur Identifizierung eines neuen Anbieters fallen unter primär unter ausgeschlossene Projektmanagement- und Entscheidungskosten
   - **TRANSPARENZ:** Diese Selektion und Operationalisierung ist analytische Eigenleistung der Arbeit

3. Ökonomische Konsequenz: Asymmetrische Verhandlungsposition
   - Zhu/Zhou (2012): Migration to Open-Source Systems, S. 1288-1290
     - Unterscheidung zwischen vorausschauenden und kurzsichtigen Kunden (forward-looking vs. myopic)
     - Kurzsichtige Kunden antizipieren Wechselkosten nicht vollständig bei Erstentscheidung
     - Schlussfolgerung: Lock-in ermöglicht Anbietern Preiserhöhungen, da kurzsichtige Kunden bei steigenden Preisen nicht wechseln, solange Preisdifferenz < Wechselkosten
   - **EINSCHRÄNKUNG:** Zhu/Zhou analysieren OSS vs. Proprietary, nicht SaaS-Subscriptions; Übertragung konzeptionell plausibel, aber nicht direkt empirisch validiert
   - **IMPLIKATION FÜR DIESE ARBEIT:** Das Quantifizierungsmodell richtet sich implizit an vorausschauende Entscheidungsträger, die Lock-in-Risiken bei Plattformwahl berücksichtigen wollen

4. Plausibilisierung der Mechanismen für GitHub/GitLab
   - Beide Plattformen weisen die relevanten Wechselkostentypen auf:
     - **Ausbildungskosten:** Proprietäre CI/CD-Syntax (GitHub Actions YAML vs. GitLab CI YAML mit unterschiedlicher Semantik), plattformspezifische Konzepte (GitHub Environments vs. GitLab Stages)
     - **Migrationskosten:** Akkumulierte Datenbestände (Issues, PRs/MRs, Wikis, Releases), Pipeline-Konfigurationen, Integrationen zu Drittdiensten
   - **HINWEIS:** Diese Plausibilisierung schließt das argumentative Fehlglied zwischen allgemeiner Theorie und konkreter Anwendung

### 2.2 Finanzielle Risikokomponenten bei SaaS-Plattformen (100 Wörter)

**Argumentationskette:**

1. Operationalisierung von Lock-in-Risiko in zwei finanzielle Komponenten
   - **TRANSPARENZ:** Zweiteilung als analytisches Konstrukt dieser Arbeit, basierend auf Shapiro/Varian-Typologie

2. Komponente 1: Wechselkostenrisiko (einmalig)
   - Definition: Gesamtkosten eines vollständigen Anbieterwechsels (Transition)
   - Zusammensetzung (vgl. Abgrenzung Kap. 1):
     - Migrationskosten: Datentransfer, Pipeline-Konvertierung, Integrationsanpassung
     - Ausbildungskosten: Schulung, Produktivitätsverlust während Einarbeitung
     - Transitionskosten: Parallelbetriebs-Lizenzen, Setup der Zielplattform, ggf. externe Unterstützung
   - Dynamik: Steigt mit Nutzungsdauer und Integrationstiefe
   - Bezug zu Shapiro/Varian: Migrationskosten + Ausbildungskosten (Kap. 5, S. 117-123)

3. Komponente 2: Preiseskalationsrisiko (kumulativ)
   - Definition: Kumulative Mehrkosten durch Preissteigerungen, denen nicht ausgewichen werden kann
   - Mechanismus: Lock-in ermöglicht Preiserhöhungen, da kurzsichtige Kunden bei Preisdifferenz < Wechselkosten nicht wechseln
   - Bezug zu Zhu/Zhou (2012): Kurzsichtige Kunden antizipieren Wechselkosten nicht vollständig → Anbieter können Preise erhöhen

4. Zusammenhang der Komponenten
   - Wechselkosten wirken als Barriere, die Preiseskalation erst ermöglicht
   - Je höher die Wechselkosten, desto größer der Spielraum für Preiserhöhungen
   - **VERBLEIBENDE SCHWACHSTELLE:** Kausalzusammenhang konzeptionell plausibel (Zhu/Zhou), aber nicht empirisch validiert für DevOps-Plattformen

---

## Kapitel 3: Methodik zur Risikoquantifizierung (200 Wörter)

### 3.1 Aktivitätenbasierte Kostenschätzung für Wechselkosten (100 Wörter)

**Argumentationskette:**

1. Methodenwahl-Begründung
   - Aktivitätenbasierte Kostenschätzung in Anlehnung an Activity-Based Costing (ABC)
   - Kaplan/Cooper (1998): Cost & Effect, Kap. 3 – Grundprinzip: Kosten über Aktivitäten und Kostentreiber zuordnen
   - **BEGRÜNDUNG:** Aktivitätenbasierter Ansatz gewählt, weil Wechselkosten aus heterogenen Aktivitäten bestehen, die unterschiedliche Kostentreiber haben (Anzahl Repos, Pipelines, Entwickler)
   - **EINSCHRÄNKUNG:** Keine vollständige ABC-Anwendung, da indirekte Kosten (Overhead, Gemeinkosten) gemäß Abgrenzung (Kap. 1) ausgeschlossen sind – insbesondere Projektmanagement- und Entscheidungskosten. Die Schätzung beschränkt sich auf direkte, aktivitätsbezogene Kosten.

2. Kostenkategorien für Plattformmigration (aggregiert)
   - Kategorie A: Datentransfer (Repository-Migration inkl. Historie, Issues, Wikis) → Migrationskosten
   - Kategorie B: Konfigurationsanpassung (CI/CD-Pipeline-Konversion, Workflow-Re-Engineering) → Migrationskosten
   - Kategorie C: Integrationen (Neuverbindung zu Drittdiensten) → Migrationskosten
   - Kategorie D: Humankapital (Schulung, Produktivitätsverlust während Einarbeitung) → Ausbildungskosten
   - Kategorie E: Parallelbetrieb (Lizenzkosten beider Plattformen während Übergangsphase) → Transitionskosten
   - **HINWEIS:** Externe Unterstützung (Beratung, Implementierungspartner) ist optional und stark variabel; im Standardszenario nicht berücksichtigt, kann aber signifikant sein

3. Parametrisierung (Standardszenario)
   - Annahmen: 50 Repositories, 40 Pipelines, 10 Integrationen, 20 Entwickler
   - Kostensatz: 60€/h (basierend auf StepStone 2024: Median DevOps Engineer 65.000€/Jahr + 60% Lohnnebenkosten)
   - **VERBLEIBENDE SCHWACHSTELLE:** Aufwandsschätzungen pro Aktivität basieren auf Forrester TEI (2021), einer von GitLab beauftragten Studie
   - **TRANSPARENZ IM TEXT:** „Die Aufwandsschätzungen stützen sich mangels unabhängiger Studien auf herstellernahe Quellen, deren potenzielle Verzerrung bei der Interpretation zu berücksichtigen ist."

4. Exemplarische Vollrechnung für eine Plattform im Text (GitHub)
   - Demonstriert Methodik, detaillierte Herleitung
   - Zweite Plattform (GitLab) nur Ergebnisse + Abweichungen

### 3.2 Kostenvergleichsrechnung mit Preisszenarien für Preiseskalationsrisikokosten (100 Wörter)

**Argumentationskette:**

1. Methodenwahl-Begründung
   - Kostenvergleichsrechnung mit Preisszenarien zur Quantifizierung der Preiseskalationsrisikokosten
   - Götze (2014): Investitionsrechnung, Kap. 3 – Kostenvergleichsrechnung als statisches Verfahren zum Vergleich von Handlungsalternativen anhand ihrer Kosten
   - **BEGRÜNDUNG:** Kostenvergleichsrechnung gewählt, weil:
     - Fokus auf Kostendifferenz zwischen zwei Preisszenarien, nicht auf Investitionsrendite
     - Keine vollständigen Cashflows erforderlich (konsistent mit Abgrenzung)
     - Methodisch schlichter und transparenter als dynamische Verfahren
   - **ERWEITERUNG:** Anwendung auf zwei Preisszenarien (Baseline vs. Eskalation) als pragmatische Operationalisierung

2. Datenerhebung
   - Historische Preisdaten via Internet Archive (archive.org) für Zeitraum 2020-2024
   - **LIMITATION:** Nicht alle Preisänderungen vollständig dokumentiert; Enterprise-Preise nicht öffentlich
   - Erfassung: Absolute Preise, Feature-Bundling-Änderungen

3. Berechnung
   - Durchschnittliche jährliche Preissteigerungsrate aus historischen Daten ermitteln
   - Zwei Preisszenarien über 5-Jahres-Betrachtungszeitraum:
     - Baseline-Szenario: Konstante Preise (Preissteigerung = 0%)
     - Eskalationsszenario: Fortschreibung der historischen Preissteigerungsrate
   - Preiseskalationsrisikokosten = Σ(Lizenzkosten_Eskalation) - Σ(Lizenzkosten_Baseline)
   - **HINWEIS:** Keine Diskontierung, da statischer Kostenvergleich

4. Aggregation zum Gesamtrisiko
   - Lock-in-Risiko = Wechselkosten + Preiseskalationsrisiko
   - **TRANSPARENZ:** Additive Verknüpfung als Worst-Case-Betrachtung; die Preiseskalationsrisikokosten sind als Risikoaufschlag bei der Erstentscheidung zu interpretieren, nicht als prognostizierte Kosten

---

## Kapitel 4: Vergleichende Risikoanalyse (250 Wörter)

### 4.1 Referenzfall GitHub Team (100 Wörter)

**Argumentationskette:**

1. Wechselkosten-Berechnung (Volldarstellung)
   - Datentransfer: 50 Repos × 3h × 60€ = 9.000€
   - Konfiguration: 40 Pipelines × 8h × 60€ = 19.200€
     - Begründung Faktor 1,0: GitHub Actions nutzt standardisierte YAML-Syntax, Marketplace reduziert Custom-Code
   - Integrationen: 10 × 12h × 60€ = 7.200€
   - Schulung: 20 Entwickler × 12h × 60€ = 14.400€
   - Parallelbetrieb: 3 Monate × 20 User × 4 USD × 0,92 €/USD = ~221€
     - **ANNAHME:** 3 Monate Übergangsphase mit Lizenzen für beide Plattformen
   - **Gesamt Wechselkosten: ~50.021€** (gerundet: 50.000€)
   - **VERBLEIBENDE SCHWACHSTELLE:** Stundenschätzungen nicht unabhängig validiert

2. Preisrisikoanalyse
   - Historische Entwicklung (Team-Tier): 2020: 4 USD → 2024: 4 USD
   - CAGR: 0% p.a. (Preisstabilität)
   - **5-Jahres-Preiseskalationsrisiko: 0€**
   - **LIMITATION:** Extrapolation unsicher; Strategiewechsel möglich

3. Gesamtrisiko GitHub
   - **Lock-in-Risiko: ~50.000€**
   - Charakterisierung: Niedriges Risiko, konzentriert auf Wechselkosten-Komponente; Parallelbetriebs-Kosten marginal (0,4%)

### 4.2 Kontrastfall GitLab Premium (100 Wörter)

**Argumentationskette:**

1. Wechselkosten-Berechnung (Abweichungen zu GitHub)
   - Datentransfer: 9.000€ (identisch, Git-Standard)
   - Konfiguration: 40 Pipelines × 10h × 60€ = 24.000€
     - Faktor 1,25 aufgrund höherer Komplexität:
       - Auto DevOps (proprietäre Pipeline-Generierung)
       - DAG Pipelines (komplexe Abhängigkeitssteuerung)
       - Integriertes Security-Scanning
     - **VERBLEIBENDE SCHWACHSTELLE:** Faktor 1,25 nicht empirisch belegt, qualitative Einschätzung
   - Integrationen: 6.000€ (leicht reduziert durch bessere API-Standardisierung)
   - Schulung: 14.400€ (identisch)
   - Parallelbetrieb: 3 Monate × 20 User × 29 USD × 0,92 €/USD = ~1.600€
     - **HINWEIS:** Signifikant höher als GitHub aufgrund höherer Lizenzkosten
   - **Gesamt Wechselkosten: ~55.000€**

2. Preisrisikoanalyse
   - Historische Entwicklung (Premium-Tier): 2020: 19 USD → 2022: 29 USD → 2024: 29 USD
   - Durchschnittliche jährliche Preissteigerungsrate: 11,1% p.a. (signifikante historische Steigerung, konzentriert auf 2020-2022)
   - GitLab Blog (2022): Offizielle Preiserhöhungs-Ankündigung
   - Kostenvergleich mit Preisszenarien (20 User, 5 Jahre):
     - Baseline-Szenario (konstant 29 USD): 20 × 29 × 12 × 5 × 0,92 = ~32.000€
     - Eskalationsszenario (Preissteigerung 11,1% p.a.): ~39.300€
     - **Preiseskalationsrisiko: ~7.300€**
   - **HINWEIS:** Konservative Schätzung, da historische Preissteigerungsrate auf gesamten Projektionszeitraum angewendet; tatsächliche Preisstabilität seit 2022 könnte niedrigeres Risiko bedeuten

3. Gesamtrisiko GitLab
   - **Lock-in-Risiko: ~62.300€** (55.000€ Wechselkosten + 7.300€ Preiseskalation)
   - Charakterisierung: Höheres Risiko durch Kombination beider Komponenten; Parallelbetriebs-Kosten verstärken Differenz zu GitHub

### 4.3 Vergleichende Einordnung (50 Wörter)

**Ergebnistabelle:**

| Plattform | Wechselkosten | Preiseskalation | Gesamtrisiko | Primärer Treiber |
|-----------|---------------|-----------------|--------------|------------------|
| GitHub Team | ~50.000€ | 0€ | ~50.000€ | Wechselkosten |
| GitLab Premium | ~55.000€ | ~7.300€ | ~62.300€ | Preis + Wechsel |

**Befund:** Risikodifferenz von ca. 25% zwischen den Plattformen. Der Unterschied resultiert aus drei Faktoren: höhere Pipeline-Komplexität (+4.800€), höhere Parallelbetriebs-Kosten (+1.379€) und historische Preisvolatilität (+7.300€).

**NEU IDENTIFIZIERTE SCHWACHSTELLE:** Durch Reduktion auf zwei Plattformen ist keine Aussage über den Gesamtmarkt möglich; Ergebnisse als Methodendemonstration, nicht als vollständige Marktanalyse zu verstehen.

---

## Kapitel 5: Diskussion und Implikationen (150 Wörter)

### Ergebnisinterpretation mit integrierten Limitationen

**Argumentationskette:**

1. Beantwortung der Forschungsfrage
   - Finanzielle Risiken: Wechselkosten und Preiseskalation als quantifizierbare Komponenten identifiziert
   - Wechselkosten umfassen: Migrations-, Ausbildungs- und Transitionskosten (inkl. Parallelbetrieb)
   - Quantifizierung: Aktivitätenbasierte Kostenschätzung + Kostenvergleichsrechnung mit Preisszenarien als kombiniertes Bewertungsframework anwendbar
   - Ergebnis: Lock-in-Risiken im fünfstelligen Euro-Bereich bei mittelgroßen Teams (~50.000-62.000€)

2. Einordnung der Befunde
   - Kontextualisierung: Ähnlich zu Cloud-IaaS-Befunden (451 Research 2021: Exit-Kosten 18-32% des Spend), wenngleich Kostenstrukturen unterschiedlich
   - **KRITISCHE EINSCHRÄNKUNG:** 451 Research untersucht Cloud-Infrastruktur, nicht DevOps-SaaS; Übertragbarkeit begrenzt

3. Methodische Limitationen (integriert, nicht aufgelistet)
   - Aufwandsschätzungen basieren auf herstellernahen Quellen
   - Historischer Beobachtungszeitraum (4 Jahre) begrenzt Prognosesicherheit
   - Standardisiertes Szenario (50 Repos, 20 Entwickler) nicht für alle Unternehmensgrößen repräsentativ

4. Konzeptionelle Limitation
   - Modell zeigt Risikopotenzial, nicht realisierte Verluste
   - Kausalität Lock-in → tatsächliche Mehrkosten nicht empirisch nachgewiesen

### Entscheidungsframework für Praxis

**Argumentationskette:**

1. Integration in Investitionsentscheidungen
   - Erweiterung der TCO-Betrachtung um Lock-in-Risikokomponente
   - Formel: TCO_adjusted = Nominale SaaS-Kosten + Lock-in-Risiko
   - **TRANSPARENZ:** Als konservative Heuristik zu verstehen (Worst-Case)

2. Zwei Kernmaßnahmen zur Risikoreduktion
   - Maßnahme 1: Vertragliche Preisgarantien (z.B. max. +5% p.a.)
     - Effekt: Eliminiert Preiseskalationskomponente für Garantiezeitraum
   - Maßnahme 2: Exit-Support-Vereinbarungen
     - Anbieter unterstützt bei Migration (Datenexport, API-Zugang)
     - Effekt: Reduziert Exit-Kosten um geschätzt 10-20%
     - **SCHWACHSTELLE:** 10-20% nicht empirisch belegt

3. Fazit
   - Lock-in-Risiken sind quantifizierbar und sollten in Plattformentscheidungen einfließen
   - Methodischer Beitrag: Aktivitätenbasierte Kostenschätzung + Kostenvergleichsrechnung mit Preisszenarien als pragmatisches Bewertungsframework
   - Ausblick: Empirische Validierung durch longitudinale Fallstudien wäre wünschenswert
