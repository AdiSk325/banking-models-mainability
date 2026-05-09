# Rozdział 1: Cel, Zakres i Odbiorcy

> **Część:** Model Lifecycle Guide  
> **Status:** Draft — wymaga uzupełnienia merytorycznego  
> **Powiązane dokumenty:** [MODEL_LIFECYCLE_GUIDE.md](./MODEL_LIFECYCLE_GUIDE.md)

---

## 1.1 Cel Dokumentu

<!-- PROMPT DLA AUTORA:
Opisz w 2-4 akapitach:
- Dlaczego ten dokument istnieje (problem, który rozwiązuje)
- Jak wpisuje się w strukturę zarządzania ryzykiem modelowym organizacji
- Czym NIE jest (nie jest proceduralnym SOP-em ani instrukcją techniczną)
- Jak należy go stosować w praktyce
Przykładowe zdanie otwierające: "Model Lifecycle Guide stanowi nadrzędny framework..."
-->

Model Lifecycle Guide stanowi nadrzędny framework zarządzania cyklem życia modeli w organizacji. Dokument ten określa zasady, wymagania minimalne oraz punkty kontrolne obowiązujące na każdym etapie procesu — od inicjacji modelu, przez jego budowę, walidację i wdrożenie, aż po monitoring, zarządzanie zmianą i wycofanie.

Przewodnik pełni rolę **konstytucji pracy z modelami**: definiuje, co musi się wydarzyć i kto za to odpowiada, natomiast szczegółowe instrukcje jak to zrobić zawarte są w dedykowanych standardach i procedurach, do których ten dokument odsyła.

**Czym NIE jest ten dokument:**
- Nie jest instrukcją krok po kroku dla poszczególnych analiz
- Nie zawiera technicznych instrukcji obsługi narzędzi
- Nie zastępuje standardów walidacji, monitoringu ani procedur MLOps

---

## 1.2 Definicja Modelu

<!-- PROMPT DLA AUTORA:
Podaj oficjalną definicję modelu przyjętą w organizacji.
Powinna być spójna z definicją z SR 11-7 lub analogicznego dokumentu regulacyjnego.
Wskaż kryteria pozwalające odróżnić "model" od "kalkulacji" lub "narzędzia analitycznego".
Dodaj przykłady graniczne.
-->

### Definicja podstawowa

Na potrzeby niniejszego przewodnika, **model** definiuje się jako:

> *Metodę ilościową, system lub podejście, które przetwarza dane wejściowe i generuje oszacowania ilościowe, predykcje lub decyzje, przy czym wyniki te mogą być istotne dla procesów decyzyjnych, oceny ryzyka lub sprawozdawczości regulacyjnej organizacji.*

Definicja jest spójna z wytycznymi SR 11-7 (US Federal Reserve, 2011) oraz EBA Guidelines on Model Risk Management (2023).

### Trzy komponenty modelu

Każdy model składa się z:
1. **Komponentu informacyjnego (input)** — dane wejściowe i założenia
2. **Komponentu przetwarzania (processing)** — metodologia, algorytmy, transformacje
3. **Komponentu wynikowego (output)** — predykcje, oszacowania, decyzje

### Kiedy "narzędzie" jest modelem?

<!-- PROMPT DLA AUTORA:
Uzupełnij poniższą tabelę o przykłady z własnej organizacji.
Kryteria: materialność wyników, automatyzacja decyzji, złożoność metodologiczna, wymaganie walidacji.
-->

| Przykład | Klasyfikacja | Uzasadnienie |
|----------|-------------|--------------|
| Model PD dla portfela IRB | ✅ Model | Materialny wpływ regulacyjny i finansowy |
| Scoring aplikacyjny | ✅ Model | Automatyczna decyzja kredytowa |
| Kalkulator amortyzacji | ❌ Nie-model | Algorytm deterministyczny, brak niepewności |
| Segmentacja klientów ML | ✅ Model | Niepewność metodologiczna, wpływ na decyzje |
| Prosta reguła decyzyjna | ⚠️ Do oceny | Zależy od złożoności i materialności wpływu |

---

## 1.3 Zakres Zastosowania

### Typy modeli objęte przewodnikiem

Ten przewodnik obejmuje wszystkie modele produkowane lub stosowane w organizacji, z podziałem na cztery kategorie:

#### Kategoria 1: Modele Regulacyjne

<!-- PROMPT DLA AUTORA:
Uzupełnij o specyfikę lokalną (regulacje KNF, wymogi kapitałowe EBC/EBA).
Opisz poziom rygoryzmu wymagany dla tej kategorii.
-->

Modele bezpośrednio zasilające sprawozdawczość regulacyjną lub wyliczenia wymogów kapitałowych.

**Przykłady:**
- Modele PD (Probability of Default) w podejściu IRB
- Modele LGD (Loss Given Default) i EAD (Exposure at Default)
- Modele IFRS9 — wyliczanie ECL (Expected Credit Loss), alokacja do Stage 1/2/3
- Modele kapitału regulacyjnego (Basel III/IV RWA)
- Modele stress-testingowe (ICAAP, SREP)

**Specyfika dla Data Scientist:**
- Najwyższy poziom wymogów dokumentacyjnych
- Obowiązkowa niezależna walidacja przed wdrożeniem i przy każdej materialnej zmianie
- Wymogi traceability do regulacji (SR 11-7, EBA, ECB TRIM, KNF)
- Archiwizacja wszystkich wersji i historii decyzji

#### Kategoria 2: Modele Statystyczne / Scorecard

<!-- PROMPT DLA AUTORA:
Opisz specyfikę scorecardów: WoE, IV, metodologia budowy, wymagania wyjaśnialności.
Uwzględnij scoring aplikacyjny, behawioralny, kolekccyjny.
-->

Modele oparte na metodologii scorecardowej lub statystycznej, stosowane w procesach decyzyjnych.

**Przykłady:**
- Scoring aplikacyjny (kredyty hipoteczne, gotówkowe, karty)
- Scoring behawioralny (zarządzanie limitami, monitoring)
- Scoring kolekcyjny (windykacja, recovery)
- Modele ratingowe (wewnętrzne ratingi klientów)

**Specyfika dla Data Scientist:**
- Wymóg wyjaśnialności (bias-free, dokumentacja WoE/IV)
- Regularne monitorowanie stabilności (PSI, CSI)
- Uzasadnienie zastosowania w kontekście Consumer Duty / RODO
- Dokumentacja zmiennych i procesu selekcji cech

#### Kategoria 3: Modele Nadzorowane (Supervised ML)

<!-- PROMPT DLA AUTORA:
Opisz specyficzne wymogi dla modeli ML nadzorowanych w bankowości:
explainability (SHAP/LIME), bias detection, model cards, dodatkowe wymogi governance.
Wskaż gdzie kończy się scorecard a zaczyna "czarna skrzynka".
-->

Modele uczenia maszynowego nadzorowanego stosowane w zastosowaniach biznesowych i ryzyka.

**Przykłady:**
- Modele XGBoost/GBM dla ryzyka kredytowego
- Modele predykcji churn/retencji klientów
- Modele fraud detection (klasyfikacja transakcji)
- Modele early warning dla niespłacalności

**Specyfika dla Data Scientist:**
- Obowiązkowa analiza wyjaśnialności (SHAP, LIME lub metody alternatywne)
- Obowiązkowy test na bias i dyskryminację (fairness assessment)
- Dodatkowe wymogi monitoringu driftu konceptualnego i danych
- Model Card jako uzupełnienie standardowej dokumentacji

#### Kategoria 4: Modele Nienadzorowane (Unsupervised ML)

<!-- PROMPT DLA AUTORA:
Opisz specyficzne wyzwania dla modeli unsupervised:
brak "prawdy gruntowej", ocena jakości, walidacja koncepcyjna, monitoring.
-->

Modele uczenia maszynowego nienadzorowanego lub semi-nadzorowanego.

**Przykłady:**
- Segmentacja klientów (clustering: k-means, DBSCAN)
- Anomaly detection (AE, Isolation Forest)
- Redukcja wymiarowości (PCA, UMAP) w pipeline'ach decyzyjnych
- Embeddingi behawioralne klientów

**Specyfika dla Data Scientist:**
- Brak jednoznacznej "prawdy gruntowej" — walidacja wymaga innego podejścia
- Ocena stabilności i sens biznesowy wyników jako kryterium jakości
- Monitoring ewolucji segmentów / anomalii w czasie
- Dokumentacja kryteriów oceny jakości (silhouette score, business evaluation)

---

### Modele wyłączone z zakresu

<!-- PROMPT DLA AUTORA:
Uzupełnij o wyłączenia specyficzne dla organizacji.
Typowe wyłączenia: narzędzia analityczne bez wpływu na decyzje, modele vendor z pełnym outsourcingiem governance.
Pamiętaj: nawet modele vendor wymagają podstawowego nadzoru.
-->

Z zakresu niniejszego przewodnika **wyłączone** są:
- Kalkulacje deterministyczne bez niepewności metodologicznej (np. amortyzacja liniowa)
- Arkusze kalkulacyjne do jednorazowych analiz ad-hoc bez wdrożenia produkcyjnego
- Modele w pełni outsourcowane do dostawcy zewnętrznego — *pod warunkiem zawarcia odpowiednich wymogów governance w umowie z dostawcą*

> ⚠️ **Uwaga:** Modele vendor (dostawców zewnętrznych) nie są wyłączone z obowiązku rejestracji w Model Inventory ani podstawowego nadzoru.

---

## 1.4 Odbiorcy Dokumentu

### Główni odbiorcy i jak korzystać z przewodnika

| Rola | Jak korzystać | Kluczowe rozdziały |
|------|--------------|-------------------|
| **Data Scientist / Deweloper** | Przewodnik procesu pracy — co zrobić na każdym etapie | 4, 5 (etapy), 7 |
| **Model Owner** | Punkt odniesienia dla obowiązków i decyzji | 5 (stage gates), 6, 8 |
| **Niezależny Walidator** | Wymagania walidacji i zakres oceny | 5.5, 7, 8 |
| **Model Risk Management** | Framework governance i kontroli | 2, 3, 8, 9 |
| **IT / MLOps** | Wymagania wdrożeniowe i kontrole infrastruktury | 5.7, 9 |
| **Compliance / Audit** | Wymagania zgodności i dokumentacja | 2, 8, 9 |
| **Komitety / Zarząd** | Oversight — zasady i punkty decyzyjne | 2, 3, 8 |

---

## 1.5 Relacja do Innych Dokumentów

<!-- PROMPT DLA AUTORA:
Opisz jak ten przewodnik wpisuje się w szerszy ekosystem dokumentów organizacji.
Wymień dokumenty nadrzędne (polityki) i podrzędne (standardy, procedury).
Wskaż czy istnieje Model Risk Policy w organizacji i do czego odsyła.
-->

```
Model Risk Policy (Polityka zarządzania ryzykiem modelowym)
        ↓
Model Lifecycle Guide ← TEN DOKUMENT
        ↓
┌──────────────────────────────────────────────┐
│ Standardy:                                   │
│ • Standard Developmentu Modeli               │
│ • Standard Dokumentacji Modeli               │
│ • Standard Walidacji Modeli                  │
│ • Standard Monitoringu Modeli                │
│ • Standard Change Management                 │
│ • Standard MLOps / Wdrożeń                   │
└──────────────────────────────────────────────┘
        ↓
┌──────────────────────────────────────────────┐
│ Procedury:                                   │
│ • Procedura Niezależnej Walidacji            │
│ • Procedura Rejestracji w Model Inventory    │
│ • Procedura Zarządzania Zmianą               │
│ • Procedura Wycofania Modelu                 │
└──────────────────────────────────────────────┘
        ↓
┌──────────────────────────────────────────────┐
│ Szablony i narzędzia:                        │
│ • Model Development Document (MDD)           │
│ • Raport Walidacyjny                         │
│ • Plan Monitoringu                           │
│ • Formularz Zmiany Modelu                    │
│ • Checklista Release Readiness               │
└──────────────────────────────────────────────┘
```

---

*Następny rozdział: [02_zasady_nadrzedne.md — Zasady Nadrzędne](./02_zasady_nadrzedne.md)*
