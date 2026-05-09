# Rozdział 3: Klasyfikacja i Tiering Modeli

> **Status:** 🔄 Szkielet — wymaga uzupełnienia macierzy tiering z konkretnymi progami  
> **Priorytet uzupełnienia:** Wysoki

---

## 3.1 Po co klasyfikować modele?

Nie wszystkie modele są jednakowo ryzykowne. Klasyfikacja (tiering) pozwala stosować wymagania proporcjonalne do ryzyka — Tier 1 (modele najważniejsze) podlegają najostrzejszym wymogom, Tier 3 (modele pomocnicze) — uproszczonej ścieżce.

> 🔴 **OBOWIĄZKOWE** — Każdy model musi być zaklasyfikowany do odpowiedniego tieru na etapie inicjacji, przed rozpoczęciem developmentu.

---

## 3.2 Wymiary Klasyfikacji

Tier modelu wyznaczany jest na podstawie oceny następujących wymiarów:

| Wymiar | Opis | Przykład |
|---|---|---|
| **Wpływ finansowy** | Potencjalna strata lub zysk wynikający z błędu modelu | Model IFRS 9 — błąd o 10% ECL → materialna strata |
| **Wpływ regulacyjny** | Czy błąd modelu narazi bank na sankcje nadzorcze | Model IRB — nieprawidłowy PD → wyższy wymóg kapitałowy |
| **Automatyzacja decyzji** | Czy model podejmuje decyzje bez udziału człowieka | Scoring kredytowy → automatyczna decyzja o pożyczce |
| **Liczba klientów** | Ile klientów/transakcji podlega modelowi | Model scoringowy masowy vs. model dla portfela korporacyjnego |
| **Explainability** | Czy model może być wyjaśniony klientowi/regulatorowi | Black-box ML vs. regresja logistyczna |
| **Złożoność modelu** | Liczba zmiennych, interakcji, złożoność architektury | XGBoost z 200 features vs. 5-zmienna regresja |
| **Wrażliwość danych** | Czy model przetwarza dane osobowe / wrażliwe | Model churn z transakcjami osobistymi |
| **Częstotliwość użycia** | Jak często model jest używany operacyjnie | Scoring dzienny vs. model kwartalny |

---

## 3.3 Definicje Tierów

### Tier 1 — Modele o wysokim ryzyku (Critical Models)

**Charakterystyka:**
- Bezpośredni wpływ na wymogi kapitałowe lub płynność
- Objęte nadzorem regulacyjnym (EBA, KNF, ECB)
- Automatyzacja decyzji na dużą skalę
- Wysoka wrażliwość na błąd — brak marginesu tolerancji

**Typowe przykłady:**

> ⚠️ **[REGULACYJNE]**
> - Modele PD, LGD, EAD (podejście IRB)
> - Modele IFRS 9 ECL (Stage 1/2/3 + forward-looking adjustments)
> - Modele stress-testowe (ICAAP, DFAST)
> - Modele LCR/NSFR (płynność)

> 📋 **[SUPERVISED]**
> - Modele scoringowe używane w masowej automatycznej decyzji kredytowej
> - Modele fraud detection blokujące transakcje w czasie rzeczywistym

**Wymagania Tier 1:**
- Pełna, niezależna walidacja (zakres: konceptualny, ilościowy, użytkowy)
- Pełna dokumentacja modelarska (MDD, assumptions register, data documentation)
- Zatwierdzenie przez komitet governance (Model Risk Committee lub równorzędny)
- Monitoring co najmniej miesięczny
- Formal change management dla wszelkich zmian
- Przegląd roczny (Annual Review)
- Archiwizacja zgodna z wymogami regulacyjnymi

---

### Tier 2 — Modele o średnim ryzyku (Significant Models)

**Charakterystyka:**
- Istotny wpływ finansowy lub decyzyjny, ale poniżej progu regulacyjnego
- Stosowane w decyzjach biznesowych dla znaczącego segmentu klientów
- Model owner posiada mechanizmy override

**Typowe przykłady:**

> 📋 **[SUPERVISED]**
> - Modele scoringowe behawioralne
> - Modele predykcyjne churn/retencja z dużym wpływem budżetowym
> - Modele wyceny ryzyka dla portfeli mid-size

> 🔬 **[UNSUPERVISED]**
> - Modele segmentacji klientów używane w strategii produktowej
> - Modele wykrywania anomalii w AML (alert generation)

**Wymagania Tier 2:**
- Walidacja niezależna (zakres: konceptualny + kluczowe testy ilościowe)
- Pełna dokumentacja modelarska
- Zatwierdzenie przez Model Owner i MRM
- Monitoring co najmniej kwartalny
- Przegląd roczny lub po zdarzeniu trigger

---

### Tier 3 — Modele o niskim ryzyku (Low-Risk / Auxiliary Models)

**Charakterystyka:**
- Pomocnicze narzędzia analityczne
- Ograniczony wpływ decyzyjny
- Możliwa prosta walidacja wewnętrzna przez developera lub team lead

**Typowe przykłady:**

> 📋 **[SUPERVISED]**
> - Modele eksploracyjne i proof-of-concept
> - Modele raportowe bez implikacji decyzyjnych

> 🔬 **[UNSUPERVISED]**
> - Clustering exploratoryjny dla segmentacji wewnętrznej
> - Modele PCA/UMAP dla wizualizacji danych

**Wymagania Tier 3:**
- Uproszczona walidacja (peer review + podstawowe testy)
- Uproszczona dokumentacja
- Zatwierdzenie przez Model Owner i/lub team lead
- Monitoring półroczny lub roczny
- Przegląd po zdarzeniu trigger lub co 2 lata

---

## 3.4 Macierz Klasyfikacji

> ✍️ **[DO UZUPEŁNIENIA]** Uzupełnić tabelę o konkretne progi finansowe i decyzyjne obowiązujące w organizacji.

| Kryterium | Tier 1 (Wysoki) | Tier 2 (Średni) | Tier 3 (Niski) |
|---|---|---|---|
| Wpływ finansowy | > [próg do uzupełnienia] | [próg] – [próg] | < [próg do uzupełnienia] |
| Regulacyjny | Tak (IRB, IFRS9, stress) | Powiązany pośrednio | Brak |
| Automatyzacja | Pełna automatyzacja | Częściowa | Manual override |
| Skala populacji | > [X] klientów/transakcji | [X]–[Y] | < [Y] |
| Explainability | Wymagana regulatoryjnie | Zalecana | Opcjonalna |

---

## 3.5 Specyfika Kategorii Modeli a Tiering

### Modele regulacyjne
> ⚠️ **[REGULACYJNE]** Modele regulacyjne są automatycznie klasyfikowane jako **Tier 1**, niezależnie od wyników oceny pozostałych kryteriów. Wynika to z obowiązujących wytycznych EBA/KNF i wymogów Bazylei.

### Modele supervised
> 📋 **[SUPERVISED]** Tier modeli supervised zależy przede wszystkim od:
> - Skali i automatyzacji decyzji (scoring masowy = Tier 1/2)
> - Wpływu finansowego (modele pricing, reserves = Tier 1/2)
> - Zastosowania regulacyjnego (scoring w procesie IRB = Tier 1)

### Modele unsupervised
> 🔬 **[UNSUPERVISED]** Modele unsupervised są często Tier 2/3, ale mogą być Tier 1 gdy:
> - Segmentacja jest podstawą dla modeli regulacyjnych (np. segmenty do PD)
> - Model generuje alerty AML/fraud z materialnym wpływem na procesy KYC
> - Model jest wbudowany w pipeline automatycznych decyzji

---

## 3.6 Proces Klasyfikacji

1. **Inicjacja projektu** — DS i Model Owner wypełniają kartę klasyfikacji (→ TMPL-001)
2. **Wstępna klasyfikacja** — zaproponowany tier przez DS / team lead
3. **Zatwierdzenie tieru** — MRM potwierdza lub koryguje klasyfikację
4. **Rejestracja** — model trafia do inwentarza z przypisanym tierem
5. **Rewizja tieru** — możliwa w wyniku material change lub zmiany zastosowania

> 🔴 **OBOWIĄZKOWE** — Tier modelu musi być zatwierdzony przez MRM przed wdrożeniem.

---

## 3.7 Powiązane Dokumenty

- [Rozdział 5: Etapy Cyklu Życia](./05_etapy_cyklu_zycia.md) — wymagania per tier per etap
- [TMPL-001: Dokument Koncepcji Modelu](../03_templates/TMPL-001_dokument_koncepcji.md) — karta klasyfikacji
- [STD-005: Inwentarz Modeli](../01_supporting_standards/STD-005_inwentarz.md) — rejestracja tieru

---

*Poprzedni: [02 — Zasady Nadrzędne](./02_zasady_nadrzedne.md) | Następny: [04 — Przegląd Cyklu Życia](./04_przeglad_cyklu_zycia.md)*
