# Rozdział 11: Dodatki

> **Status:** 🔄 Szkielet — wymaga uzupełnienia glosariuszem i diagramami  
> **Priorytet uzupełnienia:** Średni

---

## 11.1 Glosariusz Pojęć

> ✍️ **[DO UZUPEŁNIENIA]** Rozbudować glosariusz o wszystkie terminy używane w przewodniku.

| Termin PL | Termin EN | Definicja |
|---|---|---|
| Cykl życia modelu | Model lifecycle | Pełny proces od inicjacji do wycofania modelu |
| Walidacja niezależna | Independent validation | Ocena modelu przez stronę niezależną od developmentu |
| Właściciel modelu | Model Owner | Osoba biznesowo odpowiedzialna za model |
| Ryzyko modelowe | Model risk | Ryzyko strat wynikających z błędów w modelach |
| Tiering modelu | Model tiering | Klasyfikacja modelu według poziomu ryzyka |
| Bramka decyzyjna | Stage gate | Punkt kontrolny wymagający spełnienia kryteriów przed kontynuacją |
| Artefakt | Artifact | Dokument lub wynik pracy wytworzony w ramach lifecycle |
| Zmiana materialna | Material change | Zmiana wymagająca formalnej ścieżki review |
| PSI | PSI (Population Stability Index) | Miara stabilności rozkładu populacji modelu |
| Drift | Model/data drift | Zmiana charakterystyk danych lub zjawiska modelowanego |
| Findings walidacyjne | Validation findings | Uwagi i rekomendacje z raportu walidacyjnego |
| Inwentarz modeli | Model inventory | Centralny rejestr wszystkich modeli w organizacji |
| Recalibration | Recalibration | Aktualizacja parametrów modelu bez zmiany metodologii |
| Re-development | Redevelopment | Odbudowa modelu z nową metodologią lub danymi |
| Use test | Use test | Dowód, że model jest faktycznie używany w zarządzaniu ryzykiem |
| ECL | Expected Credit Loss | Oczekiwana strata kredytowa (IFRS 9) |
| IRB | Internal Ratings-Based | Metoda wewnętrznych ratingów (Bazylea) |
| PD | Probability of Default | Prawdopodobieństwo niewykonania zobowiązania |
| LGD | Loss Given Default | Strata w przypadku niewykonania zobowiązania |
| EAD | Exposure at Default | Ekspozycja w momencie niewykonania zobowiązania |
| RACI | RACI matrix | Macierz odpowiedzialności: Responsible, Accountable, Consulted, Informed |
| MRC | Model Risk Committee | Komitet ds. ryzyka modelowego |
| MRM | Model Risk Management | Funkcja zarządzania ryzykiem modelowym |
| SLA | Service Level Agreement | Umowa o poziomie usług |
| UAT | User Acceptance Testing | Testy akceptacji użytkownika |

---

## 11.2 Skróty i Akronimy

| Skrót | Rozwinięcie |
|---|---|
| DS | Data Scientist |
| MDD | Model Development Document |
| MRM | Model Risk Management |
| MRC | Model Risk Committee |
| PD | Probability of Default |
| LGD | Loss Given Default |
| EAD | Exposure at Default |
| ECL | Expected Credit Loss |
| IRB | Internal Ratings-Based approach |
| IFRS | International Financial Reporting Standards |
| EBA | European Banking Authority |
| KNF | Komisja Nadzoru Finansowego |
| ECB | European Central Bank |
| ICAAP | Internal Capital Adequacy Assessment Process |
| AUC | Area Under the Curve |
| PSI | Population Stability Index |
| CSI | Characteristic Stability Index |
| SHAP | SHapley Additive exPlanations |
| LIME | Local Interpretable Model-agnostic Explanations |
| MLOps | Machine Learning Operations |
| CI/CD | Continuous Integration / Continuous Deployment |
| UAT | User Acceptance Testing |
| SOP | Standard Operating Procedure |
| RACI | Responsible, Accountable, Consulted, Informed |
| RODO | Rozporządzenie o Ochronie Danych Osobowych (= GDPR) |

---

## 11.3 Diagramy Referencyjne

> ✍️ **[DO UZUPEŁNIENIA]** Dodać diagramy:
> - Diagram cyklu życia (flowchart z bramkami)
> - Three Lines of Defense w kontekście model governance
> - Diagram hierarchii dokumentów
> - Mapa ról i odpowiedzialności

---

## 11.4 Checklisty Szybkiego Odniesienia

### Checklist Data Scientist — "Przed startem projektu"
- [ ] Business Case zatwierdzony przez Model Owner
- [ ] Tier modelu określony i potwierdzony przez MRM
- [ ] Model zarejestrowany w inwentarzu
- [ ] Dane ocenione jako dostępne i adekwatne
- [ ] Walidator zidentyfikowany (dla Tier 1/2)
- [ ] Plan dokumentacji znany (TMPL-002 przejrzany)
- [ ] Środowisko deweloperskie gotowe i zwersjonowane

### Checklist Data Scientist — "Przed walidacją"
- [ ] Kod w Git, udokumentowany i przetestowany
- [ ] MDD kompletny (wszystkie wymagane sekcje wypełnione)
- [ ] Backtesting na out-of-time wykonany i udokumentowany
- [ ] Explainability raport przygotowany
- [ ] Assumptions Register aktualny
- [ ] Plan monitoringu przygotowany
- [ ] Benchmark comparison wykonany

### Checklist Data Scientist — "Przed wdrożeniem"
- [ ] Raport walidacji otrzymany, krytyczne findings zaadresowane
- [ ] Governance approval uzyskany
- [ ] UAT plan przygotowany
- [ ] Rollback plan przygotowany
- [ ] MLOps / IT poinformowany i gotowy
- [ ] Plan monitoringu zatwierdzony przez Model Ownera
- [ ] Inwentarz modeli zaktualizowany

---

*Poprzedni: [10 — Cykl Przeglądu](./10_przeglad_przewodnika.md)*
