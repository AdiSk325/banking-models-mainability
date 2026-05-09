# Rozdział 4: Przegląd Cyklu Życia End-to-End

> **Status:** 🔄 Szkielet — wymaga uzupełnienia diagramu flowchart i opisu bramek  
> **Priorytet uzupełnienia:** Wysoki

---

## 4.1 Mapa Cyklu Życia Modelu

Pełny cykl życia modelu składa się z 13 etapów pogrupowanych w 5 faz:

```
┌─────────────────────────────────────────────────────────────┐
│                    FAZA A: INICJACJA                        │
│  [1] Identyfikacja potrzeby → [2] Inicjacja i zatwierdzenie │
│       do developmentu                                        │
└─────────────────────────────────────────────────────────────┘
                              ↓
┌─────────────────────────────────────────────────────────────┐
│                   FAZA B: DEVELOPMENT                       │
│  [3] Dane i ocena → [4] Projektowanie → [5] Development     │
│  [6] Testy i dokumentacja                                   │
└─────────────────────────────────────────────────────────────┘
                              ↓
┌─────────────────────────────────────────────────────────────┐
│                 FAZA C: ZATWIERDZENIE                       │
│  [7] Walidacja niezależna → [8] Zatwierdzenie governance    │
└─────────────────────────────────────────────────────────────┘
                              ↓
┌─────────────────────────────────────────────────────────────┐
│                   FAZA D: PRODUKCJA                         │
│  [9] Wdrożenie → [10] Monitoring → [11] Review i aktualizacja│
│  [12] Change management                                      │
└─────────────────────────────────────────────────────────────┘
                              ↓
┌─────────────────────────────────────────────────────────────┐
│                 FAZA E: ZAKOŃCZENIE                         │
│  [13] Wycofanie i archiwizacja                              │
└─────────────────────────────────────────────────────────────┘
```

---

## 4.2 Etapy Cyklu Życia — Przegląd

| Nr | Etap | Kluczowe działanie | Kluczowy artefakt | Bramka |
|---|---|---|---|---|
| 1 | Identyfikacja potrzeby | Uzasadnienie biznesowe | Business Case | Go/No-Go decision |
| 2 | Inicjacja | Rejestracja, klasyfikacja, zatwierdzenie do dev | Model Initiation Form | Approval to develop |
| 3 | Dane i ocena | Źródła danych, jakość, dostępność | Data Assessment Report | Data approval |
| 4 | Projektowanie | Wybór metodologii, założenia | Design Document | Design sign-off |
| 5 | Development | Budowa modelu, testy jednostkowe | Model + Code | Dev complete |
| 6 | Testy i dokumentacja | QA, backtesting, dokumentacja | MDD, Test Results | Dok. complete |
| 7 | Walidacja niezależna | Niezależna ocena modelu | Validation Report | Validation passed |
| 8 | Zatwierdzenie | Review governance, sign-off | Approval Record | Governance approved |
| 9 | Wdrożenie | Implementacja, UAT, go-live | Deployment Evidence | Go-live |
| 10 | Monitoring | Ciągły monitoring performance | Monitoring Reports | — |
| 11 | Review / Recalibration | Przegląd okresowy, update | Review Report | — |
| 12 | Change management | Zarządzanie zmianami | Change Log | Change approval |
| 13 | Wycofanie | Decyzja, archiwizacja, handover | Retirement Record | Retirement approved |

---

## 4.3 Typowy Harmonogram

| Etap | Czas dla Tier 1 | Czas dla Tier 2 | Czas dla Tier 3 |
|---|---|---|---|
| Inicjacja | 2–4 tyg. | 1–2 tyg. | 1 tydzień |
| Dane i ocena | 4–8 tyg. | 2–4 tyg. | 1–2 tyg. |
| Projektowanie | 2–4 tyg. | 1–2 tyg. | < 1 tydzień |
| Development | 8–16 tyg. | 4–8 tyg. | 2–4 tyg. |
| Testy i dokumentacja | 4–8 tyg. | 2–4 tyg. | 1–2 tyg. |
| Walidacja | 6–12 tyg. | 4–6 tyg. | 1–2 tyg. |
| Zatwierdzenie | 2–4 tyg. | 1–2 tyg. | 1 tydzień |
| Wdrożenie | 4–8 tyg. | 2–4 tyg. | 1–2 tyg. |
| **Łącznie (dev→prod)** | **~9–16 mies.** | **~4–8 mies.** | **~2–4 mies.** |

---

## 4.4 Specyfika Lifecycle per Typ Modelu

### Modele regulacyjne
> ⚠️ **[REGULACYJNE]** Lifecycle modeli regulacyjnych zawiera dodatkowe elementy:
> - **Etap 2 (Inicjacja):** wymagana klasyfikacja jako Tier 1, wstępna ocena materiality
> - **Etap 7 (Walidacja):** pełny zakres walidacji (conceptual soundness + quantitative + use test)
> - **Etap 8 (Zatwierdzenie):** wymagana akceptacja MRC i w niektórych przypadkach notyfikacja KNF/ECB
> - **Etap 12 (Change management):** material changes wymagają notyfikacji nadzorcy
> - **Etap 11 (Review):** roczny przegląd jest obowiązkowy, nie opcjonalny
>
> ✍️ **[DO UZUPEŁNIENIA]** Dodać mapę wymagań KNF/EBA dla poszczególnych typów modeli regulacyjnych.

### Modele supervised
> 📋 **[SUPERVISED]** Kluczowe punkty uwagi w lifecycle:
> - **Etap 3 (Dane):** definicja target variable (label quality), time window selection, data leakage prevention
> - **Etap 5 (Development):** train/validation/test split strategy, cross-validation schema
> - **Etap 6 (Testy):** backtesting na out-of-time, subpopulation analysis, calibration
> - **Etap 7 (Walidacja):** testowanie na niezależnej próbce out-of-time, benchmark comparison
> - **Etap 10 (Monitoring):** performance drift, PSI, data drift, calibration monitoring

### Modele unsupervised
> 🔬 **[UNSUPERVISED]** Kluczowe różnice w lifecycle:
> - **Etap 4 (Projektowanie):** brak ground truth wymaga wcześniejszego ustalenia kryteriów walidacji business sense
> - **Etap 6 (Testy):** metryki wewnętrzne (Silhouette, Davies-Bouldin) + interpretacja biznesowa segmentów
> - **Etap 7 (Walidacja):** walidacja koncentruje się na stabilności, interpretacji i business sense
> - **Etap 10 (Monitoring):** monitoring stabilności segmentów, distribution shift
> - **Etap 11 (Review):** re-clustering jako standardowa czynność przy dużych zmianach populacji

---

## 4.5 Bramki Decyzyjne (Stage Gates)

Bramki są obowiązkowymi punktami kontrolnymi, po których nie można przejść do kolejnego etapu bez spełnienia kryteriów wyjścia.

| Bramka | Między etapami | Kto zatwierdza | Co jest sprawdzane |
|---|---|---|---|
| **BG-01: Approval to Develop** | 1→2 | Model Owner + MRM | Uzasadnienie biznesowe, zasoby, tier |
| **BG-02: Data Approval** | 3→4 | Data Owner + MRM | Jakość danych, dostępność, zgody |
| **BG-03: Design Sign-off** | 4→5 | Model Owner + MRM | Adekwatność metodologii, założenia |
| **BG-04: Development Complete** | 5→6 | Team Lead DS | Kompletność kodu, testy jednostkowe |
| **BG-05: Documentation Complete** | 6→7 | Model Owner | Kompletność MDD, wyniki testów |
| **BG-06: Validation Passed** | 7→8 | Validator | Brak blokujących findings |
| **BG-07: Governance Approved** | 8→9 | MRC / Model Owner | Formalna akceptacja |
| **BG-08: Go-Live** | 9→10 | IT + Model Owner | UAT passed, production readiness |

---

## 4.6 Ścieżki Alternatywne

### Warunkowe wdrożenie
> ✍️ **[DO UZUPEŁNIENIA]** Opisać politykę warunkowego wdrożenia — kiedy model może być wdrożony pomimo otwartych findings walidacyjnych (warunki, ograniczenia, timeline zamknięcia findings).

### Fast-track dla Tier 3
> ✍️ **[DO UZUPEŁNIENIA]** Opisać uproszczoną ścieżkę lifecycle dla modeli Tier 3.

### Re-development vs. recalibration
> ✍️ **[DO UZUPEŁNIENIA]** Opisać kiedy wystarczy recalibration (aktualizacja parametrów) a kiedy wymagany jest pełny re-development.

---

## 4.7 Powiązane Dokumenty

- [Rozdział 5: Wymagania Etapów](./05_etapy_cyklu_zycia.md) — szczegóły każdego etapu
- [Rozdział 7: Wymagane Artefakty](./07_wymagane_artefakty.md) — co wytwarzać na każdym etapie
- [Rozdział 6: Role i Odpowiedzialności](./06_role_i_odpowiedzialnosci.md) — kto jest odpowiedzialny za co

---

*Poprzedni: [03 — Klasyfikacja Modeli](./03_klasyfikacja_modeli.md) | Następny: [05 — Etapy Cyklu Życia](./05_etapy_cyklu_zycia.md)*
