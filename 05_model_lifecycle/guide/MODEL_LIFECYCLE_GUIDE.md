# Model Lifecycle Guide — Przewodnik Zarządzania Cyklem Życia Modeli

> **Wersja:** 1.0-draft  
> **Status:** W opracowaniu  
> **Język:** Polski  
> **Ostatnia aktualizacja:** 2026-05-09  
> **Właściciel dokumentu:** Model Risk Management / Chief Model Risk Office  

---

## O tym dokumencie

Ten dokument jest **konstytucją pracy z modelami** w organizacji. Pełni rolę nadrzędnego przewodnika (Framework Guide), który:

- **Nawiguje** — pokazuje jak wygląda pełny cykl życia modelu od pomysłu do wycofania.
- **Normuje** — definiuje minimalne obowiązkowe zasady dla wszystkich ról zaangażowanych w pracę z modelami.
- **Integruje** — spaja w jedno politykę zarządzania ryzykiem modelowym, standardy developmentu, walidację, wdrożenie, monitoring, change management i governance.
- **Odsyła** — wskazuje do szczegółowych standardów, procedur i szablonów zamiast powielać ich treść.

**Hierarchia dokumentów:**

```
Poziom 1: Polityka zarządzania ryzykiem modelowym (Model Risk Policy)
     ↓
Poziom 2: Model Lifecycle Guide ← TEN DOKUMENT
     ↓
Poziom 3: Standardy i procedury (Standards & Procedures)
     ↓
Poziom 4: Szablony, checklistry, przykłady (Templates & Tools)
```

### Zasada kluczowa
- **Guide = rama i zasady** (co musi się wydarzyć, kto odpowiada, jakie artefakty, jakie punkty kontrolne)
- **Standardy/procedury = szczegóły wykonawcze** (jak dokładnie to zrobić)
- **Szablony = narzędzia** (konkretne formularze i wzory dokumentów)

---

## Spis Treści — Kompletny

| Nr | Rozdział | Plik | Status |
|----|----------|------|--------|
| 1 | [Cel, Zakres i Odbiorcy](#1-cel-zakres-i-odbiorcy) | [01_cel_zakres_odbiorcy.md](./01_cel_zakres_odbiorcy.md) | Draft |
| 2 | [Zasady Nadrzędne](#2-zasady-nadrzędne) | [02_zasady_nadrzedne.md](./02_zasady_nadrzedne.md) | Draft |
| 3 | [Klasyfikacja i Tiering Modeli](#3-klasyfikacja-i-tiering-modeli) | [03_klasyfikacja_modeli.md](./03_klasyfikacja_modeli.md) | Draft |
| 4 | [Przegląd Cyklu Życia Modelu](#4-przegląd-cyklu-życia-modelu) | [04_przeglad_cyklu_zycia.md](./04_przeglad_cyklu_zycia.md) | Draft |
| 5 | [Wymagania Etapów Lifecycle](#5-wymagania-etapów-lifecycle) | [05_etapy/](./05_etapy/) | Draft |
| 5.1 | Inicjacja i Zgłoszenie Potrzeby | [05_etapy/01_inicjacja.md](./05_etapy/01_inicjacja.md) | Draft |
| 5.2 | Pozyskiwanie i Ocena Danych | [05_etapy/02_pozyskanie_danych.md](./05_etapy/02_pozyskanie_danych.md) | Draft |
| 5.3 | Projektowanie i Budowa Modelu | [05_etapy/03_projektowanie_rozwoj.md](./05_etapy/03_projektowanie_rozwoj.md) | Draft |
| 5.4 | Testowanie i Dokumentacja | [05_etapy/04_testowanie_dokumentacja.md](./05_etapy/04_testowanie_dokumentacja.md) | Draft |
| 5.5 | Niezależna Walidacja | [05_etapy/05_walidacja_niezalezna.md](./05_etapy/05_walidacja_niezalezna.md) | Draft |
| 5.6 | Akceptacja i Governance | [05_etapy/06_akceptacja_governance.md](./05_etapy/06_akceptacja_governance.md) | Draft |
| 5.7 | Wdrożenie i Implementacja | [05_etapy/07_wdrozenie.md](./05_etapy/07_wdrozenie.md) | Draft |
| 5.8 | Monitoring i Przegląd Okresowy | [05_etapy/08_monitoring_przeglad.md](./05_etapy/08_monitoring_przeglad.md) | Draft |
| 5.9 | Zarządzanie Zmianą | [05_etapy/09_zarzadzanie_zmiana.md](./05_etapy/09_zarzadzanie_zmiana.md) | Draft |
| 5.10 | Wycofanie i Archiwizacja | [05_etapy/10_wycofanie_archiwizacja.md](./05_etapy/10_wycofanie_archiwizacja.md) | Draft |
| 6 | [Role i Odpowiedzialności](#6-role-i-odpowiedzialności) | [06_role_odpowiedzialnosci.md](./06_role_odpowiedzialnosci.md) | Draft |
| 7 | [Wymagane Artefakty i Dokumentacja](#7-wymagane-artefakty-i-dokumentacja) | [07_wymagane_artefakty.md](./07_wymagane_artefakty.md) | Draft |
| 8 | [Kontrole, Wyjątki i Eskalacja](#8-kontrole-wyjątki-i-eskalacja) | [08_kontrole_wyjatki.md](./08_kontrole_wyjatki.md) | Draft |
| 9 | [Powiązane Standardy i Dokumenty](#9-powiązane-standardy-i-dokumenty) | [09_powiazane_dokumenty.md](./09_powiazane_dokumenty.md) | Draft |
| 10 | [Cykl Przeglądu tego Przewodnika](#10-cykl-przeglądu) | — | Do uzupełnienia |
| A | [Załączniki i Glosariusz](#załączniki) | — | Do uzupełnienia |

---

## 1. Cel, Zakres i Odbiorcy

→ *Szczegółowy rozdział: [01_cel_zakres_odbiorcy.md](./01_cel_zakres_odbiorcy.md)*

**Cel dokumentu:** Ustanowienie spójnego, opartego na ryzyku frameworku zarządzania cyklem życia modeli — od inicjacji przez wdrożenie, monitoring, aż po wycofanie.

**Zakres modeli objętych przewodnikiem:**

| Kategoria | Przykłady | Uwagi |
|-----------|-----------|-------|
| **Modele regulacyjne** | PD, LGD, EAD (IRB), IFRS9 ECL, kapitał regulacyjny | Najwyższy poziom rygoryzmu |
| **Modele statystyczne / scorecard** | Scoring aplikacyjny, behawioralny, kolekcja | Wymogi dokumentacyjne i walidacyjne |
| **Modele nadzorowane (supervised)** | XGBoost/GBM dla ryzyka kredytowego, modele predykcyjne | Dodatkowe wymogi explainability |
| **Modele nienadzorowane (unsupervised)** | Segmentacja, anomaly detection, clustering | Specyfika walidacji i monitoringu |

**Odbiorcy:**
- 🔧 **Data Scientists / Deweloperzy modeli** — przewodnik procesu pracy
- 👤 **Model Ownerzy** — obowiązki i punkty decyzyjne
- ✅ **Walidatorzy / Model Risk** — minimalne wymagania i niezależność
- ⚙️ **IT / MLOps** — wymagania wdrożeniowe i kontrole
- 📋 **Compliance / Audit** — wymagania governance i dokumentacja
- 🏛️ **Komitety i zarząd** — oversight i akceptacja

---

## 2. Zasady Nadrzędne

→ *Szczegółowy rozdział: [02_zasady_nadrzedne.md](./02_zasady_nadrzedne.md)*

Następujące zasady są podstawą wszystkich wymagań opisanych w tym przewodniku:

1. **Podejście oparte na ryzyku (Risk-Based Approach)** — poziom rygoryzmu proporcjonalny do ryzyka modelu
2. **Proporcjonalność (Proportionality)** — wymogi adekwatne do klasy i zastosowania modelu
3. **Odtwarzalność (Reproducibility)** — każdy model musi być możliwy do odtworzenia
4. **Identyfikowalność (Traceability)** — pełny ślad decyzji, zmian i zastosowania modelu
5. **Niezależne weryfikowanie (Independent Challenge)** — walidacja niezależna od developmentu
6. **Dokumentacja jako obowiązek (Documentation by Design)** — dokumentacja jest częścią procesu, nie dodatkiem
7. **Segregacja obowiązków (Segregation of Duties)** — oddzielenie budowy, walidacji i akceptacji
8. **Kontrolowane zmiany (Controlled Change)** — żadna zmiana materialna bez formalnego procesu
9. **Ciągły monitoring (Monitoring Throughout Lifecycle)** — monitoring to obowiązek przez cały czas życia modelu
10. **Ludzka odpowiedzialność (Human Accountability)** — jasno zdefiniowany owner dla każdego modelu
11. **Zgodność z regulacjami (Regulatory Compliance)** — bezwzględne przestrzeganie wymagań regulacyjnych

---

## 3. Klasyfikacja i Tiering Modeli

→ *Szczegółowy rozdział: [03_klasyfikacja_modeli.md](./03_klasyfikacja_modeli.md)*

Poziom wymagań zależy od klasy ryzyka modelu:

| Tier | Opis | Przykłady | Poziom wymagań |
|------|------|-----------|----------------|
| **Tier 1 — Krytyczny** | Modele regulacyjne, materialne dla raportowania | IRB PD/LGD, IFRS9 ECL | Pełny zakres |
| **Tier 2 — Istotny** | Modele wpływające na decyzje klientowskie | Scoring, pricing, CRM | Standardowy zakres |
| **Tier 3 — Niski wpływ** | Modele analityczne, badawcze, pomocnicze | Segmentacja eksploracyjna | Uproszczony zakres |

---

## 4. Przegląd Cyklu Życia Modelu

→ *Szczegółowy rozdział: [04_przeglad_cyklu_zycia.md](./04_przeglad_cyklu_zycia.md)*

```
[Inicjacja] → [Dane] → [Budowa] → [Testowanie] → [Walidacja] → [Akceptacja]
                                                                       ↓
[Wycofanie] ← [Zmiana] ← [Monitoring] ← [Wdrożenie] ←────────────────┘
```

Każdy etap ma zdefiniowane:
- Cel etapu
- Wejścia i wyjścia  
- Wymagane aktywności
- Wymagane artefakty
- Role odpowiedzialne
- Kryteria wejścia/wyjścia (stage gates)

---

## 5. Wymagania Etapów Lifecycle

→ *Szczegółowe rozdziały w folderze: [05_etapy/](./05_etapy/)*

| Etap | Kluczowy artefakt | Stage Gate |
|------|-------------------|------------|
| 5.1 Inicjacja | Concept Note / Business Case | Akceptacja Model Ownera + MRM |
| 5.2 Dane | Data Assessment Report | Data Owner sign-off |
| 5.3 Budowa | Model Development Document | Code Review + DS Lead |
| 5.4 Testowanie | Test Results, dokumentacja | Internal QA |
| 5.5 Walidacja | Validation Report + findings | Validator sign-off |
| 5.6 Akceptacja | Approval Record | Komitet / MRM |
| 5.7 Wdrożenie | Deployment Evidence | IT / MLOps sign-off |
| 5.8 Monitoring | Monitoring Reports | Model Owner |
| 5.9 Zmiana | Change Request + impact assessment | MRM / Komitet |
| 5.10 Wycofanie | Retirement Record | Model Owner + MRM |

---

## 6. Role i Odpowiedzialności

→ *Szczegółowy rozdział: [06_role_odpowiedzialnosci.md](./06_role_odpowiedzialnosci.md)*

Kluczowe role zdefiniowane w tym przewodniku:
- Data Scientist / Model Developer
- Model Owner
- Model User
- Niezależny Walidator
- Model Risk Management (MRM)
- Business Owner / Sponsor
- Data Owner / Data Steward
- IT / MLOps / Engineering
- Compliance
- Internal Audit
- Komitet Akceptacji Modeli

---

## 7. Wymagane Artefakty i Dokumentacja

→ *Szczegółowy rozdział: [07_wymagane_artefakty.md](./07_wymagane_artefakty.md)*

Minimalny zestaw artefaktów wymaganych dla każdego modelu (szczegóły zależą od Tiera):
- Model Concept Note / Business Justification
- Data Assessment Report
- Model Development Document (MDD)
- Assumptions Register
- Test Results
- Validation Report
- Deployment Evidence
- Monitoring Plan & Reports
- Model Inventory Entry
- Change Log / Version History
- Approval Records
- Retirement Record

---

## 8. Kontrole, Wyjątki i Eskalacja

→ *Szczegółowy rozdział: [08_kontrole_wyjatki.md](./08_kontrole_wyjatki.md)*

- Wymagane punkty kontrolne w procesie
- Zasady zarządzania wyjątkami i odstępstwami
- Ścieżki eskalacji
- Progi eskalacji i komitety decyzyjne

---

## 9. Powiązane Standardy i Dokumenty

→ *Szczegółowy rozdział: [09_powiazane_dokumenty.md](./09_powiazane_dokumenty.md)*

| Dokument | Typ | Opis |
|----------|-----|------|
| Model Risk Policy | Polityka | Nadrzędna polityka zarządzania ryzykiem modelowym |
| Model Development Standard | Standard | Wymagania developmentu |
| Model Documentation Standard | Standard | Wymogi dokumentacyjne |
| Validation Procedure | Procedura | Przebieg walidacji |
| Monitoring Standard | Standard | Metryki i progi monitoringu |
| Change Management Procedure | Procedura | Zarządzanie zmianą modelu |
| MLOps Deployment Standard | Standard | Wymagania wdrożeniowe |
| Model Inventory Procedure | Procedura | Rejestr modeli |
| AI/ML Explainability Standard | Standard | Wymagania wyjaśnialności |
| Data Quality Standard | Standard | Jakość danych dla modeli |

---

## 10. Cykl Przeglądu

Ten przewodnik podlega przeglądowi co **12 miesięcy** lub wcześniej, jeśli:
- nastąpiła istotna zmiana regulacyjna,
- zmienił się zakres modeli w organizacji,
- wyniki audytu lub walidacji wskazały na potrzebę aktualizacji.

**Właściciel przeglądu:** Model Risk Management  
**Zatwierdzający:** Komitet Akceptacji Modeli / CRO

---

## Załączniki

- **Załącznik A:** Glosariusz kluczowych pojęć *(do uzupełnienia)*
- **Załącznik B:** Mapa dokumentów powiązanych *(do uzupełnienia)*
- **Załącznik C:** Diagram lifecycle (wizualizacja) *(do uzupełnienia)*
- **Załącznik D:** RACI Matrix — pełna macierz ról *(do uzupełnienia — patrz rozdział 6)*
- **Załącznik E:** Matryca klasyfikacji modeli *(do uzupełnienia — patrz rozdział 3)*

---

## Referencje Regulacyjne i Branżowe

Pełna bibliografia: [../references/README.md](../references/README.md)

Kluczowe źródła:
- SR 11-7 Guidance on Model Risk Management (US Federal Reserve, 2011)
- OCC Bulletin 2011-12 (Office of the Comptroller of the Currency, 2011)
- EBA Guidelines on Model Risk Management (EBA, 2023)
- ECB Guide to Internal Models (ECB, 2018)
- SS1/23 Model Risk Management Principles for Banks (PRA, 2023)
- Rekomendacje KNF (aktualne wytyczne)

---

*Ten dokument stanowi własność intelektualną organizacji. Wszelkie zmiany wymagają formalnego procesu aktualizacji i akceptacji.*
