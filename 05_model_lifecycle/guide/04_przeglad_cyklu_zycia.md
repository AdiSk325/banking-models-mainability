# Rozdział 4: Przegląd Cyklu Życia Modelu

> **Część:** Model Lifecycle Guide  
> **Status:** Draft — wymaga uzupełnienia merytorycznego  
> **Powiązane dokumenty:** [MODEL_LIFECYCLE_GUIDE.md](./MODEL_LIFECYCLE_GUIDE.md)

---

## Wprowadzenie

Ten rozdział prezentuje kompleksowy widok cyklu życia modelu — od inicjacji po wycofanie. Celem jest pokazanie całości procesu i wzajemnych zależności między etapami zanim przejdziemy do szczegółowych wymagań każdego z nich w rozdziale 5.

---

## 4.1 Diagram Cyklu Życia

```
┌─────────────────────────────────────────────────────────────────┐
│                    CYKL ŻYCIA MODELU                            │
│                                                                 │
│  ┌──────────┐    ┌──────────┐    ┌────────────┐               │
│  │ 5.1      │───▶│ 5.2      │───▶│ 5.3        │               │
│  │INICJACJA │    │DANE      │    │BUDOWA      │               │
│  │          │    │          │    │MODELU      │               │
│  └──────────┘    └──────────┘    └─────┬──────┘               │
│                                        │                        │
│  ┌──────────────────────────────────────▼──────────────────┐   │
│  │                   PĘTLA ITERACYJNA DEVELOPMENTU          │   │
│  │                                                          │   │
│  │  ┌────────────┐    ┌────────────┐    ┌────────────┐     │   │
│  │  │ 5.4        │    │ 5.5        │    │ 5.6        │     │   │
│  │  │TESTOWANIE  │───▶│WALIDACJA   │───▶│AKCEPTACJA  │     │   │
│  │  │DOKUMENTACJA│    │NIEZALEŻNA  │    │GOVERNANCE  │     │   │
│  │  └────────────┘    └────────────┘    └──────┬─────┘     │   │
│  │                          ▲ (findings)       │           │   │
│  │                          └─────────────────-┘           │   │
│  └─────────────────────────────────────────────────────────┘   │
│                                        │                        │
│                                        ▼                        │
│  ┌──────────┐    ┌──────────┐    ┌────────────┐               │
│  │ 5.10     │◀───│ 5.9      │◀───│ 5.7        │               │
│  │WYCOFANIE │    │ZARZĄDZANIE│   │WDROŻENIE   │               │
│  │ARCHIWIZACJA   │ZMIANĄ    │    │IMPLEMENTACJA               │
│  └──────────┘    └──────────┘    └─────┬──────┘               │
│         ▲                              │                        │
│         │                              ▼                        │
│         │              ┌──────────────────────────┐            │
│         │              │ 5.8                      │            │
│         │              │ MONITORING I             │            │
│         └──────────────│ PRZEGLĄD OKRESOWY        │            │
│          (trigger)     │                          │            │
│                        └──────────────────────────┘            │
└─────────────────────────────────────────────────────────────────┘
```

---

## 4.2 Przegląd Etapów — Streszczenie

| Nr | Etap | Cel | Kluczowy artefakt | Stage Gate |
|----|------|-----|-------------------|------------|
| 5.1 | Inicjacja | Uzasadnienie potrzeby i zgoda na rozwój | Model Concept Note | Model Owner + MRM approval |
| 5.2 | Pozyskanie i Ocena Danych | Ocena jakości i dostępności danych | Data Assessment Report | Data Owner sign-off |
| 5.3 | Projektowanie i Budowa | Wybór metodologii, budowa modelu | Model Development Document (draft) | DS Lead review |
| 5.4 | Testowanie i Dokumentacja | Weryfikacja jakości, finalizacja dokumentacji | Test Results + finalna MDD | Internal QA approval |
| 5.5 | Niezależna Walidacja | Niezależna ocena modelu | Validation Report | Validator sign-off |
| 5.6 | Akceptacja i Governance | Formalna akceptacja do wdrożenia | Approval Record | Komitet / MRM |
| 5.7 | Wdrożenie | Bezpieczne wprowadzenie do produkcji | Deployment Evidence | IT/MLOps sign-off |
| 5.8 | Monitoring i Przegląd | Ciągłe monitorowanie w produkcji | Monitoring Reports | Model Owner |
| 5.9 | Zarządzanie Zmianą | Kontrolowane zmiany w modelu | Change Request + Impact Assessment | MRM / Komitet |
| 5.10 | Wycofanie | Bezpieczne zakończenie życia modelu | Retirement Record | Model Owner + MRM |

---

## 4.3 Stage Gates — Punkty Kontrolne

Stage Gates to obowiązkowe punkty kontrolne, przez które model musi przejść przed wejściem w kolejny etap. Brak wymaganej akceptacji blokuje przejście dalej.

### Przegląd Stage Gates

```
Inicjacja ──▶ [GATE 1: Business Approval] ──▶ Dane
                                              
Dane ──▶ [GATE 2: Data Quality OK] ──▶ Budowa

Budowa ──▶ [GATE 3: Internal QA] ──▶ Testowanie/Dokumentacja

Testowanie ──▶ [GATE 4: Test Completion + Doc] ──▶ Walidacja

Walidacja ──▶ [GATE 5: Validation Clearance] ──▶ Akceptacja

Akceptacja ──▶ [GATE 6: Committee Approval] ──▶ Wdrożenie

Wdrożenie ──▶ [GATE 7: IT Sign-off + UAT] ──▶ Produkcja

Produkcja ──▶ [Ongoing GATE: Monitoring OK] ──▶ Kontynuacja

Zmiana ──▶ [GATE 8: Change Approval] ──▶ Implementacja zmiany

Model ──▶ [GATE 9: Retirement Approval] ──▶ Wycofanie
```

### Szczegóły Gate'ów

<!-- PROMPT DLA AUTORA:
Uzupełnij każdy gate o konkretne kryteria wejścia/wyjścia dla organizacji.
Wskaż kto jest uprawniony do podpisania każdego gate'u.
Opisz procedurę warunkowego wdrożenia (provisional deployment).
-->

| Gate | Kryterium przejścia | Uprawniony do sign-off |
|------|---------------------|------------------------|
| Gate 1 | Model Concept Note zaakceptowany, Tier i Owner przypisane | Model Owner + MRM |
| Gate 2 | Data Assessment Report podpisany, kwestie jakości danych adresowane | Data Owner |
| Gate 3 | Code Review zakończony, wewnętrzne testy zaliczone | DS Lead / Tech Lead |
| Gate 4 | Testy zaliczone, MDD finalna, Assumptions Register kompletny | Model Owner |
| Gate 5 | Validation Report bez blokujących findings (lub plan remediation) | Niezależny Walidator |
| Gate 6 | Formalna akceptacja komitetu | [PLACEHOLDER: nazwa komitetu] |
| Gate 7 | UAT zaliczony, IT deployment checklist podpisany | IT Lead / MLOps |
| Gate Monitoring | Brak przekroczenia progów alarmowych | Model Owner |
| Gate 8 | Change Request zaakceptowany, impact assessment zakończony | MRM / Komitet |
| Gate 9 | Retirement Record kompletny, następnik lub plan | Model Owner + MRM |

---

## 4.4 Specyfika Lifecycle według Kategorii Modelu

Diagram powyżej prezentuje typowy lifecycle. Poniżej przedstawiono kluczowe różnice w przebiegu procesu w zależności od kategorii modelu.

### Modele Regulacyjne (Kategoria A)

<!-- PROMPT DLA AUTORA:
Opisz gdzie lifecycle regulacyjnego modelu różni się od standardowego.
Kluczowe elementy: regulatory mapping, notyfikacje nadzorcze, wyższy bar dla gate'ów.
-->

**Kluczowe różnice:**
- Gate 1 wymaga analizy regulacyjnej i mapowania do przepisów
- Gate 5 (Walidacja) obejmuje ocenę zgodności z wymogami regulacyjnymi jako obowiązkowe kryterium
- Gate 6 (Komitet) na wyższym poziomie (CRO, ALCO lub równoważny)
- Zmiany wymagają oceny czy konieczna jest notyfikacja regulatora
- Archiwizacja wszystkich wersji i decyzji zgodnie z wymogami regulacyjnymi

**Dodatkowy artefakt na etapie Inicjacji:** Regulatory Mapping Document

**Uwaga dotycząca modeli IRB:** Wszelkie zmiany w modelach IRB mogą wymagać uprzedniej zgody nadzorcy (EBC/KNF) — weryfikacja tego obowiązku jest elementem Gate 8 (Zarządzanie Zmianą).

---

### Modele Scorecard / Statystyczne (Kategoria B)

<!-- PROMPT DLA AUTORA:
Opisz specyficzne elementy lifecycle scorecardów:
- Initial population analysis
- WoE/IV analysis jako etap budowy
- Champion-Challenger testing
-->

**Kluczowe różnice:**
- Etap budowy obejmuje obowiązkową analizę WoE/IV i binning
- Testowanie obejmuje champion-challenger test jeśli zastępuje istniejący model
- Monitoring obejmuje PSI/CSI jako metryki podstawowe

**Specyficzne artefakty:**
- WoE / IV Analysis Document
- Scorecard points documentation
- Population Stability Index baseline

---

### Modele Supervised ML (Kategoria C)

<!-- PROMPT DLA AUTORA:
Opisz pipeline ML jako etap budowy.
Wymień specyficzne testy (OOT, bias) jako obowiązkowe.
Opisz monitoring driftu.
-->

**Kluczowe różnice:**
- Etap budowy obejmuje eksperymentowanie (MLflow lub równoważny rejestr eksperymentów)
- Testowanie obejmuje Out-of-Time (OOT) validation i bias assessment jako obowiązkowe
- Gate 5 (Walidacja) obejmuje ocenę explainability jako kryterium
- Monitoring obejmuje drift konceptualny i drift danych

**Specyficzne artefakty:**
- Experiment Log (MLflow lub równoważny)
- SHAP/explainability report
- Bias & Fairness Assessment
- Model Card

---

### Modele Unsupervised (Kategoria D)

<!-- PROMPT DLA AUTORA:
Opisz jak wygląda budowa modelu unsupervised (iteracyjność, ocena bez etykiet).
Opisz alternatywne podejście do walidacji.
Opisz monitoring segmentów/anomalii.
-->

**Kluczowe różnice:**
- Etap budowy jest bardziej iteracyjny i eksploracyjny
- Brak klasycznego backtesting w Gate 4/5 — zastąpione przez ocenę jakości wielowymiarową
- Walidacja opiera się na ocenie biznesowej sensowności wyników
- Monitoring śledzi stabilność segmentów lub anomaly rate

**Specyficzne artefakty:**
- Cluster quality metrics report
- Business evaluation document (ocena sensowności biznesowej)
- Stability baseline dla segmentów

---

## 4.5 Ścieżka Uproszczona (Fast-Track) — Tier 3

<!-- PROMPT DLA AUTORA:
Opisz uproszczoną ścieżkę dla modeli Tier 3.
Wskaż które gate'y mogą być uproszczone lub połączone.
Zaznacz jakie minimalne wymagania nadal obowiązują.
-->

Dla modeli Tier 3 (niski wpływ) możliwe jest zastosowanie uproszczonej ścieżki:

| Element standardowy | Uproszczenie dla Tier 3 |
|--------------------|------------------------|
| Pełna MDD | Uproszczona dokumentacja (2-5 stron) |
| Niezależna walidacja | Wewnętrzny peer review |
| Komitet akceptacji | MRM sign-off |
| Monitoring miesięczny | Przegląd ad-hoc lub roczny |

> ⚠️ **Bez wyjątku:** Nawet w ścieżce uproszczonej: rejestracja w Model Inventory + przypisanie Model Ownera + podstawowa dokumentacja celu i metodologii.

---

## 4.6 Trigger Events — Wyjście z Ścieżki Standardowej

Następujące zdarzenia mogą uruchomić dodatkowe etapy lub zmianę ścieżki:

| Trigger | Skutek |
|---------|--------|
| Degradacja performance w monitoringu | Uruchomienie review, możliwa re-walidacja |
| Istotna zmiana danych wejściowych | Ocena potrzeby re-walidacji |
| Zmiana regulacyjna | Ocena wpływu na model, możliwa re-walidacja |
| Znajdowanie błędu w produkcji | Procedura awaryjna, natychmiastowa eskalacja |
| Zmiana zakresu stosowania modelu | Re-klasyfikacja Tier, możliwa re-walidacja |
| Nowy model zastępujący stary | Ścieżka wycofania (etap 5.10) |
| Przegląd roczny wskazał istotne ograniczenia | Decyzja o re-developmentu lub wycofaniu |

---

*Następny rozdział: [05_etapy/ — Wymagania Etapów Lifecycle](./05_etapy/)*
