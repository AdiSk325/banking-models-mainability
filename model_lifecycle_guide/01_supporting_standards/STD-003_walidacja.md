# STD-003: Standard Walidacji Modeli

> **Typ dokumentu:** Standard (Poziom 2)  
> **Status:** 🔄 Szkielet  
> **Powiązany rozdział przewodnika:** Etap 7

---

## Cel standardu

Standard określa minimalne wymagania dla niezależnej walidacji modeli, w tym zakres, metodologię, wymagania niezależności oraz raportowanie.

---

## 1. Zakres walidacji

### Minimalne elementy każdej walidacji

| Element | Tier 1 | Tier 2 | Tier 3 |
|---|---|---|---|
| Przegląd konceptualny (conceptual soundness) | 🔴 Pełny | 🔴 Pełny | 🟡 Uproszczony |
| Ocena danych i procesu developmentu | 🔴 Pełna | 🔴 Pełna | 🟡 Podstawowa |
| Niezależne testy ilościowe | 🔴 Pełne | 🔴 Kluczowe testy | 🟢 Opcjonalne |
| Ocena dokumentacji | 🔴 Pełna | 🔴 Pełna | 🟡 Podstawowa |
| Ocena planu monitoringu | 🔴 Obowiązkowa | 🔴 Obowiązkowa | 🟢 Opcjonalna |
| Porównanie z benchmarkiem | 🔴 Obowiązkowe | 🟡 Zalecane | 🟢 Opcjonalne |
| Use test assessment | 🔴 Obowiązkowy | 🟡 Zalecany | 🟢 Opcjonalny |

---

## 2. Wymagania niezależności

> 🔴 **OBOWIĄZKOWE** — Walidator musi być:
> - Organizacyjnie niezależny od zespołu developmentu modelu
> - Nieposiadający osobistego interesu w wyniku walidacji
> - Mający odpowiednią wiedzę merytoryczną do oceny modelu

> ⚠️ **[REGULACYJNE]** Dla modeli regulacyjnych: niezależność musi być wykazalna i udokumentowana. Regulatorzy (EBA, KNF) oczekują dowodów niezależności walidacji.

---

## 3. Metodologia walidacji

### 3.1 Przegląd konceptualny

> ✍️ **[DO UZUPEŁNIENIA]** Opisać:
> - Kryteria oceny adekwatności metodologii
> - Jak oceniać assumptions
> - Jak oceniać wybór algorytmu

### 3.2 Testy ilościowe

> ✍️ **[DO UZUPEŁNIENIA]** Opisać:
> - Minimalny zestaw testów per typ modelu
> - Progi akceptacji
> - Metody benchmark comparison

**Dla modeli supervised:**
> 📋 **[SUPERVISED]** Kluczowe testy:
> - Backtesting na niezależnym out-of-time dataset
> - Discriminatory power (GINI/AUC/KS)
> - Calibration (Hosmer-Lemeshow, calibration plots)
> - PSI / CSI (stability)
> - Subpopulation analysis
> - Sensitivity analysis

**Dla modeli unsupervised:**
> 🔬 **[UNSUPERVISED]** Kluczowe testy:
> - Internal validity metrics (Silhouette, Davies-Bouldin)
> - Stability across different time periods or samples
> - Business sense evaluation (expert review)
> - Sensitivity to hyperparameters (number of clusters, distance metric)

**Dla modeli regulacyjnych:**
> ⚠️ **[REGULACYJNE]** Kluczowe dodatkowe testy:
> - Stress testing
> - Sensitivity to macroeconomic scenarios
> - Benchmarking against regulatory-approved methodologies
> - Use test review

---

## 4. Klasyfikacja Findings

| Kategoria | Definicja | Konsekwencja |
|---|---|---|
| **Krytyczne** | Finding uniemożliwia bezpieczne użycie modelu | Model nie może być wdrożony |
| **Poważne** | Finding istotnie ogranicza wiarygodność | Wymaga planu adresowania przed lub po wdrożeniu |
| **Informacyjne** | Obserwacja bez bezpośredniego wpływu na bezpieczeństwo | Rekomendacja do rozważenia |

---

## 5. Rewalidacja

> ✍️ **[DO UZUPEŁNIENIA]** Opisać kiedy wymagana jest rewalidacja:
> - Po material change
> - Po przekroczeniu progów monitoringowych
> - Po rocznym przeglądzie
> - Na żądanie MRC lub nadzorcy

---

## Powiązania

- [Rozdział 5: Etap 7 — Walidacja](../00_guide/05_etapy_cyklu_zycia.md#57-etap-7-walidacja-niezależna)
- [TMPL-003: Raport Walidacji](../03_templates/TMPL-003_raport_walidacji.md)
- [PROC-003: Procedura Walidacji](../02_procedures/PROC-003_walidacja.md)
