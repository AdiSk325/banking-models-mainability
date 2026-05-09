# Rozdział 3: Klasyfikacja i Tiering Modeli

> **Część:** Model Lifecycle Guide  
> **Status:** Draft — wymaga uzupełnienia merytorycznego  
> **Powiązane dokumenty:** [MODEL_LIFECYCLE_GUIDE.md](./MODEL_LIFECYCLE_GUIDE.md)

---

## Wprowadzenie

Klasyfikacja modeli jest fundamentem podejścia opartego na ryzyku (Risk-Based Approach). Poziom wymagań — zakres dokumentacji, intensywność walidacji, częstotliwość monitoringu, poziom komitetu akceptacyjnego — jest uzależniony od klasy ryzyka modelu.

Każdy model zarejestrowany w Model Inventory musi mieć przypisany Tier oraz kategorię funkcjonalną.

---

## 3.1 Framework Klasyfikacji

### Dwa wymiary klasyfikacji

Każdy model jest oceniany według dwóch niezależnych wymiarów:

1. **Tier ryzyka (1–3)** — określa poziom rygoryzmu procesowego
2. **Kategoria funkcjonalna** — określa specyfikę metodologiczną i regulacyjną

```
           Kategoria funkcjonalna
           ┌──────────┬──────────────┬────────────┬──────────────┐
           │Regulacyjny│Scorecard/Stat│Supervised  │Unsupervised  │
Tier ─┬────┼──────────┼──────────────┼────────────┼──────────────┤
      │ 1  │ IRB PD   │ Scoring      │ Fraud ML   │              │
      │    │ LGD/EAD  │ behawioralny │ Tier1      │              │
      ├────┼──────────┼──────────────┼────────────┼──────────────┤
      │ 2  │ IFRS9    │ App Scoring  │ Churn      │ Segmentacja  │
      │    │ Stress T.│ Kolekcyjny   │ XGBoost    │ klientów     │
      ├────┼──────────┼──────────────┼────────────┼──────────────┤
      │ 3  │          │ Rating       │ ML tools   │ Anomaly      │
      │    │          │ pomocniczy   │ analityczne│ exploration  │
      └────┴──────────┴──────────────┴────────────┴──────────────┘
```

---

## 3.2 Tier Ryzyka Modelu

### Tier 1 — Krytyczny

<!-- PROMPT DLA AUTORA:
Uzupełnij o specyficzne przykłady modeli Tier 1 z organizacji.
Opisz konkretne konsekwencje klasyfikacji jako Tier 1:
jakie dodatkowe wymagania, jaka częstotliwość walidacji, jaki komitet.
-->

**Definicja:** Modele o bezpośrednim, istotnym wpływie na:
- Sprawozdawczość regulacyjną lub wyliczenia wymogów kapitałowych
- Decyzje z potencjalnie wysokim wpływem finansowym lub prawnym
- Automatyczne decyzje klientowskie w dużej skali

**Kryteria Tier 1 (spełnienie co najmniej jednego):**
- [ ] Zasila obowiązkową sprawozdawczość regulacyjną (COREP, FINREP, itp.)
- [ ] Wpływ błędu > [PLACEHOLDER: próg finansowy do uzupełnienia przez organizację] PLN
- [ ] Pokrywa > [PLACEHOLDER: %] klientów lub wolumenu portfela
- [ ] Automatyczna decyzja kredytowa bez interwencji człowieka
- [ ] Klasyfikacja przez nadzorcę jako model wewnętrzny (IRB, IRRBB)

**Wymagania dla Tier 1:**

| Obszar | Wymaganie |
|--------|-----------|
| Dokumentacja | Pełny Model Development Document |
| Walidacja | Pełna niezależna walidacja przed wdrożeniem |
| Re-walidacja | Co najmniej raz na rok lub przy każdej materialnej zmianie |
| Monitoring | Miesięczny lub kwartalny, raport do komitetu |
| Komitet akceptacji | Wymagana akceptacja [PLACEHOLDER: nazwa komitetu] |
| Przegląd dokumentacji | Co najmniej raz na rok |
| Archiwizacja | Zachowanie wszystkich wersji modelu i dokumentacji |

---

### Tier 2 — Istotny

<!-- PROMPT DLA AUTORA:
Uzupełnij o przykłady modeli Tier 2 z organizacji.
Wskaż jakie uproszczenia są możliwe w stosunku do Tier 1.
-->

**Definicja:** Modele o istotnym wpływie na procesy biznesowe, decyzje klientowskie lub ocenę ryzyka, nieposiadające cech klasyfikujących do Tier 1.

**Kryteria Tier 2 (spełnienie co najmniej jednego):**
- [ ] Wpływa na indywidualne decyzje kredytowe lub cenowe
- [ ] Zasila procesy zarządzania ryzykiem lub kontroli
- [ ] Pokrywa znaczącą (ale mniejszą niż Tier 1) część portfela
- [ ] Stosowany regularnie w procesach produkcyjnych

**Wymagania dla Tier 2:**

| Obszar | Wymaganie |
|--------|-----------|
| Dokumentacja | Model Development Document (zakres standardowy) |
| Walidacja | Niezależna walidacja przed wdrożeniem |
| Re-walidacja | Co najmniej raz na 2 lata lub przy materialnej zmianie |
| Monitoring | Kwartalny lub półroczny |
| Komitet akceptacji | [PLACEHOLDER: nazwa komitetu lub MRM] |
| Przegląd dokumentacji | Co 2 lata lub przy zmianie |

---

### Tier 3 — Niski Wpływ

<!-- PROMPT DLA AUTORA:
Uzupełnij o przykłady modeli Tier 3.
Opisz uproszczoną ścieżkę i jakie elementy są obowiązkowe nawet dla Tier 3.
-->

**Definicja:** Modele analityczne, pomocnicze lub badawcze o ograniczonym wpływie na decyzje biznesowe, ryzyko lub klientów.

**Kryteria Tier 3 (wszystkie muszą być spełnione):**
- [ ] Brak bezpośredniego wpływu na decyzje klientowskie
- [ ] Brak zastosowania w sprawozdawczości regulacyjnej
- [ ] Ograniczony wpływ finansowy w przypadku błędu
- [ ] Stosowany jako narzędzie pomocnicze, nie produkcyjne

**Wymagania dla Tier 3:**

| Obszar | Wymaganie |
|--------|-----------|
| Dokumentacja | Uproszczona dokumentacja modelu |
| Walidacja | Weryfikacja wewnętrzna (niekoniecznie niezależna) |
| Re-walidacja | Przy istotnej zmianie lub co 3 lata |
| Monitoring | Według potrzeb |
| Komitet akceptacji | MRM lub uproszczona ścieżka |

> ⚠️ **Minimalne wymagania niezależne od Tiera:** Rejestracja w Model Inventory, przypisanie Model Ownera, podstawowa dokumentacja.

---

## 3.3 Kategorie Funkcjonalne Modeli

Każdy model jest additionally klasyfikowany według kategorii funkcjonalnej, która określa specyficzne wymagania metodologiczne i dokumentacyjne.

### Kategoria A: Modele Regulacyjne

<!-- PROMPT DLA AUTORA:
Opisz specyficzne wymagania dokumentacyjne i walidacyjne dla tej kategorii.
Wymień konkretne regulacje i co z nich wynika dla procesu lifecycle.
-->

**Definicja:** Modele, których wyniki bezpośrednio zasilają obowiązkowe obliczenia regulacyjne lub sprawozdawczość.

**Typy modeli:**

| Typ | Zastosowanie | Kluczowa regulacja |
|-----|-------------|-------------------|
| PD (Probability of Default) | Wymogi kapitałowe IRB | CRR Art. 143–191, ECB TRIM |
| LGD (Loss Given Default) | Wymogi kapitałowe IRB | CRR, EBA GL 2017/16 |
| EAD (Exposure at Default) | Wymogi kapitałowe IRB | CRR, EBA GL 2017/16 |
| IFRS9 ECL | Rezerwy rachunkowe | IFRS 9, EBA GL |
| Stage Assignment | Klasyfikacja ekspozycji IFRS9 | IFRS 9 |
| Stress-testing | ICAAP, SREP | CRD IV Art. 97, EBA |

**Dodatkowe wymagania dla Kategorii A:**
- Mapowanie wymagań modelu do konkretnych artykułów regulacyjnych
- Udokumentowanie interpretacji regulacyjnych (Assumptions Register)
- Dokumentacja zmian regulacyjnych i ich wpływu na model
- Możliwość przedstawienia historii decyzji modelowych regulatorowi

**Specyficzne wymogi lifecycle:**

| Etap | Specyfika dla modeli regulacyjnych |
|------|------------------------------------|
| Inicjacja | Wymóg analizy regulacyjnej (regulatory mapping) |
| Walidacja | Zgodność z EBA/ECB guidelines jako kryterium |
| Zmiana | Ocena czy zmiana wymaga powiadomienia regulatora |
| Monitoring | Reporting do komitetu z odniesieniem do wymogów regulacyjnych |

---

### Kategoria B: Modele Statystyczne / Scorecard

<!-- PROMPT DLA AUTORA:
Opisz metodologię scorecardów (WoE, IV, binning).
Wskaż specyficzne wymogi explainability dla scorecardów vs. ML.
Odwołaj się do wymogów consumer disclosure / RODO.
-->

**Definicja:** Modele oparte na metodologii scorecardowej lub klasycznej statystycznej (regresja logistyczna, WoE), typowo stosowane w procesach decyzyjnych dla klientów detalicznych.

**Typy modeli:**

| Typ | Zastosowanie |
|-----|-------------|
| Scoring aplikacyjny | Decyzja kredytowa przy wniosku |
| Scoring behawioralny | Zarządzanie limitami, monitoring portfela |
| Scoring kolekcyjny | Strategie windykacyjne |
| Rating wewnętrzny | Ocena klienta korporacyjnego |

**Specyfika metodologiczna:**
- Transformacja zmiennych: Weight of Evidence (WoE)
- Selekcja zmiennych: Information Value (IV), test statystyczny
- Binning: grupowanie przedziałów dla cech ciągłych
- Kalibracja: mapowanie punktów scoringowych na prawdopodobieństwo

**Wymagania explainability dla Kategorii B:**
- Dokumentacja wag i przedziałów WoE
- Możliwość wygenerowania wyjaśnienia decyzji na poziomie klienta
- Uzasadnienie dla odrzucenia wniosku (RODO art. 22 — prawo do wyjaśnienia)
- Test czy zmienne stosowane są dopuszczalne prawnie (brak zmiennych dyskryminujących)

---

### Kategoria C: Modele Nadzorowane (Supervised ML)

<!-- PROMPT DLA AUTORA:
Opisz specyficzne wyzwania modeli ML w bankowym środowisku regulacyjnym.
Wymagania explainability (SHAP/LIME), bias testing, model cards.
Wskaż różnicę w podejściu do walidacji vs. modele klasyczne.
-->

**Definicja:** Modele uczenia maszynowego nadzorowanego, gdzie zbiór treningowy zawiera etykiety wynikowe, stosowane w procesach ryzyka lub biznesowych.

**Typy modeli:**

| Typ | Zastosowanie |
|-----|-------------|
| Gradient Boosting (XGBoost, LightGBM) | Scoring kredytowy, fraud |
| Random Forest | Credit risk, retention |
| Neural Networks | Fraud detection, NLP |
| Ensemble methods | Prediction, risk models |

**Dodatkowe wymagania dla Kategorii C:**

| Obszar | Wymaganie |
|--------|-----------|
| Explainability | Obligatoryjna analiza SHAP lub LIME |
| Bias & Fairness | Test dyskryminacji na chronionych cechach |
| Model Card | Uzupełnienie MDD o Model Card (patrz szablon) |
| Monitoring driftu | Monitoring driftu konceptualnego i danych |
| Feature importance | Udokumentowana lista i uzasadnienie cech |

**Specyfika lifecycle dla Kategorii C:**

| Etap | Specyfika dla Supervised ML |
|------|-----------------------------|
| Budowa | Dokumentacja pipeline'u (feature engineering → model → output) |
| Testowanie | Testy na hold-out set, cross-validation, OOT (Out-of-Time) |
| Walidacja | Ocena wyjaśnialności i bias jako obowiązkowe |
| Monitoring | Monitoring feature drift + prediction drift |

---

### Kategoria D: Modele Nienadzorowane (Unsupervised ML)

<!-- PROMPT DLA AUTORA:
Opisz wyzwania walidacji modeli bez etykiet (brak "prawdy gruntowej").
Metodologia oceny jakości: silhouette score, business evaluation, stability.
Specyfika monitoringu segmentów / anomalii w czasie.
-->

**Definicja:** Modele uczenia maszynowego nienadzorowanego, gdzie zbiór treningowy nie zawiera etykiet wynikowych.

**Typy modeli:**

| Typ | Zastosowanie |
|-----|-------------|
| Clustering (k-means, DBSCAN) | Segmentacja klientów |
| Anomaly Detection (Isolation Forest, AE) | Fraud, AML |
| Dimensionality Reduction (PCA, UMAP) | Feature engineering, wizualizacja |
| Association Rules | Cross-sell, basket analysis |

**Wyzwania specyficzne dla Kategorii D:**
- **Brak prawdy gruntowej** — niemożliwa bezpośrednia ocena trafności predykcji
- **Ocena jakości wymaga podejścia wielowymiarowego:**
  - Kryteria wewnętrzne: Silhouette Score, Davies-Bouldin Index
  - Ocena biznesowa: Czy segmenty są interpretowalnie sensowne?
  - Stabilność w czasie: Czy podział jest stabilny?
  - Profilowalność: Czy segmenty różnią się mierzalnie?

**Wymagania walidacji dla Kategorii D:**

| Element | Podejście |
|---------|-----------|
| Conceptual soundness | Ocena zasadności metodologicznej wyboru algorytmu |
| Outcomes analysis | Ocena biznesowej sensowności wyników |
| Stability testing | Sprawdzenie stabilności segmentów w czasie |
| Sensitivity analysis | Wrażliwość wyników na hiperparametry |
| Monitoring plan | Jak monitoring ewolucji segmentów będzie wyglądał |

**Specyfika lifecycle dla Kategorii D:**

| Etap | Specyfika dla Unsupervised ML |
|------|-------------------------------|
| Inicjacja | Uzasadnienie biznesowe — co model ma "odkryć" / rozwiązać |
| Budowa | Dokumentacja podejść próbowanych i kryteriów wyboru |
| Walidacja | Brak backtestu tradycyjnego — ocena jakości wielowymiarowa |
| Monitoring | Tracking stabilności segmentów, anomaly rate, feature drift |

---

## 3.4 Macierz Wymogów: Tier × Kategoria

<!-- PROMPT DLA AUTORA:
Uzupełnij macierz o progi liczbowe i konkretne wymagania obowiązujące w organizacji.
Dostosuj do struktury komitetów i ścieżek akceptacji.
-->

| Wymóg | Tier 1 / Kat. A (Regulacyjny) | Tier 1–2 / Kat. B (Scorecard) | Tier 2 / Kat. C (Supervised ML) | Tier 2–3 / Kat. D (Unsupervised) |
|-------|-------------------------------|-------------------------------|----------------------------------|-----------------------------------|
| Pełny MDD | ✅ Obowiązkowy | ✅ Obowiązkowy | ✅ Obowiązkowy | ✅ Wymagany (zakres dostosowany) |
| Regulatory Mapping | ✅ Obowiązkowy | ⚠️ Jeśli dotyczy | ⚠️ Jeśli dotyczy | ❌ Typowo nie dotyczy |
| Niezależna walidacja | ✅ Pełna | ✅ Pełna | ✅ Pełna | ✅ Wymagana (metodologia dostosowana) |
| SHAP/explainability | ⚠️ Jeśli ML | ⚠️ WoE/scorecard cards | ✅ Obowiązkowy | ⚠️ Jeśli możliwy |
| Bias/Fairness test | ✅ Obowiązkowy | ✅ Obowiązkowy | ✅ Obowiązkowy | ✅ Obowiązkowy |
| Model Card | ❌ | ⚠️ Opcjonalny | ✅ Obowiązkowy | ✅ Obowiązkowy |
| Monitoring miesięczny | ✅ | ✅ | ✅ | ⚠️ Kwartalny |
| Drift monitoring | ⚠️ Jeśli ML | ⚠️ PSI/CSI wymagane | ✅ Obowiązkowy | ✅ Obowiązkowy |
| Komitet akceptacji | Wyższy komitet | Standardowy | Standardowy | Uproszczony |
| Re-walidacja (freq.) | ≤ 1 rok | ≤ 2 lata | ≤ 2 lata | ≤ 3 lata |

---

## 3.5 Proces Klasyfikacji

<!-- PROMPT DLA AUTORA:
Opisz krok po kroku jak model jest klasyfikowany.
Wskaż kto podejmuje decyzję o klasyfikacji.
Jak postępować w przypadku wątpliwości?
Jak przebiega zmiana klasyfikacji?
-->

### Krok 1: Wstępna samoocena (Data Scientist)

Przed formalną rejestracją, Data Scientist wypełnia wstępną ocenę ryzyka modelu, odpowiadając na pytania klasyfikacyjne (patrz szablon: [../templates/model_risk_assessment_form.md](../templates/model_risk_assessment_form.md)).

### Krok 2: Formalna klasyfikacja (MRM)

Model Risk Management weryfikuje propozycję klasyfikacji i podejmuje decyzję na podstawie:
- Wyników wstępnej samooceny
- Znajomości portfela modeli organizacji
- Oceny materialności potencjalnego wpływu

### Krok 3: Rejestracja w Model Inventory

Po klasyfikacji, model jest rejestrowany z przypisanym Tier i Kategorią.

### Krok 4: Przegląd klasyfikacji

Klasyfikacja podlega przeglądowi:
- Przy każdej materialnej zmianie zakresu stosowania modelu
- Przy corocznym przeglądzie Model Inventory
- Na wniosek walidatora, auditora lub MRM

---

*Następny rozdział: [04_przeglad_cyklu_zycia.md — Przegląd Cyklu Życia](./04_przeglad_cyklu_zycia.md)*
