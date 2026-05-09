# Etap 5.3: Projektowanie i Budowa Modelu

> **Część:** Model Lifecycle Guide — Rozdział 5 (Etapy Lifecycle)  
> **Status:** Draft  
> **Powiązane dokumenty:** [MODEL_LIFECYCLE_GUIDE.md](../MODEL_LIFECYCLE_GUIDE.md) | [← Poprzedni: Dane](./02_pozyskanie_danych.md) | [Następny: Testowanie →](./04_testowanie_dokumentacja.md)

---

## Cel Etapu

Wybór metodologii modelowej, budowa modelu, bieżąca dokumentacja procesu, wewnętrzny code review oraz przygotowanie modelu do formalnego testowania i dokumentacji.

---

## Kto wykonuje

| Rola | Aktywność |
|------|-----------|
| **Data Scientist (lead)** | Projektowanie, implementacja, dokumentacja |
| **Data Scientist (peer)** | Code review, wsparcie metodologiczne |
| **Model Owner** | Weryfikacja postępu, zgodność z celem biznesowym |
| **IT / MLOps** | Wsparcie infrastrukturalne, code standards |

---

## Wejścia (Inputs)

- Data Assessment Report + Data Dictionary (z etapu 5.2)
- Model Concept Note (z etapu 5.1)
- Standardy deweloperskie (patrz: [Standard Developmentu](../../standards/development_standard.md))
- Wymagania regulacyjne (Kategoria A)

---

## Główne Aktywności

<!-- PROMPT DLA AUTORA:
Opisz szczegółowo proces budowy modelu przyjęty w organizacji.
Jak wygląda dokumentowanie założeń na bieżąco?
Jakie narzędzia do experiment tracking są stosowane (MLflow, itp.)?
Jaki jest standard kodu (Python/R, style guide, testy jednostkowe)?
-->

1. **Wybór i uzasadnienie metodologii** — porównanie podejść, wybór z uzasadnieniem
2. **Podział danych (train/validation/test)** — zgodnie z zasadami zapobiegania data leakage
3. **Feature engineering** — transformacje, selekcja zmiennych, dokumentacja decyzji
4. **Budowa i iteracja modelu** — trenowanie, tuning, porównanie wariantów
5. **Dokumentacja założeń i ograniczeń** — na bieżąco w Assumptions Register
6. **Experiment tracking** — rejestrowanie wszystkich eksperymentów i wyników
7. **Code review** — wewnętrzna weryfikacja kodu przez inny DS lub Tech Lead
8. **Pierwsze sekcje MDD** — przygotowanie draftu metodologicznego

---

## Wymagane Artefakty

| Artefakt | Opis | Obowiązkowość |
|----------|------|---------------|
| **Model Development Document (draft)** | Dokumentacja metodologii, danych, zmiennych, wyników | ✅ Obowiązkowy |
| **Assumptions Register** | Rejestr wszystkich kluczowych założeń i ich uzasadnień | ✅ Obowiązkowy |
| **Experiment Log** | Rejestr eksperymentów (MLflow lub równoważny) | ✅ Kat. C/D, zalecany dla B |
| **Code Repository** | Kod modelu pod kontrolą wersji, ukończony code review | ✅ Obowiązkowy |
| **Feature Documentation** | Dokumentacja użytych zmiennych, ich definicji i transformacji | ✅ Obowiązkowy |
| **Limitations Register** | Identyfikacja znanych ograniczeń modelu | ✅ Obowiązkowy |

---

## Minimalne Wymagania Dokumentacyjne dla MDD na tym Etapie

<!-- PROMPT DLA AUTORA:
Uzupełnij wymagania dokumentacyjne zgodnie z organizacyjnym standardem MDD.
Powiąż z szablonem MDD w katalogu templates/.
-->

### Sekcje MDD wymagane po etapie 5.3

- [ ] Opis celu modelu i problemu biznesowego
- [ ] Opis i ocena danych (z Data Assessment Report)
- [ ] Opis populacji modelowej (treningowej, targetowej)
- [ ] Metodologia — uzasadnienie wyboru podejścia
- [ ] Opis feature engineering i selekcji zmiennych
- [ ] Opis architektury / specyfikacji modelu
- [ ] Assumptions Register (zintegrowany lub jako załącznik)
- [ ] Znane ograniczenia i ryzyka

---

## Minimalne Standardy Kodowania

<!-- PROMPT DLA AUTORA:
Uzupełnij o standardy kodowania obowiązujące w organizacji.
Wskaż: język, linter, format, konwencje nazewnictwa, wymagania co do testów.
Powiąż z organizacyjnym Coding Standard.
-->

Kod modelu musi spełniać poniższe minimalne wymagania:

- [ ] Kod pod kontrolą wersji (Git) — od początku projektu
- [ ] Dokumentacja funkcji / klas (docstrings)
- [ ] Seed losowości ustawiony dla procedur stochastycznych
- [ ] Zależności udokumentowane (requirements.txt, environment.yml lub equivalent)
- [ ] Code review przez co najmniej jedną inną osobę przed etapem 5.4
- [ ] Brak hardcoded credentials i danych wrażliwych w kodzie
- [ ] Możliwość uruchomienia w środowisku deweloperskim (reproducibility)

---

## Kryteria Wyjścia — Stage Gate 3

- [ ] Draft MDD z sekcjami metodologicznymi ukończony
- [ ] Assumptions Register kompletny
- [ ] Kod zdeponowany w repozytorium, code review zakończony
- [ ] Model osiąga akceptowalne wyniki na zbiorze walidacyjnym
- [ ] Experiment log dostępny (Kategoria C/D)
- [ ] DS Lead / Tech Lead sign-off

---

## Specyfika według Kategorii Modelu

### Kategoria A — Regulacyjny

<!-- PROMPT DLA AUTORA:
Opisz specyficzne wymagania metodologiczne dla modeli regulacyjnych.
Np. wymogi EBA co do prób treningowych, Long-Run Average, MoC.
-->

- Udokumentowane podejście do Margin of Conservatism (MoC) jeśli wymagane
- Metodologia zgodna z EBA GL 2017/16 (PD/LGD) lub odpowiednimi wytycznymi
- Dokumentacja próby treningowej: reprezentatywność ekonomiczna, long-run average
- Testy na pełnych cyklach ekonomicznych jeśli dane dostępne

### Kategoria B — Scorecard

<!-- PROMPT DLA AUTORA:
Opisz wymagania metodologiczne dla scorecardów.
WoE, IV, binning, kalibracja.
-->

- Obowiązkowa analiza WoE (Weight of Evidence) i IV (Information Value)
- Dokumentacja procesu binningu i uzasadnienie wybranych przedziałów
- Test na korelację między zmiennymi (VIF lub równoważny)
- Kalibracja scorecardów do prawdopodobieństwa (jeśli wymagana)
- Dokumentacja odrzuconych zmiennych i powodów odrzucenia

### Kategoria C — Supervised ML

<!-- PROMPT DLA AUTORA:
Opisz pipeline ML: feature engineering, model selection, HPO, SHAP.
-->

- Obowiązkowe eksperymentowanie z co najmniej kilkoma algorytmami z uzasadnieniem wyboru
- Hyperparameter optimization z udokumentowaną procedurą
- Feature importance analysis — SHAP lub alternatywna metoda
- Bias & Fairness assessment — wstępny (przed testowaniem finalnym)
- Model Card — rozpoczęcie draftu

### Kategoria D — Unsupervised

<!-- PROMPT DLA AUTORA:
Opisz specyficzne decyzje przy budowie modeli unsupervised:
wybór liczby klastrów, algorytm, normalizacja.
-->

- Dokumentacja procesu wyboru algorytmu i jego parametrów (np. liczba klastrów)
- Uzasadnienie wyboru metody normalizacji i pre-processingu
- Testy stabilności — różne seedy, różne próby
- Ocena interpretowalności biznesowej segmentów / anomalii

---

## Najczęstsze Błędy na tym Etapie

<!-- PROMPT DLA AUTORA:
Uzupełnij o typowe błędy metodologiczne i procesowe w organizacji.
-->

- ❌ Data leakage — informacja z testu wpływa na trening (np. niepoprawny time split)
- ❌ Brak dokumentacji założeń "w locie" — trudne do odtworzenia po kilku tygodniach
- ❌ Overfitting bez walidacji na OOT (Out-of-Time) sample
- ❌ Wybór algorytmu bez uzasadnienia — "XGBoost bo zawsze działa"
- ❌ Pominięcie zmiennych dyskusyjnych bez dokumentacji decyzji

---

*Szablony: [Model Development Document Template](../../templates/), [Assumptions Register Template](../../templates/)*
