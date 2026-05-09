# Rozdział 7: Wymagane Artefakty i Minimalna Dokumentacja

> **Część:** Model Lifecycle Guide  
> **Status:** Draft — wymaga uzupełnienia merytorycznego  
> **Powiązane dokumenty:** [MODEL_LIFECYCLE_GUIDE.md](./MODEL_LIFECYCLE_GUIDE.md)

---

## Wprowadzenie

Ten rozdział definiuje minimalny zestaw artefaktów wymaganych dla modeli produkowanych lub wdrażanych w organizacji. Dokumentacja modelu jest wymogiem — nie czynnością opcjonalną.

Szczegółowe szablony dokumentów: [../templates/](../templates/)

---

## 7.1 Pełna Lista Artefaktów według Etapu Lifecycle

| Artefakt | Etap | Tier 1 | Tier 2 | Tier 3 | Właściciel |
|----------|------|--------|--------|--------|-----------|
| **Model Concept Note** | Inicjacja | ✅ | ✅ | ✅ | Data Scientist |
| **Regulatory Mapping** | Inicjacja | ✅ (Kat.A) | ⚠️ | ❌ | DS + Compliance |
| **Model Inventory Entry** | Inicjacja | ✅ | ✅ | ✅ | MRM |
| **Data Assessment Report** | Dane | ✅ | ✅ | ✅ uproszczony | Data Scientist |
| **Data Dictionary** | Dane | ✅ | ✅ | ✅ | Data Scientist |
| **RODO Assessment** | Dane | ✅ | ✅ | ⚠️ | DS + Compliance |
| **Model Development Document (MDD)** | Budowa | ✅ pełny | ✅ standard | ✅ uproszczony | Data Scientist |
| **Assumptions Register** | Budowa | ✅ | ✅ | ✅ | Data Scientist |
| **Limitations Register** | Budowa | ✅ | ✅ | ✅ | Data Scientist |
| **Experiment Log** | Budowa | ✅ (ML) | ✅ (ML) | ⚠️ | Data Scientist |
| **SHAP / Explainability Analysis** | Testowanie | ✅ (ML) | ✅ (ML) | ⚠️ | Data Scientist |
| **Bias & Fairness Assessment** | Testowanie | ✅ | ✅ | ⚠️ | Data Scientist |
| **Model Card** | Testowanie | ✅ (ML) | ✅ (ML) | ⚠️ | Data Scientist |
| **Test Results Report** | Testowanie | ✅ | ✅ | ✅ | Data Scientist |
| **OOT Validation Results** | Testowanie | ✅ | ✅ | ⚠️ | Data Scientist |
| **Validation Report** | Walidacja | ✅ pełny | ✅ standard | ✅ uproszczony | Walidator |
| **Findings Register** | Walidacja | ✅ | ✅ | ✅ | Walidator |
| **Remediation Plan** | Walidacja | ✅ jeśli H/M | ✅ | ✅ | DS + Model Owner |
| **Approval Record (Gate 6)** | Akceptacja | ✅ | ✅ | ✅ | Komitet / MRM |
| **Deployment Evidence** | Wdrożenie | ✅ | ✅ | ✅ | IT/MLOps |
| **IT Deployment Checklist** | Wdrożenie | ✅ | ✅ | ⚠️ | IT/MLOps |
| **UAT Sign-off** | Wdrożenie | ✅ | ✅ | ⚠️ | Model Owner |
| **Rollback Plan** | Wdrożenie | ✅ | ✅ | ⚠️ | IT/MLOps |
| **Monitoring Plan** | Wdrożenie | ✅ | ✅ | ⚠️ | Model Owner |
| **Monitoring Reports** | Monitoring | ✅ | ✅ | ⚠️ | Model Owner |
| **Annual Review Report** | Monitoring | ✅ | ✅ | ⚠️ | Model Owner |
| **Change Request Form** | Zmiana | ✅ | ✅ | ✅ | DS / Model Owner |
| **Impact Assessment** | Zmiana | ✅ | ✅ | ⚠️ | DS / MRM |
| **Change Log** | Zmiana | ✅ | ✅ | ✅ | MRM |
| **Retirement Record** | Wycofanie | ✅ | ✅ | ✅ | Model Owner |

*✅ = Obowiązkowy, ⚠️ = Zalecany / wymagany jeśli dotyczy, ❌ = Nie wymagany*

---

## 7.2 Kluczowe Dokumenty — Opis

### Model Development Document (MDD)

<!-- PROMPT DLA AUTORA:
Opisz obowiązkową zawartość MDD w organizacji.
Jakie sekcje są bezwzględnie wymagane? Jaka jest docelowa objętość?
Powiąż z szablonem MDD.
-->

MDD jest głównym dokumentem technicznym modelu. Musi zawierać:

**Sekcje obowiązkowe (wszystkie Tiery):**
1. Cel i zakres modelu
2. Populacja docelowa i ograniczenia zastosowania
3. Dane wejściowe — opis, źródła, ocena jakości
4. Metodologia — opis i uzasadnienie podejścia
5. Budowa modelu — specyfikacja, parametry
6. Wyniki testów — performance, stabilność
7. Założenia i ograniczenia
8. Plan monitoringu (skrócony)
9. Wersja i historia zmian

**Sekcje dodatkowe (Tier 1 / Kategoria A):**
- Mapowanie do wymogów regulacyjnych
- Analiza sensytywności i stress testing
- Szczegółowa analiza danych treningowych

**Sekcje dodatkowe (Kategoria C — Supervised ML):**
- SHAP analysis / wyjaśnialność
- Bias & Fairness Assessment
- Feature engineering pipeline
- Model Card (jako załącznik lub oddzielny dokument)

---

### Assumptions Register

Rejestr wszystkich kluczowych założeń modelu, zawierający dla każdego założenia:
- Opis założenia
- Uzasadnienie
- Ryzyko w przypadku naruszenia założenia
- Status weryfikacji

---

### Validation Report

Raport walidacyjny musi zawierać:
1. Executive summary (ocena ogólna)
2. Zakres walidacji
3. Metodologia walidacji
4. Wyniki per obszar walidacji (conceptual soundness, outcomes, dokumentacja, etc.)
5. Findings Register (klasy: C/H/M/L)
6. Wnioski i rekomendacje
7. Podpis walidatora i data

---

### Monitoring Plan

Plan monitoringu musi zawierać:
1. Lista metryk z definicjami
2. Progi alarmowe (soft / hard) per metryka
3. Częstotliwość monitoringu
4. Odpowiedzialny za monitoring
5. Trigger events i eskalacja
6. Schemat raportowania

---

### Model Inventory Entry

Każdy model w rejestrze musi mieć:
- Unikalny Model ID
- Nazwa i opis
- Kategoria funkcjonalna (A/B/C/D)
- Tier ryzyka (1/2/3)
- Model Owner (imię, rola)
- Status (Development / Validation / Production / Retired)
- Data ostatniej walidacji
- Następna planowana walidacja
- Wersja produkcyjna
- Powiązane dokumenty (linki/referencje)

---

## 7.3 Minimalne Wymagania Dokumentacyjne dla MDD według Kategorii

<!-- PROMPT DLA AUTORA:
Uzupełnij wymagania według kategorii — co jest specyficzne dla każdej grupy modeli.
-->

### Kategoria A — Regulacyjny

Poza sekcjami standardowymi, wymagane są:
- [ ] Mapowanie wymagań do artykułów regulacyjnych (Regulatory Mapping Table)
- [ ] Dokumentacja próby treningowej — rozkład ekonomiczny, long-run average
- [ ] Margin of Conservatism (MoC) — uzasadnienie jeśli stosowany
- [ ] Analiza zgodności z EBA GL / ECB TRIM / KNF
- [ ] Udokumentowanie interpretacji regulacyjnych (regulatory judgments)

### Kategoria B — Scorecard

Poza sekcjami standardowymi, wymagane są:
- [ ] Analiza WoE i IV per zmienna (tabela)
- [ ] Uzasadnienie binningu i przedziałów
- [ ] Korelacja zmiennych (VIF lub alternatywa)
- [ ] Dokumentacja odrzuconych zmiennych
- [ ] Kalibracja scorecardów (jeśli stosowana)
- [ ] PSI/CSI baseline dla monitoringu

### Kategoria C — Supervised ML

Poza sekcjami standardowymi, wymagane są:
- [ ] Feature engineering pipeline (opis transformacji)
- [ ] SHAP values analysis (global i local)
- [ ] Bias & Fairness Assessment (wyniki i wnioski)
- [ ] Model Card (oddzielny dokument lub załącznik do MDD)
- [ ] Experiment Log (MLflow lub równoważny)
- [ ] Porównanie z modelem baseline / referencyjnym

### Kategoria D — Unsupervised

Poza sekcjami standardowymi, wymagane są:
- [ ] Uzasadnienie wyboru algorytmu i parametrów (liczba klastrów itd.)
- [ ] Kryteria oceny jakości (silhouette, DB, biznesowa ocena)
- [ ] Test stabilności segmentów
- [ ] Profil biznesowy segmentów / anomalii
- [ ] Plan monitoringu stabilności

---

## 7.4 Archiwizacja Artefaktów

Artefakty modelu podlegają archiwizacji przez:
- Okres wynikający z wymogów regulacyjnych (Kategoria A)
- Minimum [PLACEHOLDER: N] lat po wycofaniu modelu (pozostałe)

> ⚠️ **RODO:** Dane osobowe użyte do treningu podlegają osobnym regułom retencji — mogą wymagać anonimizacji lub usunięcia.

---

*Szablony wszystkich dokumentów: [../templates/](../templates/)*  
*Następny rozdział: [08_kontrole_wyjatki.md — Kontrole, Wyjątki i Eskalacja](./08_kontrole_wyjatki.md)*
