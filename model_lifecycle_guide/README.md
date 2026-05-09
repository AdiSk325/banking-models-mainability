# Model Lifecycle Guide — Przewodnik dla Data Scientist w Bankowości

> **Przeznaczenie:** Nadrzędny framework pracy z modelami — „konstytucja" Data Scientistów pracujących z modelami bankowymi.  
> **Język:** Polski  
> **Odbiorcy główni:** Data Scientists, Model Developerzy  
> **Zakres modeli:** Modele regulacyjne · Modele supervised · Modele unsupervised

---

## Czym jest ten dokument?

**Model Lifecycle Guide** to ramowy przewodnik opisujący pełny cykl życia modelu w instytucji bankowej — od pomysłu biznesowego aż do wycofania modelu z produkcji. Pełni cztery kluczowe funkcje:

| Funkcja | Co oznacza w praktyce |
|---|---|
| **Nawigacyjna** | Pokazuje, gdzie jesteś w cyklu życia i co musisz zrobić dalej |
| **Normatywna** | Definiuje minimalne obowiązki i bramki decyzyjne |
| **Integrująca** | Spina governance, development, walidację, wdrożenie, monitoring i retirement |
| **Referencyjna** | Wskazuje powiązane standardy, procedury i szablony — nie duplikuje ich treści |

---

## Dla kogo jest ten przewodnik?

Ten przewodnik jest zaprojektowany przede wszystkim jako **codzienny przewodnik nawigacyjny dla Data Scientist** — odpowiada na pytania:

- Co muszę zrobić *przed* rozpoczęciem budowy modelu?
- Jakie dane i zatwierdzenia są wymagane?
- Jakie artefakty muszę wytworzyć?
- Kiedy angażuję Validatora / Model Ownera / MRM / IT?
- Jakie są bramki decyzyjne i kto je zatwierdza?
- Co jest wymagane do wdrożenia?
- Jakie obowiązki mam po wdrożeniu?
- Kiedy uruchamiam review lub recalibration?
- Jakie zmiany mogę wprowadzić samodzielnie, a jakie wymagają formalnej ścieżki?
- Jak zakończyć życie modelu?

Przewodnik jest również użyteczny dla:
- Model Ownerów i Model Userów
- Walidatorów i MRM (Model Risk Management)
- Audytorów wewnętrznych
- IT / MLOps
- Compliance

---

## Zakres — jakich modeli dotyczy?

Przewodnik obejmuje **wszystkie typy modeli** używanych w bankowości. Kluczowe kategorie, dla których mogą różnić się wymagania lifecycle i governance:

### 📐 Modele regulacyjne
Modele wymagane lub bezpośrednio regulowane przepisami ostrożnościowymi:
- Modele PD, LGD, EAD (Basel IRB)
- Modele IFRS 9 (ECL, staging)
- Modele kapitału regulacyjnego
- Modele stress-testowe (ICAAP, DFAST)

> ⚠️ **Uwaga dla DS:** Modele regulacyjne podlegają surowszym wymogom walidacji, dokumentacji, change management i zatwierdzenia przez nadzorcę. Wymagania etapów są opisane ze wskazaniem, gdzie dla tych modeli obowiązują wyższe standardy.

### 🤖 Modele supervised
Modele uczenia nadzorowanego z etykietowanymi danymi:
- Modele klasyfikacji (scoring, PD ML, fraud detection)
- Modele regresji (LGD ML, wycena)
- Modele time-series (forecasting, cashflow)
- Modele sekwencyjne i ensemble

> 📋 **Uwaga dla DS:** Dla modeli supervised kluczowe są: quality label, data split strategy, feature leakage prevention, backtesting i explainability. Przewodnik wskazuje te priorytety w odpowiednich etapach.

### 🔍 Modele unsupervised
Modele bez etykiet, uczące się wzorców z danych:
- Modele segmentacji (clustering klientów, PD)
- Modele wykrywania anomalii (fraud, AML)
- Modele redukcji wymiarowości
- Modele embeddings i reprezentacji

> 🔬 **Uwaga dla DS:** Dla modeli unsupervised walidacja business sense i stabilność segmentów są szczególnie istotne. Przewodnik wskazuje alternatywne podejścia walidacyjne dla tej kategorii.

---

## Hierarchia dokumentów

```
POZIOM 1: Model Lifecycle Guide (ten dokument)
    ↓ Zasady, etapy, role, artefakty, governance, odwołania

POZIOM 2: Supporting Standards (01_supporting_standards/)
    ↓ STD-001 Development | STD-002 Documentation | STD-003 Validation
    ↓ STD-004 Monitoring | STD-005 Inventory | STD-006 Change Mgmt
    ↓ STD-007 Explainability | STD-008 Deployment

POZIOM 3: Procedures / SOPs (02_procedures/)
    ↓ PROC-001 Inicjacja | PROC-002 Dane | PROC-003 Walidacja
    ↓ PROC-004 Wdrożenie | PROC-005 Monitoring | PROC-006 Wycofanie

POZIOM 4: Templates & Checklists (03_templates/)
    ↓ Dokumentacja modelu | Raport walidacji | Plan monitoringu
    ↓ Wniosek o zmianę | Formularz wycofania | Checklista go-live
```

---

## Struktura tego repozytorium

```
model_lifecycle_guide/
├── README.md                          ← TEN PLIK — start tutaj
├── STATUS.md                          ← Roadmap i status prac
│
├── 00_guide/                          ← Główne rozdziały przewodnika
│   ├── README.md                      ← Spis treści i instrukcja nawigacji
│   ├── 01_cel_i_zakres.md             ← Cel, zakres, odbiorcy, definicje
│   ├── 02_zasady_nadrzedne.md         ← Zasady nadrzędne (Guiding Principles)
│   ├── 03_klasyfikacja_modeli.md      ← Klasyfikacja i tiering modeli
│   ├── 04_przeglad_cyklu_zycia.md     ← Przegląd end-to-end lifecycle
│   ├── 05_etapy_cyklu_zycia.md        ← Wymagania każdego etapu
│   ├── 06_role_i_odpowiedzialnosci.md ← Role, macierz RACI
│   ├── 07_wymagane_artefakty.md       ← Minimalne artefakty per etap i typ
│   ├── 08_kontrole_wyjatki.md         ← Kontrole, wyjątki, eskalacja
│   ├── 09_powiazane_dokumenty.md      ← Mapa dokumentów powiązanych
│   ├── 10_przeglad_przewodnika.md     ← Cykl przeglądu tego przewodnika
│   └── 11_dodatki.md                  ← Glosariusz, skróty, diagramy
│
├── 01_supporting_standards/           ← Standardy wspierające (Poziom 2)
│   ├── README.md
│   ├── STD-001_rozwoj_modeli.md
│   ├── STD-002_dokumentacja.md
│   ├── STD-003_walidacja.md
│   ├── STD-004_monitoring.md
│   ├── STD-005_inwentarz.md
│   ├── STD-006_zarzadzanie_zmiana.md
│   ├── STD-007_explainability.md
│   └── STD-008_wdrozenie.md
│
├── 02_procedures/                     ← Procedury / SOPs (Poziom 3)
│   ├── README.md
│   ├── PROC-001_inicjacja.md
│   ├── PROC-002_dane_i_ocena.md
│   ├── PROC-003_walidacja.md
│   ├── PROC-004_wdrozenie.md
│   ├── PROC-005_monitoring.md
│   └── PROC-006_wycofanie.md
│
├── 03_templates/                      ← Szablony i checklisty (Poziom 4)
│   ├── README.md
│   ├── TMPL-001_dokument_koncepcji.md
│   ├── TMPL-002_dokumentacja_modelu.md
│   ├── TMPL-003_raport_walidacji.md
│   ├── TMPL-004_plan_monitoringu.md
│   ├── TMPL-005_wniosek_o_zmiane.md
│   └── TMPL-006_wycofanie_modelu.md
│
├── 04_references/                     ← Źródła i inspiracje
│   ├── README.md
│   ├── 01_regulacyjne.md
│   ├── 02_nadzorcze.md
│   ├── 03_standardy.md
│   ├── 04_branzowe.md
│   ├── 05_akademickie.md
│   └── 06_wewnetrzne.md
│
└── 05_working_notes/                  ← Notatki robocze
    ├── README.md
    ├── pytania_otwarte.md
    └── notatki_robocze.md
```

---

## Jak nawigować tym przewodnikiem?

### Jeśli jesteś Data Scientistem i...

| Sytuacja | Gdzie iść |
|---|---|
| Zaczynasz nowy projekt modelarski | [05_etapy → Inicjacja](./00_guide/05_etapy_cyklu_zycia.md) |
| Chcesz wiedzieć jakie dokumenty wytworzyć | [07_wymagane_artefakty](./00_guide/07_wymagane_artefakty.md) |
| Przygotowujesz model do walidacji | [PROC-003_walidacja](./02_procedures/PROC-003_walidacja.md) |
| Szukasz szablonu dokumentacji | [03_templates/](./03_templates/) |
| Chcesz zrozumieć zakres walidacji | [STD-003_walidacja](./01_supporting_standards/STD-003_walidacja.md) |
| Planujesz wdrożenie | [PROC-004_wdrozenie](./02_procedures/PROC-004_wdrozenie.md) |
| Coś się zmieniło w modelu | [STD-006_zarzadzanie_zmiana](./01_supporting_standards/STD-006_zarzadzanie_zmiana.md) |
| Model przestał działać poprawnie | [PROC-005_monitoring](./02_procedures/PROC-005_monitoring.md) |
| Wycofujesz model | [PROC-006_wycofanie](./02_procedures/PROC-006_wycofanie.md) |

---

## Status dokumentu

| Element | Status | Wersja |
|---|---|---|
| Struktura repozytorium | ✅ Gotowa | 1.0 |
| Rozdziały główne (szkielet) | 🔄 W trakcie | 0.5 |
| Supporting Standards | 🔄 Szkielety gotowe | 0.3 |
| Procedures / SOPs | 🔄 Szkielety gotowe | 0.3 |
| Templates | 🔄 Szkielety gotowe | 0.3 |
| References | 🔄 W trakcie | 0.5 |
| Working Notes | 🔄 Aktywne | — |

Szczegółowy roadmap: [STATUS.md](./STATUS.md)

---

*Wersja: 0.5 | Data ostatniej aktualizacji: 2026-05-09 | Język: Polski*
