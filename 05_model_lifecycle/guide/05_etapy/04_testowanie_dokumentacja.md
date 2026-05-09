# Etap 5.4: Testowanie i Dokumentacja

> **Część:** Model Lifecycle Guide — Rozdział 5 (Etapy Lifecycle)  
> **Status:** Draft  
> **Powiązane dokumenty:** [MODEL_LIFECYCLE_GUIDE.md](../MODEL_LIFECYCLE_GUIDE.md) | [← Poprzedni: Budowa](./03_projektowanie_rozwoj.md) | [Następny: Walidacja →](./05_walidacja_niezalezna.md)

---

## Cel Etapu

Kompleksowe przetestowanie modelu na zbiorze testowym (hold-out), weryfikacja jakości dokumentacji oraz finalizacja wszystkich artefaktów wymaganych przed niezależną walidacją. Etap ten zamyka prace deweloperskie.

---

## Kto wykonuje

| Rola | Aktywność |
|------|-----------|
| **Data Scientist** | Przeprowadzenie testów, finalizacja dokumentacji |
| **Model Owner** | Weryfikacja kompletności, akceptacja do walidacji |
| **DS Lead / QA** | Wewnętrzna weryfikacja jakości |

---

## Główne Aktywności

<!-- PROMPT DLA AUTORA:
Opisz szczegółowo wymagany zakres testów w organizacji.
Które testy są obowiązkowe dla każdej kategorii modelu?
Jak wygląda formalna procedura QA przed walidacją?
-->

1. **Testy na zbiorze testowym (hold-out)** — ocena performance na danych nie widzianych
2. **Out-of-Time (OOT) validation** — ocena performance na późniejszym oknie czasowym
3. **Testy stabilności** — PSI, CSI dla scorecardów; drift metrics dla ML
4. **Testy sensu wynikowego** — czy wyniki są biznesowo sensowne?
5. **Testy graniczne i brzegowe** — zachowanie modelu dla skrajnych wartości wejść
6. **Testy bias/fairness** — ocena dyskryminacji dla chronionych grup (Kat. B, C)
7. **Testy explainability** — SHAP analysis dla Kat. C
8. **Finalizacja MDD** — kompletny Model Development Document
9. **Kompletność Assumptions Register**
10. **Wewnętrzna QA** — DS Lead lub wyznaczona osoba przegląda całość
11. **Approval Gate 4** — Model Owner akceptuje do przesłania do walidacji

---

## Wymagane Artefakty (do walidacji)

| Artefakt | Opis | Obowiązkowość |
|----------|------|---------------|
| **Model Development Document (finalny)** | Pełna dokumentacja modelu | ✅ Obowiązkowy |
| **Test Results Report** | Wyniki wszystkich przeprowadzonych testów | ✅ Obowiązkowy |
| **OOT Validation Results** | Wyniki na zbiorze Out-of-Time | ✅ Obowiązkowy (Kat. A, B, C) |
| **Assumptions Register (finalny)** | Kompletny rejestr założeń | ✅ Obowiązkowy |
| **Limitations Register** | Zidentyfikowane ograniczenia modelu | ✅ Obowiązkowy |
| **SHAP / Explainability Analysis** | Analiza wyjaśnialności | ✅ Kat. C; ⚠️ Kat. A jeśli ML |
| **Bias & Fairness Assessment** | Wyniki testów na dyskryminację | ✅ Kat. B, C |
| **Model Card (draft)** | Skrócona karta modelu | ✅ Kat. C, D |
| **Code + Documentation** | Kod + komentarze, repozytorium | ✅ Obowiązkowy |
| **Approval Record (Gate 4)** | Model Owner sign-off | ✅ Obowiązkowy |

---

## Minimalne Metryki Testowe według Kategorii

<!-- PROMPT DLA AUTORA:
Uzupełnij o minimalne progi akceptacji metryk obowiązujące w organizacji.
Każda organizacja ma swoje progi — pozostaw [PLACEHOLDER] do uzupełnienia.
-->

### Modele klasyfikacyjne (PD, scoring, ML binary)

| Metryka | Opis | Minimalny próg |
|---------|------|----------------|
| AUROC / Gini | Discriminatory power | ≥ [PLACEHOLDER] |
| KS Statistic | Separation measure | ≥ [PLACEHOLDER] |
| PSI (In-Sample vs OOT) | Stability | ≤ 0.2 (alarmowy), ≤ 0.1 (dobry) |
| Brier Score | Calibration quality | ≤ [PLACEHOLDER] |
| Hosmer-Lemeshow | Calibration test | p ≥ [PLACEHOLDER] |

### Modele regresyjne (LGD, pricing)

| Metryka | Opis | Minimalny próg |
|---------|------|----------------|
| R² / Adjusted R² | Explained variance | ≥ [PLACEHOLDER] |
| RMSE / MAE | Prediction error | ≤ [PLACEHOLDER] |
| Residual analysis | Pattern in errors | Brak systematycznego wzorca |
| OOT performance | Stability across time | Degradacja ≤ [PLACEHOLDER]% |

### Modele klastrowania (Unsupervised)

| Metryka | Opis | Akceptowalny zakres |
|---------|------|---------------------|
| Silhouette Score | Cluster cohesion | ≥ [PLACEHOLDER] |
| Davies-Bouldin Index | Cluster separation | ≤ [PLACEHOLDER] |
| Inertia (k-means) | Within-cluster variance | Elbow method |
| Business evaluation | Sensowność biznesowa | Ocena ekspercka |

---

## Testy Bias & Fairness — Zakres Minimalny

<!-- PROMPT DLA AUTORA:
Opisz obowiązkowy zakres testów bias w organizacji.
Jakie cechy chronione są testowane? Jaka metodologia (disparate impact, equalized odds)?
-->

Dla modeli stosowanych w decyzjach klientowskich (Kategoria B, C):

- [ ] Identyfikacja cech potencjalnie korelujących z chronionymi atrybutami
- [ ] Disparate Impact Analysis dla głównych grup chronionych
- [ ] Equalized Odds lub podobna metryka jeśli dotyczy
- [ ] Dokumentacja wyników i wniosków
- [ ] Decyzja o akceptacji ryzyka lub mitygacji

---

## Kryteria Wyjścia — Stage Gate 4

- [ ] Wszystkie obowiązkowe artefakty ukończone i dostępne
- [ ] Metryki performance spełniają minimalne progi
- [ ] Testy OOT zaliczone
- [ ] Bias & Fairness assessment zakończony (Kat. B, C)
- [ ] SHAP/explainability ukończony (Kat. C)
- [ ] DS Lead wewnętrzna QA zakończona
- [ ] Model Owner sign-off do przesłania do walidacji

---

## Najczęstsze Błędy na tym Etapie

- ❌ Przekazanie do walidacji niekompletnej dokumentacji
- ❌ Brak OOT testu — niemożliwa ocena stabilności temporalnej
- ❌ Optymistyczne metryki na train/val bez holdout
- ❌ Testy bias pominięte jako "nieistotne"
- ❌ MDD napisany "po fakcie" bez odzwierciedlenia faktycznego procesu

---

*Szablony: [Model Development Document Template](../../templates/), [Test Results Template](../../templates/)*
