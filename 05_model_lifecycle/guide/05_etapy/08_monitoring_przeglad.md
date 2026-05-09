# Etap 5.8: Monitoring i Przegląd Okresowy

> **Część:** Model Lifecycle Guide — Rozdział 5 (Etapy Lifecycle)  
> **Status:** Draft  
> **Powiązane dokumenty:** [MODEL_LIFECYCLE_GUIDE.md](../MODEL_LIFECYCLE_GUIDE.md) | [← Poprzedni: Wdrożenie](./07_wdrozenie.md) | [Następny: Zmiana →](./09_zarzadzanie_zmiana.md)

---

## Cel Etapu

Ciągłe monitorowanie działania modelu w produkcji w celu wczesnego wykrycia degradacji performance, driftu danych lub innych problemów wymagających interwencji.

---

## Kto wykonuje

| Rola | Aktywność |
|------|-----------|
| **Model Owner** | Odpowiada za monitoring, eskalacja problemów |
| **Data Scientist** | Analiza wyników monitoringu, rekomendacje |
| **MRM** | Oversight, raportowanie, tracking trigger events |
| **IT / MLOps** | Techniczne utrzymanie pipeline'u monitoringu |

---

## Monitoring jako Obowiązek "By Design"

Monitoring nie jest czynnością dodatkową — jest planowany i konfigurowany **przed wdrożeniem** modelu. Monitoring Plan musi być gotowy jako warunek Gate 7.

---

## Wymogi Monitoring Plan

<!-- PROMPT DLA AUTORA:
Opisz wymaganą zawartość Monitoring Plan dla modeli w organizacji.
Jakie metryki są standardowe? Jakie są progi alarmowe?
-->

Monitoring Plan musi zawierać:
- Listę metryk performance, stabilności i danych
- Progi alarmowe (soft / hard) dla każdej metryki
- Częstotliwość raportowania
- Odpowiedzialnego za monitoring (Model Owner lub wyznaczona rola)
- Trigger events uruchamiające eskalację lub re-walidację

---

## Typy Monitoringu

### 1. Monitoring Performance (Discriminatory Power)

<!-- PROMPT DLA AUTORA:
Opisz zakres monitoringu performance w organizacji.
Jakie metryki są standardowe? Co jest progiem alarmowym?
-->

| Metryka | Opis | Trigger (przykładowy) |
|---------|------|----------------------|
| AUROC / Gini | Siła dyskryminacyjna | Spadek > [PLACEHOLDER]% vs baseline |
| KS Statistic | Separacja | Spadek > [PLACEHOLDER]% vs baseline |
| Accuracy / Precision / Recall | (ML) | Zależy od zastosowania |
| R², RMSE | (regresja) | Zmiana > [PLACEHOLDER]% |

### 2. Monitoring Stabilności

| Metryka | Opis | Progi |
|---------|------|-------|
| **PSI** (Population Stability Index) | Zmiana rozkładu zmiennej wejściowej | 0.1 = alarmowy; 0.2 = krytyczny |
| **CSI** (Characteristic Stability Index) | Zmiana rozkładu per zmienna | [PLACEHOLDER] |
| Drift konceptualny | Zmiana relacji feature–target | Metody statystyczne lub ML |

### 3. Monitoring Jakości Danych

- Brakujące wartości (missing rate) — próg: > [PLACEHOLDER]%
- Anomalie w rozkładach zmiennych wejściowych
- Spójność z historycznymi rozkładami treningowymi
- Data freshness — czy dane są aktualne?

### 4. Monitoring Biznesowy

<!-- PROMPT DLA AUTORA:
Opisz jak śledzone są wyniki biznesowe modelu (outcomes).
Np. default rate vs predicted PD, actual vs predicted LGD.
-->

- Porównanie przewidywanych vs rzeczywistych wyników (outcomes validation)
- Wskaźniki override / manual override rate
- Zmiany w działaniu modelu względem poprzednich okresów
- Anomalie w liczbie decyzji / scorów / predykcji

### 5. Monitoring Specyficzny dla Kategorii Modelu

| Kategoria | Specyficzne metryki |
|-----------|---------------------|
| A — Regulacyjny | Odchyłki od prognoz regulacyjnych, backtesting regulacyjny |
| B — Scorecard | PSI/CSI dla scorecardów, override rate, Gini/KS |
| C — Supervised ML | Feature drift, prediction drift, SHAP drift |
| D — Unsupervised | Stabilność segmentów, zmiana cluster assignments, anomaly rate |

---

## Częstotliwość Raportowania

<!-- PROMPT DLA AUTORA:
Uzupełnij o wymaganą częstotliwość raportowania dla każdego Tiera.
Do jakich komitetów raportowany jest monitoring?
-->

| Tier | Minimalna częstotliwość | Raportowanie do |
|------|------------------------|-----------------|
| Tier 1 | Miesięczne | Komitet / CRO |
| Tier 2 | Kwartalne | MRM |
| Tier 3 | Roczne lub ad-hoc | Model Owner |

---

## Trigger Events — Eskalacja i Re-walidacja

| Trigger | Klasyfikacja | Wymagana Akcja |
|---------|-------------|----------------|
| PSI > 0.25 | Krytyczny | Natychmiastowa eskalacja do MRM, wstrzymanie modelu |
| PSI 0.1–0.25 | Alarmowy | Eskalacja do MRM, pogłębiona analiza w 30 dni |
| Gini/AUC spadek > [PLACEHOLDER]% | Krytyczny | Re-walidacja lub re-development |
| Missing data rate > [PLACEHOLDER]% | Alarmowy | Analiza przyczyn, IT/Data |
| Outcomes validation wskazuje materialne odchylenia | Zależy | MRM ocenia potrzebę re-walidacji |
| Zmiana regulacji dotycząca modelu | - | MRM ocenia wpływ |

---

## Przegląd Okresowy (Annual / Periodic Review)

<!-- PROMPT DLA AUTORA:
Opisz wymagania przeglądu okresowego — zakres, kto wykonuje, czego efektem jest.
-->

Przegląd okresowy jest formalnym przeglądem stanu modelu, wykraczającym poza bieżące raporty monitoringowe.

**Zakres przeglądu:**
- Podsumowanie wyników monitoringu za okres
- Ocena nadal aktualnych założeń modelu
- Przegląd findings z poprzedniej walidacji i statusu remediation
- Ocena czy zakres stosowania modelu nie zmienił się
- Decyzja: kontynuacja / rekalibracja / re-development / wycofanie
- Aktualizacja klasyfikacji Tier jeśli wymagana

**Wynik przeglądu:**
- Annual Review Report
- Decyzja o kolejnym roku funkcjonowania modelu lub eskalacja

---

## Kryteria Wyjścia (Ongoing Gate — Monitoring)

W cyklu bieżącym:
- [ ] Raport monitoringowy zgodnie z harmonogramem
- [ ] Brak przekroczonych progów krytycznych (lub jeśli przekroczone — eskalacja aktywna)
- [ ] Model Owner potwierdza aktualność i adekwatność modelu

W przeglądzie rocznym:
- [ ] Annual Review Report ukończony
- [ ] Decyzja o kontynuacji lub działaniu zaradczym udokumentowana

---

*Szablony: [Monitoring Plan Template](../../templates/), [Annual Review Template](../../templates/), [Monitoring Report Template](../../templates/)*
