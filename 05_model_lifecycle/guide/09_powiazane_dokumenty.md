# Rozdział 9: Powiązane Standardy, Procedury i Szablony

> **Część:** Model Lifecycle Guide  
> **Status:** Draft — wymaga uzupełnienia merytorycznego  
> **Powiązane dokumenty:** [MODEL_LIFECYCLE_GUIDE.md](./MODEL_LIFECYCLE_GUIDE.md)

---

## Wprowadzenie

Ten rozdział mapuje Model Lifecycle Guide do powiązanego ekosystemu dokumentów. Przewodnik definiuje ramy i zasady — szczegółowe instrukcje jak wypełnić te wymagania zawarte są w dokumentach niższych poziomów.

```
Model Risk Policy (Polityka)
       ↓
Model Lifecycle Guide (TEN DOKUMENT — Framework)
       ↓
Standardy → Procedury → Szablony
```

---

## 9.1 Standardy (Poziom 2)

Standardy definiują szczegółowe wymagania metodologiczne i procesowe w danym obszarze.

### Mapa Standardów

| Standard | Opis | Lokalizacja | Status |
|----------|------|-------------|--------|
| **Standard Developmentu Modeli** | Wymagania dot. budowy modeli: coding standards, dokumentacja, split strategies | [../standards/development_standard.md](../standards/development_standard.md) | Do opracowania |
| **Standard Dokumentacji Modeli** | Minimalna zawartość MDD, szablony, wymogi archiwizacji | [../standards/documentation_standard.md](../standards/documentation_standard.md) | Do opracowania |
| **Standard Walidacji Modeli** | Zakres walidacji, metodologia, wymogi niezależności | [../standards/validation_standard.md](../standards/validation_standard.md) | Do opracowania |
| **Standard Monitoringu Modeli** | Metryki, progi, częstotliwość, raportowanie | [../standards/monitoring_standard.md](../standards/monitoring_standard.md) | Do opracowania |
| **Standard Zarządzania Zmianą** | Klasyfikacja zmian, ścieżki zatwierdzenia, wersjonowanie | [../standards/change_management_standard.md](../standards/change_management_standard.md) | Do opracowania |
| **Standard MLOps / Wdrożeń** | Wymagania infrastrukturalne, CI/CD, model serving | [../standards/mlops_standard.md](../standards/mlops_standard.md) | Do opracowania |
| **Standard Explainability (AI/ML)** | Wymogi wyjaśnialności, metody (SHAP/LIME), dokumentacja | [../standards/explainability_standard.md](../standards/explainability_standard.md) | Do opracowania |
| **Standard Jakości Danych** | Wymogi jakości danych dla modeli, profile danych | [../standards/data_quality_standard.md](../standards/data_quality_standard.md) | Do opracowania |
| **Standard Fairness i Etyki AI** | Bias testing, fairness metrics, dyskryminacja | [../standards/fairness_standard.md](../standards/fairness_standard.md) | Do opracowania |

---

## 9.2 Procedury (Poziom 3)

Procedury opisują krok po kroku jak wykonać konkretne działania.

### Mapa Procedur

| Procedura | Opis | Lokalizacja | Status |
|-----------|------|-------------|--------|
| **Procedura Niezależnej Walidacji** | Szczegółowy przebieg procesu walidacji | [../procedures/validation_procedure.md](../procedures/validation_procedure.md) | Do opracowania |
| **Procedura Rejestracji w Model Inventory** | Jak zarejestrować model, wymagane pola | [../procedures/model_inventory_procedure.md](../procedures/model_inventory_procedure.md) | Do opracowania |
| **Procedura Zarządzania Zmianą** | Szczegółowy przebieg Change Management | [../procedures/change_management_procedure.md](../procedures/change_management_procedure.md) | Do opracowania |
| **Procedura Wycofania Modelu** | Kroki wycofania i archiwizacji | [../procedures/model_retirement_procedure.md](../procedures/model_retirement_procedure.md) | Do opracowania |
| **Procedura Awaryjna** | Reakcja na krytyczny błąd modelu produkcyjnego | [../procedures/emergency_procedure.md](../procedures/emergency_procedure.md) | Do opracowania |
| **Procedura Vendor Model Assessment** | Ocena modeli zakupionych od dostawców | [../procedures/vendor_model_procedure.md](../procedures/vendor_model_procedure.md) | Do opracowania |

---

## 9.3 Szablony i Narzędzia (Poziom 4)

Szablony to gotowe formularze, wzory dokumentów i checklistry.

### Mapa Szablonów

| Szablon | Opis | Lokalizacja | Status |
|---------|------|-------------|--------|
| **Model Concept Note** | Dokument inicjacyjny | [../templates/](../templates/) | Do opracowania |
| **Model Risk Assessment Form** | Wstępna ocena ryzyka i klasyfikacja Tier | [../templates/](../templates/) | Do opracowania |
| **Data Assessment Report** | Ocena jakości danych | [../templates/](../templates/) | Do opracowania |
| **Model Development Document (MDD)** | Główny dokument techniczny modelu | [../templates/](../templates/) | Do opracowania |
| **Assumptions Register** | Rejestr założeń | [../templates/](../templates/) | Do opracowania |
| **Validation Report** | Raport walidacyjny | [../templates/](../templates/) | Do opracowania |
| **Findings Register** | Rejestr findings z walidacji | [../templates/](../templates/) | Do opracowania |
| **Deployment Checklist** | Lista kontrolna wdrożenia | [../templates/](../templates/) | Do opracowania |
| **Monitoring Plan** | Plan monitoringu modelu | [../templates/](../templates/) | Do opracowania |
| **Monitoring Report** | Szablon raportu monitoringowego | [../templates/](../templates/) | Do opracowania |
| **Annual Review Report** | Szablon rocznego przeglądu | [../templates/](../templates/) | Do opracowania |
| **Change Request Form** | Formularz wniosku o zmianę | [../templates/](../templates/) | Do opracowania |
| **Retirement Record** | Dokument wycofania | [../templates/](../templates/) | Do opracowania |
| **Model Card** | Karta modelu ML | [../templates/](../templates/) | Do opracowania |
| **Exception Request Form** | Wniosek o wyjątek | [../templates/](../templates/) | Do opracowania |
| **RACI Matrix (blank)** | Matryca ról do uzupełnienia | [../templates/](../templates/) | Do opracowania |

---

## 9.4 Referencje Regulacyjne i Branżowe

Pełna bibliografia i kolekcja referencji: [../references/](../references/)

### Kluczowe Dokumenty Regulacyjne

| Dokument | Organizacja | Rok | Opis |
|----------|-------------|-----|------|
| **SR 11-7** Guidance on Model Risk Management | US Federal Reserve | 2011 | Globalny standard branżowy — framework MRM |
| **OCC Bulletin 2011-12** | OCC | 2011 | Model risk management dla banków USA |
| **EBA/GL/2023/xx** Guidelines on Model Risk Management | EBA | 2023 | Wiążące dla banków UE |
| **ECB Guide to Internal Models (TRIM)** | ECB | 2018 | Walidacja modeli wewnętrznych (IRB) |
| **SS1/23** Model Risk Management Principles | PRA/BoE | 2023 | Dobra praktyka — banki UK |
| **EBA/GL/2017/16** Estimation of PD, LGD, CF | EBA | 2017 | Modele IRB — PD/LGD/EAD |
| **CRR/CRD IV** | EU | 2013+ | Wymogi kapitałowe, modele IRB |
| **IFRS 9** | IASB | 2014 | Modele ECL, staging |
| **RODO / GDPR** | EU | 2018 | Ochrona danych osobowych |
| **Rekomendacje KNF** | KNF | aktualne | Polskie wymogi nadzorcze |

---

## 9.5 Mapa Powiązań: Guide ↔ Standardy ↔ Regulacje

<!-- PROMPT DLA AUTORA:
Uzupełnij tabelę mapowania wymagań Guide do konkretnych sekcji regulacji.
Cel: pokazać jak każde wymaganie Guide ma podstawę w regulacjach lub standardach.
-->

| Wymaganie Guide | Standard wewnętrzny | Regulacja zewnętrzna |
|----------------|---------------------|---------------------|
| Niezależna walidacja (rozdz. 5.5) | Validation Standard | SR 11-7 Section IV; EBA GL 2023 |
| Documentation by design (zasada 2.6) | Documentation Standard | SR 11-7 Section III; ECB TRIM |
| Model Inventory (każdy etap) | Model Inventory Procedure | SR 11-7 Section II; EBA GL |
| Monitoring (rozdz. 5.8) | Monitoring Standard | SR 11-7 Section V; EBA GL |
| Change Management (rozdz. 5.9) | Change Management Standard | SR 11-7 Section VI |
| Explainability (Kat. C) | Explainability Standard | EBA GL 2023; RODO Art. 22 |
| Bias & Fairness (Kat. B, C) | Fairness Standard | RODO Art. 22; Equal treatment |
| Data Quality (rozdz. 5.2) | Data Quality Standard | EBA GL; ECB TRIM |

---

*Powrót do: [MODEL_LIFECYCLE_GUIDE.md — Główny Przewodnik](./MODEL_LIFECYCLE_GUIDE.md)*
