# Rozdział 1: Cel, Zakres i Odbiorcy

> **Status:** 🔄 Szkielet — wymaga uzupełnienia treścią merytoryczną  
> **Priorytet uzupełnienia:** Wysoki

---

## 1.1 Cel Przewodnika

**Model Lifecycle Guide** jest nadrzędnym dokumentem ramowym określającym zasady, etapy, role, obowiązki i wymagania dotyczące pracy z modelami analitycznymi w bankowości.

Dokument pełni rolę **„konstytucji"** pracy Data Scientistów i innych uczestników procesu modelarskiego — jest punktem odniesienia, do którego podłączone są szczegółowe procedury, standardy i metodologie.

### Cele szczegółowe
- Zapewnić jednolite, risk-based podejście do zarządzania modelami w całym cyklu życia
- Stanowić nawigację dla Data Scientistów w codziennej pracy z modelami
- Definiować minimalne wymagania jakościowe i governance dla wszystkich typów modeli
- Integrować wymagania regulacyjne, biznesowe i techniczne w spójny framework
- Odsyłać do szczegółowych procedur i standardów zamiast je duplikować

> 🔴 **OBOWIĄZKOWE** — Każdy Data Scientist pracujący z modelami w banku jest zobowiązany do zapoznania się z tym przewodnikiem i przestrzegania zawartych w nim zasad.

---

## 1.2 Zakres

### 1.2.1 Definicja modelu

> ✍️ **[DO UZUPEŁNIENIA]** Wpisać tu oficjalną definicję modelu obowiązującą w organizacji.  
> Zalecana referencyjna definicja (na podstawie SR 11-7):  
> _„Model to ilościowa metoda, system lub podejście, które przetwarza dane wejściowe i dostarcza oszacowania kwantytatywne. Składa się z komponentów: teoretycznego/konceptualnego, operacyjnego (parametry, dane) i raportowego."_

**Zakres obejmuje:**
- Modele statystyczne i ekonometryczne
- Modele machine learning (supervised i unsupervised)
- Modele optymalizacyjne i symulacyjne
- Modele skoringowe i predykcyjne
- Modele regulacyjne (IRB, IFRS 9, stress-testy)
- Modele eksperymentalne (proof-of-concept, piloty)
- Modele vendorskie używane w banku

**Zakres nie obejmuje:**
> ✍️ **[DO UZUPEŁNIENIA]** Wymienić typy modeli wyłączonych z zakresu tego przewodnika.  
> Przykłady do rozważenia: proste kalkulacje deterministyczne, modele arkuszowe bez komponentu statystycznego, itp.

### 1.2.2 Typy modeli w zakresie

Przewodnik obejmuje trzy główne kategorie, dla których wymagania lifecycle mogą się różnić:

#### Modele regulacyjne
Modele bezpośrednio powiązane z wymogami nadzorczymi lub kapitałowymi:
- **PD / LGD / EAD** — modele parametrów ryzyka kredytowego (podejście IRB)
- **IFRS 9** — modele ECL, staging (Stage 1/2/3), forward-looking
- **Stres-testy** — ICAAP, DFAST, scenariusze makroekonomiczne
- **Modele kapitału regulacyjnego** — RWA, kapitał Tier 1/2

> ⚠️ **[REGULACYJNE]** Modele regulacyjne podlegają zatwierdzeniu przez nadzorcę, surowszym wymogom dokumentacyjnym i walidacyjnym oraz szczególnym procedurom change management. Wszelkie zmiany materialne wymagają uprzedniej notyfikacji lub zatwierdzenia przez KNF/ECB.

#### Modele supervised
Modele uczenia nadzorowanego z etykietowanymi danymi treningowymi:
- Modele klasyfikacji binarnej (binary scoring, fraud, churn)
- Modele regresji (predict LTV, pricing, cashflow)
- Modele wieloklasowe i rankingowe
- Modele sekwencyjne (LSTM, time series)
- Modele ensemble (Random Forest, XGBoost, LightGBM)

> 📋 **[SUPERVISED]** Kluczowe wymagania specyficzne: quality label (target definition), data split z uwzględnieniem time-leakage, backtesting na out-of-time, explainability (SHAP/LIME), feature importance.

#### Modele unsupervised
Modele uczące się wzorców bez etykietowanych danych:
- Clustering klientów i portfeli (K-Means, DBSCAN, hierarchiczne)
- Wykrywanie anomalii i fraud (Isolation Forest, autoencoders)
- Segmentacja behawioralna
- Embeddings i reprezentacje (Word2Vec, autoencoders)
- Redukcja wymiarowości (PCA, UMAP)

> 🔬 **[UNSUPERVISED]** Kluczowe wymagania specyficzne: walidacja business sense (interpretacja segmentów), stabilność klasteryzacji (Silhouette, Davies-Bouldin), brak etykiet wymaga alternatywnych technik walidacyjnych.

### 1.2.3 Granulacja wymagań — tiering

Nie wszystkie modele podlegają tym samym wymaganiom. Poziom rygoru zależy od:
- Materiality modelu (wpływ finansowy, decyzyjny)
- Klasyfikacji regulacyjnej
- Poziomu automatyzacji decyzji
- Złożoności i interpretowalności

Szczegółowa macierz tiering: [Rozdział 3: Klasyfikacja Modeli](./03_klasyfikacja_modeli.md)

---

## 1.3 Odbiorcy

### Główni odbiorcy

| Rola | Jak korzysta z przewodnika |
|---|---|
| **Data Scientist / Model Developer** | Nawigacja przez cały cykl życia modelu; codzienny punkt odniesienia |
| **Model Owner** | Rozumienie obowiązków właścicielskich i bramek akceptacyjnych |
| **Independent Validator** | Weryfikacja zakresu i standardów walidacji |
| **Model Risk Management (MRM)** | Kontrola zgodności z ramami governance |
| **IT / MLOps Engineer** | Wymagania wdrożenia i utrzymania |
| **Compliance / Audit** | Weryfikacja zgodności z regulacjami i politykami |

### Jak korzystać — Data Scientist
Jeśli jesteś Data Scientistem, ten przewodnik odpowiada na Twoje codzienne pytania:
1. **Przed projektem:** Co muszę zaplanować? → Rozdział 4, 5 (Inicjacja)
2. **W trakcie developmentu:** Jakie artefakty wytworzyć? → Rozdział 7
3. **Przed walidacją:** Co walidator będzie sprawdzać? → Rozdział 5 (Walidacja)
4. **Przed wdrożeniem:** Co musi być gotowe? → Rozdział 5 (Wdrożenie)
5. **Po wdrożeniu:** Jakie obowiązki monitoringowe? → Rozdział 5 (Monitoring)
6. **Przy zmianach:** Kiedy potrzebuję formalnej ścieżki? → STD-006

---

## 1.4 Definicje Kluczowych Pojęć

> ✍️ **[DO UZUPEŁNIENIA]** Uzupełnić pełny glosariusz terminów.

| Termin | Definicja |
|---|---|
| **Model** | *(patrz 1.2.1 — definicja do uzupełnienia)* |
| **Cykl życia modelu** | Pełny proces od inicjacji do wycofania modelu z produkcji |
| **Model Tier** | Klasyfikacja modelu według poziomu ryzyka i materiality |
| **Walidacja niezależna** | Ocena modelu przeprowadzona przez stronę niezależną od zespołu tworzącego |
| **Model Owner** | Osoba odpowiedzialna za model z perspektywy biznesowej |
| **Model Developer / Data Scientist** | Osoba odpowiedzialna za budowę, dokumentację i utrzymanie modelu |
| **MRM** | Model Risk Management — funkcja zarządzania ryzykiem modelowym |
| **Stage Gate** | Bramka decyzyjna wymagająca spełnienia określonych kryteriów przed przejściem do kolejnego etapu |
| **Artefakt** | Dokument, raport lub inny wynik pracy wytworzony w ramach danego etapu cyklu życia |
| **Material change** | Zmiana modelu wymagająca formalnej ścieżki review i zatwierdzenia |
| **Model Inventory** | Centralny rejestr wszystkich modeli w organizacji |
| **PSI** | Population Stability Index — miara stabilności populacji modelu |
| **GINI / AUC** | Miary dyskryminacji modeli klasyfikacyjnych |
| **LTV** | Lifetime Value — wartość klienta w czasie |
| **ECL** | Expected Credit Loss — oczekiwana strata kredytowa (IFRS 9) |

Pełny glosariusz: [Rozdział 11: Dodatki](./11_dodatki.md)

---

## 1.5 Powiązane Dokumenty

| Dokument | Typ | Powiązanie |
|---|---|---|
| STD-001: Standard Rozwoju Modeli | Standard | Szczegółowe wymagania developmentu |
| STD-002: Standard Dokumentacji | Standard | Minimalna treść dokumentacji |
| STD-003: Standard Walidacji | Standard | Zakres i metodologia walidacji |
| Polityka Model Risk Management | Polityka | Nadrzędne zasady zarządzania ryzykiem modelowym |
| Regulamin Inwentarza Modeli | Procedura | Rejestracja i klasyfikacja modeli |

---

## 1.6 Historia Wersji

| Wersja | Data | Opis zmian | Autor |
|---|---|---|---|
| 0.5 | 2026-05-09 | Inicjalny szkielet rozdziału | — |
| 1.0 | TBD | Treść merytoryczna — do uzupełnienia | — |

---

*Następny rozdział: [02 — Zasady Nadrzędne](./02_zasady_nadrzedne.md)*
