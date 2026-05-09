# Rozdział 5: Wymagania Etapów Cyklu Życia

> **Status:** 🔄 Szkielet — wymaga uzupełnienia każdego etapu w pełnym układzie  
> **Priorytet uzupełnienia:** Wysoki  
> **Format etapu:** Cel → Wejścia → Kluczowe działania → Artefakty → Role → Bramka wyjścia

---

## Układ opisu każdego etapu

Każdy etap opisany jest według stałego schematu:
- **Cel etapu** — co chcemy osiągnąć
- **Wejścia** — co jest potrzebne do rozpoczęcia
- **Kluczowe działania** — co należy wykonać
- **Wymagane artefakty** — co należy wytworzyć
- **Role** — kto jest odpowiedzialny
- **Bramka wyjścia** — kryteria przejścia do kolejnego etapu
- **Uwagi specyficzne** — dla regulacyjne / supervised / unsupervised

---

## 5.1 Etap 1: Identyfikacja Potrzeby Biznesowej

**Cel:** Uzasadnić potrzebę budowy modelu i uzyskać wstępną akceptację.

**Wejścia:**
- Problem biznesowy lub regulacyjny
- Wstępna dostępność danych (szacunkowa)

**Kluczowe działania:**
- Sformułowanie problemu decyzyjnego i pytania modelarskiego
- Wstępna ocena feasibility (dane, zasoby, czas)
- Identyfikacja sponsora biznesowego (Model Owner)
- Wstępna klasyfikacja potencjalnego tieru modelu
- Ocena alternatyw (czy model jest faktycznie potrzebny?)

**Wymagane artefakty:**
- Business Case / Model Concept Note (→ TMPL-001)
- Wstępna karta klasyfikacji tieru

**Role:**
- **DS / Analityk** — inicjuje i przygotowuje concept note
- **Model Owner** — zatwierdza uzasadnienie biznesowe
- **MRM** — wstępna ocena tieru (konsultacyjnie)

**Bramka wyjścia — BG-01:** Zatwierdzenie Business Case przez Model Owner i wstępna akceptacja MRM.

> ⚠️ **[REGULACYJNE]** Modele regulacyjne wymagają wstępnej identyfikacji wymagań nadzorczych już na tym etapie (np. które artykuły CRR/EBA Guidelines mają zastosowanie).

---

## 5.2 Etap 2: Inicjacja i Zatwierdzenie do Developmentu

**Cel:** Formalnie zarejestrować model, potwierdzić tier i uzyskać zatwierdzenie do rozpoczęcia prac.

**Wejścia:**
- Zatwierdzony Business Case
- Zidentyfikowany Model Owner i team DS

**Kluczowe działania:**
- Rejestracja modelu w inwentarzu modeli
- Potwierdzenie lub aktualizacja tieru przez MRM
- Uzgodnienie planu developmentu i milestones
- Uzgodnienie zasobów (dane, środowisko, team)
- Powołanie walidatora (dla Tier 1 i 2) — wcześniej niż się wydaje konieczne

**Wymagane artefakty:**
- Model Initiation Form / Development Charter
- Wpis w inwentarzu modeli (z tiersem i statusem "In Development")
- Plan developmentu (harmonogram, zasoby)

**Role:**
- **DS** — przygotowuje plan developmentu
- **Model Owner** — formalnie inicjuje model
- **MRM** — zatwierdza tier, rejestruje w inwentarzu
- **Walidator** — identyfikowany i informowany (nie wykonuje pracy na tym etapie)

**Bramka wyjścia — BG-01:** MRM potwierdza tier i rejestruje model.

---

## 5.3 Etap 3: Dane i Ocena

**Cel:** Zidentyfikować, pozyskać i ocenić dane wymagane do budowy modelu.

**Wejścia:**
- Business Case z opisem danych wymaganych
- Zatwierdzony tier modelu

**Kluczowe działania:**
- Identyfikacja źródeł danych (wewnętrznych i zewnętrznych)
- Ocena dostępności i jakości danych
- Ocena reprezentatywności próbki (czy dane odzwierciedlają populację docelową?)
- Zgody i wymagania privacy (RODO, GDPR)
- Dokumentacja linii danych (data lineage)
- Wstępna EDA (Exploratory Data Analysis)

**Wymagane artefakty:**
- Data Assessment Report
- Data Dictionary (wstępna wersja)
- Privacy / Data Ethics Assessment (jeśli dotyczy)

**Role:**
- **DS** — wykonuje ocenę danych, EDA
- **Data Owner / Data Steward** — potwierdza dostępność i jakość
- **Compliance** — ocena wymogów privacy (jeśli dotyczy)

**Bramka wyjścia — BG-02:** Data Owner i MRM potwierdzają adekwatność danych.

> 📋 **[SUPERVISED]** Szczególna uwaga na:
> - Definicję target variable (label) — jakość labeli jest kluczowa
> - Time window: kiedy obserwacja, kiedy outcome? Unikanie data leakage
> - Reprezentatywność: czy próbka dev odpowiada populacji produkcyjnej?
> - Sample bias: odrzucone aplikacje, truncated data

> 🔬 **[UNSUPERVISED]** Szczególna uwaga na:
> - Brak target variable — konieczna jasna definicja celu klasteryzacji
> - Reprezentatywność danych jest szczególnie ważna przy braku ground truth
> - Outlier treatment ma duży wpływ na klastry

---

## 5.4 Etap 4: Projektowanie Modelu

**Cel:** Wybrać metodologię i podejście modelarskie, udokumentować założenia.

**Wejścia:**
- Ocena danych
- Wymagania biznesowe i regulacyjne

**Kluczowe działania:**
- Wybór metodologii (uzasadnienie wyboru podejścia)
- Określenie założeń i ograniczeń modelu
- Zdefiniowanie miar performance i kryteriów sukcesu
- Projekt planu walidacji (co będzie walidowane?)
- Design planu monitoringu (co monitorujemy po wdrożeniu?)

**Wymagane artefakty:**
- Design Document / Model Methodology Note
- Assumptions Register (wstępna wersja)
- Plan walidacji (uzgodniony z walidatorem)

**Role:**
- **DS** — proponuje metodologię i projekt
- **Model Owner** — zatwierdza podejście biznesowe
- **Walidator** — opiniuje plan walidacji
- **MRM** — akceptuje projektowane podejście (Tier 1/2)

**Bramka wyjścia — BG-03:** Sign-off metodologii przez Model Owner i MRM.

> ⚠️ **[REGULACYJNE]** Wybór metodologii dla modeli regulacyjnych musi być spójny z wytycznymi EBA (np. EBA GL 2017/16 dla PD/LGD) lub innymi właściwymi regulacjami.

> 📋 **[SUPERVISED]** Uzasadnij wybór algorytmu w kontekście explainability, regulatory requirements i charakterystyk danych.

> 🔬 **[UNSUPERVISED]** Zdefiniuj już na tym etapie: co oznacza dobry klaster? Jak będziemy mierzyć "sukces" klasteryzacji bez ground truth?

---

## 5.5 Etap 5: Development Modelu

**Cel:** Zbudować model zgodnie z zatwierdzonym projektem.

**Wejścia:**
- Zatwierdzony Design Document
- Przygotowany i zatwierdzony dataset

**Kluczowe działania:**
- Inżynieria cech (feature engineering)
- Trening i selekcja modelu
- Tuning hiperparametrów
- Testy jednostkowe kodu
- Wersjonowanie kodu (Git)
- Dokumentowanie kluczowych decyzji w code comments i notatkach

**Wymagane artefakty:**
- Kod modelu (z dokumentacją, w repozytorium)
- Wyniki eksperymentów (experiment tracking — MLflow lub równorzędny)
- Wersjonowane artefakty modelu (pickle/joblib lub format produkcyjny)

**Role:**
- **DS** — development modelu, testy jednostkowe
- **Peer DS** — code review
- **MLOps / IT** — konsultacje dot. środowiska wdrożeniowego

> 📋 **[SUPERVISED]** Obowiązkowe podczas developmentu:
> - Użyj osobnego validation set podczas selekcji cech i tuning (nie test set)
> - Zachowaj test set wyłącznie do końcowej ewaluacji (single use rule)
> - Dokumentuj wszystkie próby i iteracje (experiment tracking)

> 🔬 **[UNSUPERVISED]** Obowiązkowe podczas developmentu:
> - Przetestuj multiple konfiguracje algorytmu (różne k, różne metryki odległości)
> - Dokumentuj kryterium wyboru finalnej konfiguracji
> - Zbuduj interpretację segmentów jako integralną część developmentu

---

## 5.6 Etap 6: Testy i Dokumentacja

**Cel:** Przetestować model, udokumentować wyniki i przygotować do walidacji.

**Wejścia:**
- Zbudowany model
- Wyniki development

**Kluczowe działania:**
- Backtesting / out-of-time validation
- Analiza podpopulacji (subpopulation analysis)
- Calibration analysis
- Explainability (SHAP values lub inne)
- Testy stress i sensytywność
- Kompletna dokumentacja modelarska (MDD)
- Code review

**Wymagane artefakty:**
- Model Development Document (MDD) (→ TMPL-002) — kompletny
- Test Results Report
- Assumptions Register — finalna wersja
- Data Documentation — finalna wersja

**Role:**
- **DS** — wykonuje testy, pisze dokumentację
- **Model Owner** — zatwierdza kompletność dokumentacji
- **Peer DS** — code review i review wyników

**Bramka wyjścia — BG-05:** Model Owner potwierdza kompletność dokumentacji.

> ⚠️ **[REGULACYJNE]** MDD musi spełniać minimalne wymagania dokumentacyjne określone w EBA/KNF wytycznych dla danego typu modelu.

> 📋 **[SUPERVISED]** Obowiązkowe testy:
> - Backtesting na out-of-time dataset (nie widzianym w treningu)
> - Porównanie z modelem benchmarkowym (np. model poprzedni lub prosty baseline)
> - Analiza stability (PSI, CSI) między development a current population
> - Explainability raport (feature importance, SHAP)

> 🔬 **[UNSUPERVISED]** Obowiązkowe testy:
> - Internal cluster validity metrics (Silhouette, Calinski-Harabasz, Davies-Bouldin)
> - Stability check: czy segmenty są stabilne na nowej próbce?
> - Business validation: interpretacja każdego segmentu przez ekspertów domenowych

---

## 5.7 Etap 7: Walidacja Niezależna

**Cel:** Niezależna ocena modelu przez stronę niemającą udziału w developmencie.

> 🔴 **OBOWIĄZKOWE** dla Tier 1 i Tier 2. Dla Tier 3: uproszczona forma.

**Wejścia:**
- Kompletne MDD
- Kod modelu
- Dataset (lub reprezentatywna próbka)
- Plan walidacji

**Kluczowe działania:**
- Przegląd konceptualny (conceptual soundness)
- Ocena danych i procesu developmentu
- Niezależne testy ilościowe
- Ocena dokumentacji i założeń
- Ocena planu monitoringu
- Sformułowanie findings i rekomendacji

**Wymagane artefakty:**
- Raport Walidacji (→ TMPL-003)
- Lista findings z oceną istotności (krytyczne / poważne / informacyjne)

**Role:**
- **Validator / MRM** — wykonuje walidację
- **DS** — odpowiada na pytania, nie modyfikuje modelu w trakcie
- **Model Owner** — adresuje findings organizacyjne

**Bramka wyjścia — BG-06:** Brak krytycznych findings lub plan ich adresowania.

> ⚠️ **[REGULACYJNE]** Walidator musi być niezależny organizacyjnie od zespołu developmentu. Raport walidacyjny jest dokumentem podlegającym ocenie nadzorcy.

---

## 5.8 Etap 8: Zatwierdzenie i Governance Review

**Cel:** Formalna akceptacja modelu przez komitet governance.

**Wejścia:**
- Raport walidacji
- Kompletna dokumentacja
- Plan adresowania findings

**Kluczowe działania:**
- Prezentacja na MRC / Model Governance Committee
- Review i decyzja o zatwierdzeniu
- Dokumentacja decyzji i warunków

**Wymagane artefakty:**
- Approval Record (protokół zatwierdzenia)
- Lista warunków i termin adresowania (jeśli conditional approval)

**Bramka wyjścia — BG-07:** Formalna akceptacja governance.

---

## 5.9 Etap 9: Wdrożenie

**Cel:** Bezpieczna implementacja modelu w środowisku produkcyjnym.

**Wejścia:**
- Governance approval
- Production-ready kod
- Plan wdrożenia i rollback

**Kluczowe działania:**
- UAT (User Acceptance Testing)
- Testy wydajnościowe i bezpieczeństwa
- Deployment (zgodnie z zatwierdzonym kodem)
- Parallel run (jeśli zastępujemy stary model)
- Go-live i przekazanie do operacji

**Wymagane artefakty:**
- Deployment Evidence
- UAT Sign-off
- Go-live Checklist (→ PROC-004)
- Aktualizacja inwentarza modeli (status: Production)

**Bramka wyjścia — BG-08:** UAT pass i Go-live sign-off.

---

## 5.10 Etap 10: Monitoring

**Cel:** Ciągła kontrola działania modelu w produkcji.

**Kluczowe działania:**
- Regularne obliczanie metryk performance (zgodnie z planem monitoringu)
- Wykrywanie driftu (data drift, concept drift)
- Ocena stabilności
- Raportowanie wyników do Model Ownera i MRM

**Wymagane artefakty:**
- Raporty monitoringowe (miesięczne/kwartalne zgodnie z tierem)
- Alert log (jeśli przekroczone triggery)

> 📋 **[SUPERVISED]** Monitoruj: GINI/AUC, PSI score/feature, calibration, bad rate, override rate.

> 🔬 **[UNSUPERVISED]** Monitoruj: stabilność segmentów (Jaccard index lub inne), rozkłady cech per klaster, drift populacji.

---

## 5.11 Etap 11: Przegląd i Aktualizacja

**Cel:** Cykliczna ocena adekwatności modelu i decyzja o jego przyszłości.

> ✍️ **[DO UZUPEŁNIENIA]** Opisać częstotliwość przeglądów per tier, zakres annual review, kryteria decyzji o recalibration vs. redevelopment.

---

## 5.12 Etap 12: Zarządzanie Zmianą

**Cel:** Kontrolowane wprowadzanie zmian do modeli produkcyjnych.

> ✍️ **[DO UZUPEŁNIENIA]** Opisać klasyfikację zmian (minor/major/material), ścieżkę zatwierdzania dla każdej kategorii, wymagania dokumentacyjne.

Szczegóły: [STD-006: Zarządzanie Zmianą](../01_supporting_standards/STD-006_zarzadzanie_zmiana.md)

---

## 5.13 Etap 13: Wycofanie i Archiwizacja

**Cel:** Bezpieczne zakończenie życia modelu z zachowaniem pełnej historii.

> ✍️ **[DO UZUPEŁNIENIA]** Opisać kryteria decyzji o wycofaniu, procedurę handover, wymagania archiwizacyjne (w tym okresy retencji per typ modelu).

Szczegóły: [PROC-006: Wycofanie](../02_procedures/PROC-006_wycofanie.md)

---

## 5.14 Powiązane Dokumenty

- [Rozdział 7: Wymagane Artefakty](./07_wymagane_artefakty.md) — pełna lista co wytworzyć
- [Rozdział 6: Role i Odpowiedzialności](./06_role_i_odpowiedzialnosci.md) — RACI per etap
- [02_procedures/](../02_procedures/) — szczegółowe procedury operacyjne

---

*Poprzedni: [04 — Przegląd Cyklu Życia](./04_przeglad_cyklu_zycia.md) | Następny: [06 — Role i Odpowiedzialności](./06_role_i_odpowiedzialnosci.md)*
